# Culqi (culqi)

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

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/culqi/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/culqi/refs/heads/main/apis.yml)

## Tags

- Payments
- Payment Gateway
- FinTech
- Peru
- LatAm
- Cards
- Yape

## Timestamps

- **Created:** 2026-07-17
- **Modified:** 2026-07-17

## Hosts & Authentication

Culqi API v2 spans two hosts, both authenticated with an HTTP Bearer key:

- `https://api.culqi.com/v2` — server-side operations (charges, orders, refunds, customers, cards, plans, subscriptions, events, iins, transfers), authenticated with the **secret key** (`sk_live_`/`sk_test_`).
- `https://secure.culqi.com/v2` — PCI-scoped card/Yape tokenization and 3-D Secure charge confirmation, authenticated with the **public key** (`pk_live_`/`pk_test_`).

Amounts are integers in the currency minor unit (cents); `currency_code` is `PEN` or `USD`.

## APIs

### Culqi Tokens API

Client-side tokenization of card and Yape credentials on the PCI-scoped secure host using the public key (pk_). Returns a single-use token (tkn_/ype_) used as the source_id for a charge, plus 3DS charge confirmation.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/api-directa/introduccion/](https://docs.culqi.com/es/documentacion/pagos-online/api-directa/introduccion/)
- **Base URL:** `https://secure.culqi.com/v2`

#### Tags

- Tokens
- Tokenization
- PCI

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/culqi-js/v4/culqi-js/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Charges API

Create, capture, retrieve and list one-time charges (cargos) against a token, saved card or Yape token. Supports authorization holds and Cuotealo installments.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/cargo-unico/resumen/](https://docs.culqi.com/es/documentacion/pagos-online/cargo-unico/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Charges
- Payments
- Cargos

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/cargo-unico/cargos/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Orders API

Payment orders for asynchronous methods such as PagoEfectivo (generates a CIP code) and bank transfers, with create, confirm, retrieve, list, update and delete operations.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/pago-efectivo/resumen/](https://docs.culqi.com/es/documentacion/pagos-online/pago-efectivo/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Orders
- PagoEfectivo
- Bank Transfer

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/pago-efectivo/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Refunds API

Full or partial refunds (devoluciones) of a charge, with a documented reason (duplicado, fraudulento, solicitud_comprador).

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/devoluciones/resumen/](https://docs.culqi.com/es/documentacion/pagos-online/devoluciones/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Refunds
- Devoluciones

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/devoluciones/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Customers API

Create, retrieve, list, update and delete stored customer (cliente) profiles for saving cards and running recurring payments.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/clientes/resumen/](https://docs.culqi.com/es/documentacion/pagos-online/clientes/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Customers
- Clientes

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/clientes/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Cards API

Save a tokenized card to a customer and manage saved cards (create, retrieve, list, update, delete) for one-click and recurring charges.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/tarjetas/resumen/](https://docs.culqi.com/es/documentacion/pagos-online/tarjetas/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Cards
- Tarjetas
- Vault

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/tarjetas/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Plans API

Define recurring-billing plans (interval, amount, currency, limit) that subscriptions bill against.

- **Human URL:** [https://docs.culqi.com/es/documentacion/suscripciones/resumen/](https://docs.culqi.com/es/documentacion/suscripciones/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Plans
- Recurring
- Planes

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/suscripciones/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Subscriptions API

Subscribe a saved card to a plan for recurring charges, with create, retrieve, list, update and cancel operations.

- **Human URL:** [https://docs.culqi.com/es/documentacion/suscripciones/resumen/](https://docs.culqi.com/es/documentacion/suscripciones/resumen/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Subscriptions
- Recurring
- Suscripciones

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/suscripciones/resumen/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Events & Webhooks API

Retrieve and list account event objects (charge.creation.succeeded, order.status.changed, and more) that Culqi delivers to configured webhook endpoints as HTTP callbacks.

- **Human URL:** [https://docs.culqi.com/es/documentacion/pagos-online/webhooks/](https://docs.culqi.com/es/documentacion/pagos-online/webhooks/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Events
- Webhooks
- Eventos

#### Properties

- [Documentation](https://docs.culqi.com/es/documentacion/pagos-online/webhooks/)
- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi IIN Lookup API

Look up card IIN/BIN metadata (brand, card type, issuer, country, installments allowed) to drive checkout logic.

- **Human URL:** [https://apidocs.culqi.com/](https://apidocs.culqi.com/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- IIN
- BIN
- Card Metadata

#### Properties

- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Culqi Transfers API

Retrieve and list settlement transfers (abonos) paid out to the merchant bank account.

- **Human URL:** [https://apidocs.culqi.com/](https://apidocs.culqi.com/)
- **Base URL:** `https://api.culqi.com/v2`

#### Tags

- Transfers
- Settlement
- Abonos

#### Properties

- [API Reference](https://apidocs.culqi.com/)
- [OpenAPI](openapi/culqi-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/culqi.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

## Common Properties

- [Agentic Access](agentic-access/culqi-agentic-access.yml)
- [Trust Center](security/culqi-trust-center.yml)
- [Vulnerability Disclosure](security/culqi-vulnerability-disclosure.yml)
- [Domain Security](security/culqi-domain-security.yml)
- [Authentication](authentication/culqi-authentication.yml)
- [GitHub Organization](https://github.com/culqi)
- [LinkedIn](https://www.linkedin.com/company/culqi)
- [Website](https://culqi.com/)
- [Documentation](https://docs.culqi.com/)
- [Plans](plans/culqi-plans-pricing.yml)
- [Rate Limits](rate-limits/culqi-rate-limits.yml)
- [Fin Ops](finops/culqi-finops.yml)
- [Blog](https://medium.com/team-culqi)

## Notes

- **Ownership:** In January 2019 Grupo Crédito S.A. (Credicorp) acquired 91.36% of Culqi and later took it to 100%; Culqi sits alongside Credicorp's digital-venture arm Krealo.
- **Compliance:** Culqi is a PCI DSS Level 1 processor. Merchants calling the API directly with raw card data must comply with PCI DSS 3.2 and submit an SAQ-D; Culqi recommends client-side tokenization via Culqi Checkout / Culqi JS v4 plus Culqi 3DS and antifraud device fingerprinting.
- **Spec provenance:** Culqi publishes no downloadable OpenAPI/Swagger document (the reference at apidocs.culqi.com is a client-rendered SPA). The included OpenAPI was modeled from Culqi's live documentation and official SDKs (culqi-python, culqi-go, culqi-php), verified July 2026.
- **No WebSocket API.** Culqi is REST-only over HTTPS; asynchronous payment status is delivered via outbound HTTP webhook callbacks, not WebSocket or SSE. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
