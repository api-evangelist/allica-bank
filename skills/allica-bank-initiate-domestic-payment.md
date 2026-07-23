---
name: Initiate an Allica Bank domestic payment
description: Create a domestic payment consent, confirm funds, obtain PSU authorisation, and execute a single immediate domestic payment through Allica Bank's OBIE Read/Write Payment Initiation API.
api: openapi/allica-bank-payment-initiation-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
generated: '2026-07-23'
method: generated
---

# Initiate an Allica Bank domestic payment (PIS)

Allica's Payment Initiation API is an OBIE Read/Write v4.0 surface. A payment is always
executed against a previously PSU-authorised consent. FAPI/mTLS-gated; OBIE onboarding
required.

## Prerequisites
- FAPI OAuth2 access token bound to your mTLS client certificate.
- The `payments` scope (and `openid` for the PSU flow). See `scopes/allica-bank-scopes.yml`.
- Base URL: `https://rs1.api.ob.allica.bank/open-banking/v4.0/pisp`.

## Steps
1. **Create the payment consent** with `CreateDomesticPaymentConsents` (client-credentials token). Supply the `Initiation` block (debtor/creditor accounts, `InstructedAmount`, reference). You **must** send a unique required `x-idempotency-key` header (valid 24h). Returns a `ConsentId` in `AwaitingAuthorisation`.
2. **(Optional) Confirm funds** for the consent with `GetDomesticPaymentConsentsConsentIdFundsConfirmation`.
3. **Redirect the PSU to authorise** via the authorization-code flow with PSD2 SCA; exchange the code for a PSU access token.
4. **Verify the consent is Authorised** with `GetDomesticPaymentConsentsConsentId`.
5. **Execute the payment** with `CreateDomesticPayments`, referencing the `ConsentId` and repeating the exact `Initiation` block. Send a fresh required `x-idempotency-key`. Retrying with the same key within 24h is safe and will not double-pay.
6. **Poll payment status** with `GetDomesticPaymentsDomesticPaymentId` until it reaches a terminal status.

## Conventions & errors
- `x-idempotency-key` is required on every write — reuse it on retries (see `conventions/allica-bank-conventions.yml`).
- Send `x-fapi-interaction-id` for correlation.
- Errors use the OBIE `UK.OBIE.*` envelope — see `errors/allica-bank-problem-types.yml`. On `500`, retry the same key.
