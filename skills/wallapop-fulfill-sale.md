---
name: Fulfill a Wallapop sale
description: Accept a shipping request and track the shipping transaction through delivery via the Transactions Connect API.
api: openapi/wallapop-transactions-openapi-original.yml
operations: [sellerPendingRequests, sellerRequest, acceptHomePickup, sellerPendingTransactions, sellerTransaction, registerDelivery, updateDeliveryStatus]
generated: '2026-07-21'
method: generated
---

# Fulfill a Wallapop sale

When a buyer purchases an item, a **shipping request** is created; accepting it creates the **shipping transaction**. Base URL `https://connect.wallapop.com`, Bearer token auth.

## Steps

1. **Find pending requests** with `sellerPendingRequests` (`GET /transactions/requests/pending`), or subscribe to the `DELIVERY_REQUEST_STARTED` webhook event instead of polling.
2. **Inspect a request** with `sellerRequest` (`GET /transactions/requests/{requestId}`) — includes buyer info, revenue, and carrier drop-off options.
3. **Accept it** with `acceptHomePickup` (`POST /transactions/requests/{requestId}/accept/home-pickup`) or the post-office variant (`POST /transactions/requests/{requestId}/accept/post-office` — no operationId in the spec). Generate and pass your own `transaction_id`; it deduplicates the accept call. A `409 INVALID_ACCEPT_REQUEST` means the request is no longer `PENDING`.
4. **Track transactions** with `sellerPendingTransactions` (`GET /transactions/pending`) and `sellerTransaction` (`GET /transactions/{transactionId}`).
5. **Custom carrier only:** register the shipment with `registerDelivery` (`POST /transactions/{transactionId}/delivery/register`) — a `409 ONGOING_DELIVERY` means one is already registered — then push tracking updates with `updateDeliveryStatus` (`PATCH /deliveries/{deliveryId}/status`).

## Rules

- Requests expire if not accepted — handle `DELIVERY_REQUEST_EXPIRED` / `DELIVERY_REQUEST_CANCELLED` webhook events.
- Disputes are read-only via `findDispute` (`GET /disputes/{disputeId}`); dispute management happens in Wallapop's own flows.
- Errors use the `{code, message}` envelope (`errors/wallapop-problem-types.yml`); production only, 36 req/s per seller.
