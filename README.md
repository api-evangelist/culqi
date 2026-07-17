# Culqi (culqi)

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
