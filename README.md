# Bank of Melbourne (bank-of-melbourne)

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
