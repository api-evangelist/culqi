# Culqi

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

Culqi is a Peruvian online payments platform and a Grupo Credicorp / Krealo company. Its REST API v2 lets businesses accept card, Yape, PagoEfectivo, mobile wallet and Cuotealo (installment) payments in PEN and USD, with card data tokenized client-side against a PCI-scoped secure host and all money movement, subscriptions and webhooks driven from a server-side secret key.

**Areas:** Payments · Payment Gateway · Fintech · Peru · Latin America · Cards · Yape

## Culqi on APIs.io

Everything profiled for Culqi is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/culqi/](https://apis.io/providers/culqi/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [Culqi Cards API](https://apis.io/apis/culqi/culqi-cards-api/) — Cards saved against a customer for recurring or one-click charges.
- [Culqi Charges API](https://apis.io/apis/culqi/culqi-charges-api/) — One-time charges (cargos) against a token or saved card.
- [Culqi Customers API](https://apis.io/apis/culqi/culqi-customers-api/) — Stored customer (cliente) profiles.
- [Culqi Events API](https://apis.io/apis/culqi/culqi-events-api/) — Webhook event objects representing account activity.
- [Culqi Iins API](https://apis.io/apis/culqi/culqi-iins-api/) — Card BIN / IIN metadata lookup.
- [Culqi Orders API](https://apis.io/apis/culqi/culqi-orders-api/) — Payment orders for PagoEfectivo (CIP) and bank-transfer / cash-agent flows.
- [Culqi Plans API](https://apis.io/apis/culqi/culqi-plans-api/) — Recurring-billing plan definitions.
- [Culqi Refunds API](https://apis.io/apis/culqi/culqi-refunds-api/) — Full or partial refunds (devoluciones) of a charge.
- [Culqi Subscriptions API](https://apis.io/apis/culqi/culqi-subscriptions-api/) — Subscriptions linking a saved card to a plan.
- [Culqi Tokens API](https://apis.io/apis/culqi/culqi-tokens-api/) — Client-side tokenization of card and Yape credentials on the secure host.
- [Culqi Transfers API](https://apis.io/apis/culqi/culqi-transfers-api/) — Settlement transfers (abonos) paid out to the merchant.
- [Culqi 3 DS API](https://apis.io/apis/culqi/culqi-3-ds-api/) — 3-D Secure charge confirmation on the secure host.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Culqi Events Webhooks](https://apis.io/asyncapis/culqi/culqi-events-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [culqi](https://apis.io/servers/culqi/culqi/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Culqi Agentic Access](https://apis.io/agentic-access/culqi/culqi-agentic-access/)

#### Collections (24)

Postman and Open Collection request collections.

- [Culqi API v2 3DS API](https://apis.io/collections/culqi/open-culqi-3ds-api/)
- [Culqi API v2 3DS Cards API](https://apis.io/collections/culqi/open-culqi-cards-api/)
- [Culqi API v2 3DS Charges API](https://apis.io/collections/culqi/open-culqi-charges-api/)
- [Culqi API v2 3DS Customers API](https://apis.io/collections/culqi/open-culqi-customers-api/)
- [Culqi API v2 3DS Events API](https://apis.io/collections/culqi/open-culqi-events-api/)
- [Culqi API v2 3DS Iins API](https://apis.io/collections/culqi/open-culqi-iins-api/)
- [Culqi API v2 3DS Orders API](https://apis.io/collections/culqi/open-culqi-orders-api/)
- [Culqi API v2 3DS Plans API](https://apis.io/collections/culqi/open-culqi-plans-api/)
- [Culqi API v2 3DS Refunds API](https://apis.io/collections/culqi/open-culqi-refunds-api/)
- [Culqi API v2 3DS Subscriptions API](https://apis.io/collections/culqi/open-culqi-subscriptions-api/)
- [Culqi API v2 3DS Tokens API](https://apis.io/collections/culqi/open-culqi-tokens-api/)
- [Culqi API v2 3DS Transfers API](https://apis.io/collections/culqi/open-culqi-transfers-api/)
- [Culqi API v2 3DS API](https://apis.io/collections/culqi/postman-culqi-3ds-api/)
- [Culqi API v2 3DS Cards API](https://apis.io/collections/culqi/postman-culqi-cards-api/)
- [Culqi API v2 3DS Charges API](https://apis.io/collections/culqi/postman-culqi-charges-api/)
- [Culqi API v2 3DS Customers API](https://apis.io/collections/culqi/postman-culqi-customers-api/)
- [Culqi API v2 3DS Events API](https://apis.io/collections/culqi/postman-culqi-events-api/)
- [Culqi API v2 3DS Iins API](https://apis.io/collections/culqi/postman-culqi-iins-api/)
- [Culqi API v2 3DS Orders API](https://apis.io/collections/culqi/postman-culqi-orders-api/)
- [Culqi API v2 3DS Plans API](https://apis.io/collections/culqi/postman-culqi-plans-api/)
- [Culqi API v2 3DS Refunds API](https://apis.io/collections/culqi/postman-culqi-refunds-api/)
- [Culqi API v2 3DS Subscriptions API](https://apis.io/collections/culqi/postman-culqi-subscriptions-api/)
- [Culqi API v2 3DS Tokens API](https://apis.io/collections/culqi/postman-culqi-tokens-api/)
- [Culqi API v2 3DS Transfers API](https://apis.io/collections/culqi/postman-culqi-transfers-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Culqi Openapi Overlay](https://apis.io/overlays/culqi/culqi-openapi-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Culqi Authentication](https://apis.io/security/culqi/culqi-authentication/)
- [Culqi Domain Security](https://apis.io/security/culqi/culqi-domain-security/)
- [Culqi Trust Center](https://apis.io/security/culqi/culqi-trust-center/)
- [Culqi Vulnerability Disclosure](https://apis.io/security/culqi/culqi-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Culqi Plans Pricing](https://apis.io/plans/culqi/culqi-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Culqi Rate Limits](https://apis.io/rate-limits/culqi/culqi-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Culqi Finops](https://apis.io/finops/culqi/culqi-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://culqi.com/)
- [Documentation](https://docs.culqi.com/)
- [Getting started](https://docs.culqi.com/es/documentacion/primeros-pasos/introduccion/)
- [API reference](https://apidocs.culqi.com/)
- [Pricing](https://culqi.com/precios/)
- [Sign up](https://afiliate.culqi.com/)
- [Support](https://culqi.com/centro-de-ayuda/)
- [Blog](https://medium.com/team-culqi)
- [Terms of service](https://culqi.com/terminos_y_condiciones/)
- [Privacy policy](https://culqi.com/politicas-de-privacidad/)
- [GitHub](https://github.com/culqi)

## API Evangelist rating

**Kin Score 42.4** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 58.2 |
| Contract governance | 4.5 |
| Operational transparency | 34.2 |
| Developer ergonomics | 41.1 |
| Access clarity | 30.3 |

**Agent readiness 31.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 37.5** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/culqi/](https://apis.io/providers/culqi/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Culqi: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/culqi/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
