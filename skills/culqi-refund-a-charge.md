---
name: Refund a charge
description: Issue a full or partial refund (devolución) against an existing Culqi charge.
api: openapi/culqi-openapi.yml
operations: [getCharge, createRefund, getRefund]
---

# Refund a charge (Culqi)

Uses the **secret key** on `https://api.culqi.com/v2`.

## Steps
1. **getCharge** with the charge id (`chr_...`) to read `amount` and `amount_refunded` and confirm the refundable balance.
2. **createRefund** with `charge_id`, `amount` (minor units — omit or match the full amount for a full refund), and a `reason` from the allowed set: `duplicado`, `fraudulento`, `solicitud_comprador`. Returns `ref_...`.
3. **getRefund** to confirm the refund state if needed.

## Rules
- You cannot refund more than `amount - amount_refunded`.
- `reason` must be one of the three enum values above — the API rejects other strings.
- A refund moves real money back to the cardholder: confirm with a human before createRefund (agentic-access/culqi-agentic-access.yml).
