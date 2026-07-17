---
name: Save a card to a customer and subscribe to a plan
description: Create a customer, vault a tokenized card, define a plan, and start a recurring subscription.
api: openapi/culqi-openapi.yml
operations: [createCustomer, createCard, createPlan, createSubscription]
---

# Save a card and subscribe (Culqi)

Use this for recurring / subscription billing. All operations use the **secret key** on `https://api.culqi.com/v2`.

## Steps
1. **createCustomer** with `first_name`, `last_name`, `email`, `address`, `address_city`, `country_code` (e.g. `PE`), `phone_number`. Returns `cus_...`.
2. Tokenize the card first (see the tokenize-and-charge skill → `tkn_...`), then **createCard** with `customer_id` and `token_id`. Returns a saved card `crd_...`.
3. **createPlan** with `name`, `amount` (minor units), `currency_code`, `interval_unit_time`, `interval_count`, optional `limit`. Returns `pln_...`. (Reuse an existing plan if you already have one.)
4. **createSubscription** with `card_id` (`crd_...`) and `plan_id` (`pln_...`). Returns `sxn_...` with a `next_billing_date`.

## Rules
- A card must be **tokenized** before it can be saved — you cannot send raw PAN to createCard.
- Subscriptions bill the saved card automatically on each interval; there is no idempotency key, so avoid creating duplicate subscriptions — check listSubscriptions first.
- Starting a subscription commits the customer to recurring charges: confirm intent with a human before createSubscription.
