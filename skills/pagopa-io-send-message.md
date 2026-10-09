---
name: pagopa-io-send-message
description: Check that a citizen can be reached on the IO app, then send them a message from a public
  administration service.
api: openapi/pagopa-io-services-openapi.yml
operations:
- getProfileByPOST
- submitMessageforUserWithFiscalCodeInBody
- getMessage
generated: '2026-10-09'
method: generated
source: openapi/pagopa-io-services-openapi.yml
---

# Check that a citizen can be reached on the IO app, then send them a message from a public administration service.

## Steps

1. Call `getProfileByPOST` with the fiscal code to check that the citizen is active and allows messages from the service.
2. Call `submitMessageforUserWithFiscalCodeInBody` with the content (subject, markdown, optional payment_data).
3. Call `getMessage` with the returned id to check the delivery status.

## Notes

- Authentication: subscription key / API key header, as declared in the spec securitySchemes.
- PagoPA publishes no skills or AGENTS.md (searched 2026-10-09). This skill was generated from the OpenAPI.
