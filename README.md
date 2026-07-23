# Allica Bank (allica-bank)

Allica Bank Limited is a UK financial-technology bank built specifically for established small and medium-sized businesses, offering business current accounts, savings, commercial mortgages, asset finance, and invoice finance. It is a privately owned, venture-backed challenger bank (not a mutual or building society), authorised by the Prudential Regulation Authority and regulated by the Financial Conduct Authority and PRA (FRN 821851). As an FCA-authorised ASPSP it participates in UK Open Banking under the OBIE Read/Write Standard and PSD2, publishing a public developer portal for Account Information, Payment Initiation, and Confirmation of Funds APIs on its Business Rewards accounts. Allica is not one of the nine CMA9 mandated banks.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/allica-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/allica-bank/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- FAPI
- United Kingdom
- Payments
- Account Information
- SME
- Business Banking
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Allica Bank Account and Transaction Information API

UK Open Banking Account Information Service (AIS) conformant to the OBIE Read/Write Standard v3.1 — account access consents, accounts, balances, transactions, beneficiaries, direct debits, standing orders, scheduled payments, parties, offers, and product data for Allica Business Rewards accounts. FAPI-secured (OAuth2/OIDC, mTLS, PSD2 SCA).

- **Human URL:** [https://developer.api.ob.allica.bank/](https://developer.api.ob.allica.bank/)
- **Base URL:** `https://rs1.api.ob.allica.bank/open-banking/v3.1/aisp`

#### Properties

- [OpenAPI](openapi/allica-bank-account-information-openapi.yaml) — Account and Transaction API Specification v3.1.10 (harvested verbatim from Allica's developer portal)
- [Documentation](https://developer.api.ob.allica.bank/perry/developer/welcome)

### Allica Bank Payment Initiation API

UK Open Banking Payment Initiation Service (PIS) conformant to the OBIE Read/Write Standard v4.0 — domestic payment, domestic scheduled payment, and domestic standing order consents and payments, plus payment-details and funds-confirmation resources. FAPI-secured (OAuth2/OIDC, mTLS, PSD2 SCA).

- **Human URL:** [https://developer.api.ob.allica.bank/](https://developer.api.ob.allica.bank/)
- **Base URL:** `https://rs1.api.ob.allica.bank/open-banking/v4.0/pisp`

#### Properties

- [OpenAPI](openapi/allica-bank-payment-initiation-openapi.yaml) — Payment Initiation API Specification v4.0.0 (harvested verbatim from Allica's developer portal)
- [Documentation](https://developer.api.ob.allica.bank/perry/developer/welcome)

### Allica Bank Confirmation of Funds API

UK Open Banking Confirmation of Funds (CBPII) capability, exposed via the OBIE Read/Write Standard and the `fundsconfirmations` OAuth scope. Documented on the developer portal; not independently verified without OBIE onboarding.

- **Human URL:** [https://developer.api.ob.allica.bank/](https://developer.api.ob.allica.bank/)
- **Base URL:** `https://rs1.api.ob.allica.bank/open-banking/v3.1/cbpii`

#### Properties

- [Documentation](https://developer.api.ob.allica.bank/perry/developer/welcome)

### Allica Bank Dynamic Client Registration API

OBIE Dynamic Client Registration (DCR) v3.2 endpoint for regulated Third Party Providers to register OAuth clients using Open Banking Directory Software Statement Assertions. Confirmed as the `registration_endpoint` in Allica's production OIDC discovery document.

- **Human URL:** [https://developer.api.ob.allica.bank/](https://developer.api.ob.allica.bank/)
- **Base URL:** `https://rs1.api.ob.allica.bank/dynamic-client-registration/v3.2/register`

#### Properties

- [Documentation](https://developer.api.ob.allica.bank/perry/developer/welcome)
- [OpenID Configuration](https://auth1.api.ob.allica.bank/.well-known/openid-configuration)

## Common Properties

- [Website](https://www.allica.bank/)
- [Developer Portal](https://developer.api.ob.allica.bank/)
- [Documentation](https://developer.api.ob.allica.bank/perry/developer/welcome)
- [Authentication (OIDC discovery)](https://auth1.api.ob.allica.bank/.well-known/openid-configuration)
- [LinkedIn](https://uk.linkedin.com/company/allicabank)
- [Blog](https://www.allica.bank/blog)
- [Support](https://help.allica.bank/)
- [Terms of Service](https://www.allica.bank/website-terms-of-use)
- [Privacy Policy](https://www.allica.bank/privacy-policy)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
