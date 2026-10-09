---
name: pagopa-send-digital-notification
description: Send a legal digital notification through SEND (Piattaforma Notifiche) and track its acceptance
  and delivery progress.
api: openapi/pagopa-send-b2b-pa-openapi.yml
operations:
- presignedUploadRequest
- sendNewNotificationV26
- retrieveNotificationRequestStatusV26
- retrieveSentNotificationV29
- createEventStreamV29
- consumeEventStreamV29
- retrieveNotificationLegalFacts
generated: '2026-10-09'
method: generated
source: openapi/pagopa-send-b2b-pa-openapi.yml
---

# Send a legal digital notification through SEND (Piattaforma Notifiche) and track its acceptance and delivery progress.

## Steps

1. Call `presignedUploadRequest` to get upload URLs, then upload the notification documents.
2. Call `sendNewNotificationV26` with the recipients and document references.
3. Poll `retrieveNotificationRequestStatusV26` until the request is accepted and an IUN is assigned.
4. Read details with `retrieveSentNotificationV29`.
5. For progress, create a stream with `createEventStreamV29` and read it with `consumeEventStreamV29`.
6. Get the legal proofs with `retrieveNotificationLegalFacts`.

## Notes

- Authentication: subscription key / API key header, as declared in the spec securitySchemes.
- PagoPA publishes no skills or AGENTS.md (searched 2026-10-09). This skill was generated from the OpenAPI.
