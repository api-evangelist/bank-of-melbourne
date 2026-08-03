# Bank of Melbourne (bank-of-melbourne)

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

Bank of Melbourne is a Victorian retail and business banking brand operated by Westpac Banking Corporation (ASX: WBC) as part of the Westpac Group. The original Bank of Melbourne was acquired by Westpac in 1997 and the brand was relaunched in 2011; today it operates under the St.George Bank banking authority within Westpac and is not a customer-owned mutual - it is a division of a publicly listed, APRA-regulated authorised deposit-taking institution (ADI). As an accredited Consumer Data Right (CDR) data holder, Bank of Melbourne exposes a public, unauthenticated Product Reference Data (PRD) API that conforms to the Australian Consumer Data Standards.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/bank-of-melbourne/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/bank-of-melbourne/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Banking
- Australia
- Product Reference Data
- ADI
- Westpac Group

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### Bank of Melbourne CDR Product Reference Data API

Public, unauthenticated Consumer Data Right (CDR) Product Reference Data API exposing Bank of Melbourne's banking products (term deposits, credit and charge cards, personal loans, residential mortgages, business loans, leases) in machine-readable form under the Australian Consumer Data Standards. Confirmed live at `https://digital-api.bankofmelbourne.com.au/cds-au/v1/banking/products` (HTTP 200, x-v 5) returning a `data.products` array of 25 products; a request with x-v 3 is rejected 406 Unsupported Version. Endpoints - `GET /banking/products` and `GET /banking/products/{productId}`.

- **Human URL:** [https://www.bankofmelbourne.com.au/online-services/open-banking](https://www.bankofmelbourne.com.au/online-services/open-banking)
- **Base URL:** `https://digital-api.bankofmelbourne.com.au/cds-au/v1`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Australia

#### Properties

- [Documentation](https://www.bankofmelbourne.com.au/online-services/open-banking)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-products)
- [OpenAPI](openapi/bank-of-melbourne-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.bankofmelbourne.com.au/)
- [Documentation](https://www.bankofmelbourne.com.au/online-services/open-banking)
- [Terms Of Service](https://www.bankofmelbourne.com.au/help/terms-conditions)
- [Privacy Policy](https://www.bankofmelbourne.com.au/privacy/privacy-statement)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

## Note on API Posture

Bank of Melbourne does not run a third-party developer portal (`developer.bankofmelbourne.com.au` and `api.bankofmelbourne.com.au` do not resolve). Its only public, developer-accessible API is the mandated CDR Product Reference Data API served on shared Westpac Group infrastructure. Consumer data sharing (accounts, balances, transactions) runs through the regulated CDR / Accredited Data Recipient (ADR) model using OAuth2 / OpenID Connect (FAPI) authorization, and is not open to arbitrary developers. The harvested OpenAPI is the shared DSB Consumer Data Standards "CDR Banking API" contract (OpenAPI 3.0.3, v1.36.0), not a bank-proprietary document.
