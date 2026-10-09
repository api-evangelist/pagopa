---
name: pagopa-manage-debt-positions
description: Create, publish, look up and invalidate a pagoPA debt position (GPD) for a creditor organization,
  then fetch the receipt once it is paid.
api: openapi/pagopa-gpd-v1-openapi.yml
operations:
- createPosition
- publishPosition
- getOrganizationDebtPositionByIUPD
- getOrganizationDebtPositions
- invalidatePosition
- getOrganizationReceiptIur
generated: '2026-10-09'
method: generated
source: openapi/pagopa-gpd-v1-openapi.yml
---

# Create, publish, look up and invalidate a pagoPA debt position (GPD) for a creditor organization, then fetch the receipt once it is paid.

## Steps

1. Call `createPosition` with the organization fiscal code and the debt position body (IUPD, payment options, transfers).
2. Call `publishPosition` on the IUPD so the notice becomes payable.
3. Poll `getOrganizationDebtPositionByIUPD` (or list with `getOrganizationDebtPositions`) to read the status.
4. If the debt is cancelled, call `invalidatePosition`.
5. Once paid, call `getOrganizationReceiptIur` from the Biz Events API (openapi/pagopa-biz-events-openapi.yml) to get the receipt.

## Notes

- Authentication: subscription key / API key header, as declared in the spec securitySchemes.
- PagoPA publishes no skills or AGENTS.md (searched 2026-10-09). This skill was generated from the OpenAPI.
