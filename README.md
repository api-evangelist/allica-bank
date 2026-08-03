# Allica Bank (allica-bank)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
