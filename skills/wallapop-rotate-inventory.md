---
name: Rotate Wallapop inventory within listing limits
description: Manage active/inactive listings against subscription limits — free slots correctly (sold vs delete vs inactivate) and activate target items.
api: openapi/wallapop-items-openapi-original.yml
operations: [getMyItemsLimits, userItems, userInactiveItems, markItemAsSold, deleteItem, inactivateItem, activateItem]
generated: '2026-07-21'
method: generated
---

# Rotate Wallapop inventory within listing limits

Wallapop subscriptions cap the number of simultaneously **active** items. Publishing beyond the limit silently creates items as Inactive. Base URL `https://connect.wallapop.com`, Bearer token auth.

## Steps

1. **Check capacity** with `getMyItemsLimits` (`GET /items/limits`) — each entry lists shared `category_ids`, `total`, `used`, and `available` slots.
2. **See what is hidden** with `userInactiveItems` (`GET /items/inactive`), or list everything with `userItems` (`GET /items`) and check for `inactive: { "flag": true }`.
3. **Free a slot with the right verb** (this keeps sales history accurate):
   - Sold outside Wallapop → `markItemAsSold` (`PUT /items/{id}/sold`).
   - Gone for good → `deleteItem` (`DELETE /items/{itemId}`).
   - Temporarily hidden (seasonal) → `inactivateItem` (`PUT /items/{id}/inactivate`) — requires Wallapop Pro.
4. **Activate the target item** with `activateItem` (`PUT /items/{id}/activate`) — requires Wallapop Pro.

## Rules

- `reserveItem` / `unReserveItem` (`PUT /items/{id}/reserve|unreserve`) handle buyer holds, not slot management.
- Sync your catalog using `attributes.external_id` (SKU) and `license_plate` (Cars category).
- Cursor pagination on list endpoints (`since` + `metadata.pagination.next`, 40/page); 36 req/s per seller; production only.
