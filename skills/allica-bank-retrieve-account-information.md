---
name: Retrieve Allica Bank account information
description: Set up an AIS account-access consent and read a business customer's accounts, balances, and transactions through Allica Bank's OBIE Read/Write Account Information API.
api: openapi/allica-bank-account-information-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountId, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
generated: '2026-07-23'
method: generated
---

# Retrieve Allica Bank account information (AIS)

Allica's Account Information API is an OBIE Read/Write v3.1 surface for Business Rewards
accounts. Every call is FAPI/mTLS-gated and scoped by a PSU-authorised consent. You must
be an OBIE-onboarded TPP (Software Statement Assertion + eIDAS/OB certificates).

## Prerequisites
- FAPI OAuth2 access token bound to your mTLS client certificate (see `authentication/allica-bank-authentication.yml`).
- The `accounts` scope (and `openid` for the PSU flow). See `scopes/allica-bank-scopes.yml`.
- Base URL: `https://rs1.api.ob.allica.bank/open-banking/v3.1/aisp`.

## Steps
1. **Create the account-access consent** with `CreateAccountAccessConsents` (client-credentials token), specifying the OBIE `Permissions` (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`). This returns a `ConsentId` in status `AwaitingAuthorisation`.
2. **Redirect the PSU to authorise** via the authorization-code flow (`authorization_endpoint` https://secure.allica.bank/open-banking) so PSD2 SCA is completed. Exchange the code for a PSU access token.
3. **Confirm the consent is Authorised** with `GetAccountAccessConsentsConsentId`.
4. **List accounts** with `GetAccounts`, then read a specific one with `GetAccountsAccountId`.
5. **Read balances** with `GetAccountsAccountIdBalances` (returns the `InterimAvailable` balance).
6. **Read transactions** with `GetAccountsAccountIdTransactions` — paginated at 100/page; follow `Links.Next`. Note the bulk `GET /transactions` form is not supported.

## Conventions & errors
- Send `x-fapi-interaction-id` (RFC 4122 UUID) for correlation; it is echoed back.
- Handle `401`/`403` as token/consent/scope failures and `429` with back-off.
- Errors use the OBIE `UK.OBIE.*` envelope — see `errors/allica-bank-problem-types.yml`.
