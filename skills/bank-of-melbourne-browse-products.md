---
name: Browse Bank of Melbourne banking products
description: >-
  List and inspect Bank of Melbourne's openly offered banking products via the
  public, unauthenticated CDR Product Reference Data API — filter the catalogue,
  page through results, then pull full fee and rate detail for a chosen product.
api: openapi/bank-of-melbourne-cds-banking-products-openapi.yml
operations:
  - listBankingProducts
  - getBankingProductDetail
---

# Browse Bank of Melbourne banking products

This skill uses Bank of Melbourne's public **Consumer Data Right Product
Reference Data** API. It is **unauthenticated** — no API key, token, or OAuth.
The only required header is the CDS version header. Bank of Melbourne is a
Westpac Group brand; this surface is served on shared Westpac Group
infrastructure.

Base URL: `https://digital-api.bankofmelbourne.com.au/cds-au/v1`

## Rules

- Always send the header **`x-v: 5`**. Bank of Melbourne serves version 5; older
  versions (e.g. `3`) return HTTP `406` `UnsupportedVersion` (confirmed live).
- These are safe, read-only `GET` calls. There is no idempotency key and no
  state change.
- Errors come back as a CDS `errors[]` array (`{code, title, detail}`), not
  RFC 9457 problem+json.

## Steps

1. **List products** — call `listBankingProducts`:
   `GET /banking/products` with `x-v: 5`.
   Optional filters: `effective` (`CURRENT`|`FUTURE`|`ALL`), `updated-since`,
   `brand`, `product-category` (e.g. `RESIDENTIAL_MORTGAGES`,
   `TRANS_AND_SAVINGS_ACCOUNTS`, `CRED_AND_CHRG_CARDS`, `TERM_DEPOSITS`,
   `PERS_LOANS`, `BUSINESS_LOANS`, `LEASES`).
   Paginate with `page` and `page-size` (default 25). Read `meta.totalRecords`
   (40 at last probe) and `meta.totalPages` to know how far to page. Each item
   carries a `productId`.

2. **Get product detail** — for a `productId` of interest, call
   `getBankingProductDetail`: `GET /banking/products/{productId}` with `x-v: 5`.
   The `data` object adds `fees`, `depositRates`, `lendingRates` (with tiered
   `tiers`), `features`, `constraints`, `eligibility`, and `bundles`.

3. **Interpret rates and fees** — lending/deposit rates carry a
   `rate` (RateString) plus `lendingRateType`/`depositRateType`; fees carry
   `feeType` and one of `amount`/`balanceRate`/`transactionRate`/`accruedRate`.
   Currency defaults to `AUD` when absent.

## Notes

- Consumer/account data beyond this product catalogue is **not** available here —
  it requires CDR Accredited Data Recipient accreditation and the consent flow.
- Although the harvested OpenAPI includes accounts / balances / transactions
  operations, only `/banking/products` and `/banking/products/{productId}` are
  public and unauthenticated.
