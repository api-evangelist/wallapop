---
name: Publish an item on Wallapop
description: Create and publish a marketplace listing via the Items Connect API, including category selection, attribute validation, and additional images.
api: openapi/wallapop-items-openapi-original.yml
operations: [createItem, getCategoryAttributes, addItemImage, getItem, userItems]
generated: '2026-07-21'
method: generated
---

# Publish an item on Wallapop

Use the Items Connect API (`https://connect.wallapop.com`) with a Bearer access token obtained via OAuth 2.0 Authorization Code + PKCE (see `authentication/wallapop-authentication.yml`).

## Steps

1. **Pick the category.** Fetch the category tree with `GET /items/categories` (this operation has no operationId in the spec) and choose the most specific *leaf* category — broad categories are rejected.
2. **Check the category's attributes** with `getCategoryAttributes` (`GET /items/categories/{id}/attributes`). Respect mandatory attributes and constraints (e.g. `max_length`); an invalid attribute fails the request with `INVALID_ATTRIBUTE`.
3. **Create the item** with `createItem` (`POST /items`). Required: `item.category_leaf_id`, `item.title`, `item.description`, `item.price` (`cash_amount` + `currency`, EUR only) and `main_image.url` (direct JPG/JPEG link, 2xx, ≤10 MB). Use `attributes.external_id` to store your SKU. A `201 Created` returns the item `id`.
4. **Add more images** with `addItemImage` (`POST /items/{itemId}/images`); order controls display order. Watch for `MAX_IMAGES_EXCEED`.
5. **Verify** with `getItem` or list your live listings with `userItems` (`GET /items`, cursor pagination: pass `metadata.pagination.next` back as `since`, max 40/page).

## Rules

- If the account's listing limit is full the item is still created (`201`) but set **Inactive** — check `GET /items/limits` (`getMyItemsLimits`) first.
- Errors return `{code, message}` (see `errors/wallapop-problem-types.yml`); common publish failures: `MISSING_MAIN_IMAGE`, `INVALID_CATEGORY_LEAF`, `USER_LOCATION_MISSING`.
- Stay under 36 requests/second per seller.
- There is no sandbox — you are operating on production.
