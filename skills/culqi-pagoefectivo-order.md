---
name: Create and confirm a PagoEfectivo order
description: Generate an asynchronous cash/bank-transfer payment order (PagoEfectivo CIP) and confirm it.
api: openapi/culqi-openapi.yml
operations: [createOrder, confirmOrder, getOrder]
---

# Create a PagoEfectivo order (Culqi)

Orders back asynchronous payment methods such as PagoEfectivo (which generates a CIP code the customer pays at a bank/agent). Uses the **secret key** on `https://api.culqi.com/v2`.

## Steps
1. **createOrder** with `amount` (minor units), `currency_code`, `description`, `order_number`, `client_details` (`first_name`, `last_name`, `email`, `phone_number`), and `expiration_date` (Unix timestamp when the CIP expires). Returns `ord_...` in state `created`.
2. **confirmOrder** with the `order_id` to generate the payment instrument (the PagoEfectivo `cip_code`). Give the customer the CIP code to pay.
3. **getOrder** to poll `state`, or subscribe to the `order.status.changed` webhook (asyncapi/culqi-events-webhooks.yml) to learn when it is paid.

## Rules
- The order is not paid at creation — it settles when the customer pays the CIP before `expiration_date`.
- Watch webhook events / getOrder for the paid state rather than assuming success.
