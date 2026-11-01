# Wallapop

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Wallapop is a Barcelona-based consumer marketplace for buying and selling second-hand items across Spain, Italy, and Portugal, backed by Accel, Insight Partners, and Northzone. Its Wallapop Connect API lets professional sellers and third-party integrators programmatically publish and manage listings (Items Connect API), accept shipping requests and track transactions through delivery (Transactions Connect API), and subscribe to signed event notifications (Webhooks Connect API), all secured with OAuth 2.0 Authorization Code + PKCE via its Keycloak-based identity service.

**Areas:** Company · Consumer · Marketplace · E-Commerce · Secondhand · Classifieds · Shipping · Webhook

## Wallapop on APIs.io

Everything profiled for Wallapop is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/wallapop/](https://apis.io/providers/wallapop/)** — or go straight to one of the APIs or properties below.

### APIs (6)

- [Wallapop Categories API](https://apis.io/apis/wallapop/wallapop-categories-api/) — A category is a classification for product listings, with specific attributes and constraints that products within the category must adhere to.
- [Wallapop Delivery API](https://apis.io/apis/wallapop/wallapop-delivery-api/) — The Delivery API from Wallapop — 1 operation(s) for delivery.
- [Wallapop Disputes API](https://apis.io/apis/wallapop/wallapop-disputes-api/) — The Disputes API from Wallapop — 1 operation(s) for disputes.
- [Wallapop Items API](https://apis.io/apis/wallapop/wallapop-items-api/) — An item refers to a listing created by a user on the Wallapop marketplace, indicating their intent to sell. These items can include a diverse range of products.
- [Wallapop Transactions API](https://apis.io/apis/wallapop/wallapop-transactions-api/) — A shipping transaction is initiated when a seller accepts a shipping request.
- [Wallapop Webhooks API](https://apis.io/apis/wallapop/wallapop-webhooks-api/) — Webhooks allow you to receive event notifications.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Wallapop Webhooks Catalog](https://apis.io/asyncapis/wallapop/wallapop-webhooks-catalog/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [wallapop-connect-docs](https://apis.io/servers/wallapop/wallapop-connect-docs/)

#### Collections (6)

Postman and Open Collection request collections.

- [Items Connect Categories API](https://apis.io/collections/wallapop/open-wallapop-categories-api/)
- [Items Connect Categories Delivery API](https://apis.io/collections/wallapop/open-wallapop-delivery-api/)
- [Items Connect Categories Disputes API](https://apis.io/collections/wallapop/open-wallapop-disputes-api/)
- [Connect Categories Items API](https://apis.io/collections/wallapop/open-wallapop-items-api/)
- [Items Connect Categories Transactions API](https://apis.io/collections/wallapop/open-wallapop-transactions-api/)
- [Items Connect Categories Webhooks API](https://apis.io/collections/wallapop/open-wallapop-webhooks-api/)

#### Overlays (3)

OpenAPI overlays, including conversational phrasing for each operation.

- [Wallapop Items Overlay](https://apis.io/overlays/wallapop/wallapop-items-overlay/)
- [Wallapop Transactions Overlay](https://apis.io/overlays/wallapop/wallapop-transactions-overlay/)
- [Wallapop Webhooks Overlay](https://apis.io/overlays/wallapop/wallapop-webhooks-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Wallapop Authentication](https://apis.io/security/wallapop/wallapop-authentication/)
- [Wallapop Domain Security](https://apis.io/security/wallapop/wallapop-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Wallapop Scopes](https://apis.io/scopes/wallapop/wallapop-scopes/)

#### Rate limits (1)

Published request limits.

- [Wallapop Rate Limits](https://apis.io/rate-limits/wallapop/wallapop-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.wallapop.com)
- [Documentation](https://developers.wallapop.com/intro)
- [Getting started](https://developers.wallapop.com/pages/guides/quickstart)
- [API reference](https://developers.wallapop.com/apis/)
- [Pricing](https://es.wallapop.com/wallapop-pro)
- [Sign up](https://es.wallapop.com/login)
- [Support](https://ayuda.wallapop.com/)
- [Terms of service](https://es.wallapop.com/toc)
- [Privacy policy](https://es.wallapop.com/privacy)
- [GitHub](https://github.com/Wallapop)

## API Evangelist rating

**Kin Score 53.0** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 58.0 |
| Contract governance | 4.5 |
| Operational transparency | 57.9 |
| Developer ergonomics | 56.5 |
| Access clarity | 44.7 |

**Agent readiness 47.4** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | platform (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 34.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/wallapop/](https://apis.io/providers/wallapop/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Wallapop: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/wallapop/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
