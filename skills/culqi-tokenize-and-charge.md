---
name: Tokenize a card and create a charge
description: Turn raw card data into a single-use token on Culqi's secure host, then charge it.
api: openapi/culqi-openapi.yml
operations: [createToken, createCharge, getCharge]
---

# Tokenize a card and create a charge (Culqi)

Use this to accept a one-time card payment.

## Auth
- Tokenization runs on the **secure host** `https://secure.culqi.com/v2` with the **public key** (`pk_test_`/`pk_live_`), sent as `Authorization: Bearer pk_...`.
- The charge runs on the **server host** `https://api.culqi.com/v2` with the **secret key** (`sk_...`). Never expose the secret key client-side.

## Steps
1. **createToken** on the secure host with `card_number`, `cvv`, `expiration_month`, `expiration_year`, `email`. Returns a single-use token id `tkn_...`. (Yape? use **createYapeToken** → `ype_...`.)
2. **createCharge** on the server host with `amount` (integer minor units — 10000 = S/100.00), `currency_code` (`PEN` or `USD`), `email`, and `source_id` = the token id. Set `capture: false` for an authorization hold.
3. **getCharge** to confirm the outcome if needed.

## Rules
- Amounts are **integers in cents**; there are no decimals.
- Culqi has **no idempotency key** — do not blindly retry `createCharge`; if unsure whether it succeeded, list/get the charge before retrying (conventions/culqi-conventions.yml).
- On a declined charge you get an error object with a `decline_code` — map it via errors/culqi-decline-codes.yml (e.g. `insufficient_funds`, `incorrect_cvv`). Show `user_message` to the buyer, not `merchant_message`.
- A charge moves real money: get explicit human confirmation before calling createCharge (agentic-access/culqi-agentic-access.yml).
