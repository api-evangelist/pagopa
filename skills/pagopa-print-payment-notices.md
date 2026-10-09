---
name: pagopa-print-payment-notices
description: Generate printable pagoPA payment notices (avvisi), one at a time or in bulk, and download
  the result.
api: openapi/pagopa-print-payment-notices-openapi.yml
operations:
- getTemplates
- generateNotice
- generateNoticeMassiveRequest
- getFolderStatus
- getFolderSignedUrlResource
- getSignedUrlResource
generated: '2026-10-09'
method: generated
source: openapi/pagopa-print-payment-notices-openapi.yml
---

# Generate printable pagoPA payment notices (avvisi), one at a time or in bulk, and download the result.

## Steps

1. Pick a template with `getTemplates`.
2. Generate one notice with `generateNotice`, or many with `generateNoticeMassiveRequest`, which returns a folder id.
3. For a bulk request, poll `getFolderStatus`.
4. Download with `getFolderSignedUrlResource` (the whole folder) or `getSignedUrlResource` (a single file).

## Notes

- Authentication: subscription key / API key header, as declared in the spec securitySchemes.
- PagoPA publishes no skills or AGENTS.md (searched 2026-10-09). This skill was generated from the OpenAPI.
