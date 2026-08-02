---
name: Manage Wallapop webhooks
description: Subscribe to item, delivery, transaction, dispute, and chat events with signed webhook notifications via the Webhooks Connect API.
api: openapi/wallapop-webhooks-openapi-original.yml
operations: [createWebhook, findMyWebhooks, updateWebhook, updateWebhookToken, deleteWebhook]
generated: '2026-07-21'
method: generated
---

# Manage Wallapop webhooks

Base URL `https://connect.wallapop.com`, Bearer token auth. Full event catalog: `asyncapi/wallapop-webhooks-catalog.yml`.

## Steps

1. **Create a subscription** with `createWebhook` (`POST /webhooks`) passing your HTTPS `url` and the `events` list (18 types, e.g. `SALE_COMPLETED`, `ITEM_OUT_OF_STOCK`, `DELIVERY_REQUEST_STARTED`, `DISPUTE_CREATED`, `CHAT_LEAD_CREATED`). The `201` response returns the webhook `id` and the HMAC signing `token` — store it securely.
2. **Verify every delivery**: compute HMAC-SHA256 over `"<json payload>:<X-Wallapop-Timestamp>"` with the stored token and compare to `X-Wallapop-Signature`. Reject mismatches; the timestamp (epoch ms) prevents replay.
3. **Respond 2xx** quickly; the notification `id` is stable across retries — use it for deduplication.
4. **Audit subscriptions** with `findMyWebhooks` (`GET /webhooks`); **modify** url/events with `updateWebhook` (`PUT /webhooks/{webhookId}`).
5. **Rotate the signing token** with `updateWebhookToken` (`PATCH /webhooks/{webhookId}/token`); **remove** with `deleteWebhook` (`DELETE /webhooks/{webhookId}`).

## Rules

- Multi-publisher apps: put a unique identifier in the webhook URL query string (e.g. `?id=12345`) to map notifications to users.
- The endpoint must accept POST and return 2xx; payload shape is `{id, type, occurred_on, data}`.
- Errors use the `{code, message}` envelope: `INVALID_BODY_REQUEST`, `USER_UNAUTHORIZED`.
