---
icon: credit-card
description: The v3 preview Payments API — Payment object, capture_method, multi-currency capture.
---

# Payments API

This is the **v3 Payments API** — currently in preview. v3 introduces a small set of breaking changes that pay off for teams doing pre-orders, hospitality holds, marketplaces, and multi-currency commerce.

{% hint style="warning" icon="flask" %}
**v3 is preview.** Endpoints and shapes can change without the usual deprecation cycle. Don't use it for production traffic without coordinating with your account team. Use the variant dropdown to switch to **v2** (stable) for production.
{% endhint %}

## Base URL

```
https://api.evolve.com/v3
```

The default version date for v3 is <code class="expression">space.vars.api_version</code>. While in preview, the default version may change without notice — pin explicitly with the `Evolve-Version` header in any non-throwaway code.

## Resources

The v3 reference covers every operation. The most-used endpoints:

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-credit-card" style="color:$primary;">:credit-card:</i></h3></td><td><strong>Payments</strong></td><td>Renamed from "Charges". Same lifecycle, new name.</td><td><a href="reference/README.md">reference/README.md</a></td></tr><tr><td><h3><i class="fa-rotate-left" style="color:$primary;">:rotate-left:</i></h3></td><td><strong>Refunds</strong></td><td>Now reference <code>payment</code> instead of <code>charge</code>.</td><td><a href="reference/README.md">reference/README.md</a></td></tr><tr><td><h3><i class="fa-money-bill-transfer" style="color:$primary;">:money-bill-transfer:</i></h3></td><td><strong>Payouts</strong></td><td>Same as v2.</td><td><a href="reference/README.md">reference/README.md</a></td></tr><tr><td><h3><i class="fa-scale-balanced" style="color:$primary;">:scale-balanced:</i></h3></td><td><strong>Balance</strong></td><td>Same as v2, plus per-currency holds.</td><td><a href="reference/README.md">reference/README.md</a></td></tr></tbody></table>

## What's new in v3

### `Charge` is renamed to `Payment`

The object you create is now a `Payment` (`pay_*` ID) instead of a `Charge` (`ch_*`). Every endpoint that operated on charges now operates on payments. Webhook events are renamed accordingly: `charge.succeeded` → `payment.succeeded`, etc.

```diff
-POST /v2/charges       → returns ch_3KsM12pL9qXa7
+POST /v3/payments      → returns pay_3KsM12pL9qXa7
```

### `capture_method` enum replaces `capture` boolean

```diff
-POST /v2/charges  { "capture": false }
+POST /v3/payments { "capture_method": "manual" }
```

Three values: `automatic` (default, captures immediately), `manual` (creates an authorization, capture later), and the new `automatic_async` (captures within 24 hours when the network has confirmed authorization — useful for high-volume marketplaces that want capture batching).

### 30-day authorization window

Manual-capture authorizations now hold for **30 days** instead of 7. This unlocks pre-order and hospitality flows that v2 couldn't support without re-authing.

### Multi-currency capture

Authorize in one currency, capture in another at the daily wholesale rate plus your configured FX margin:

```http
POST /v3/payments
{
  "authorize_amount": 10000,
  "authorize_currency": "usd",
  "capture_currency": "eur",
  "capture_method": "manual"
}
```

Capture amount and currency are decided at capture time. Useful for marketplaces with international sellers — you authorize in the buyer's currency and pay out in the seller's.

### Webhooks: `payment.*` events

The full event taxonomy is renamed. See [v3 webhooks event catalog](../webhooks/event-catalog.md). Subscribe to `payment.*` instead of `charge.*` when you flip a webhook endpoint to v3.

## Should you use v3 today?

| If you're... | Recommendation |
| --- | --- |
| Building a brand-new integration | Start on v2. Migrate to v3 when it graduates. |
| Operating production traffic on v2 | Stay on v2. v3 has no production-readiness commitments yet. |
| Building a pre-orders, hospitality, or marketplace flow | v3 is worth piloting in a side environment — the 30-day holds and multi-currency capture matter. |
| Building an internal tool or admin panel | v3 is fine — your blast radius is small. |

## Graduation timeline

v3 is targeting graduation to stable around **mid-2026**. We're not committing to a date publicly until we've been through a beta-customer cohort. Sign up for the v3 beta program from your dashboard if you want early access and influence over the final shape.

## Try it

Every operation in the [Reference](reference/README.md) has a **Test it** panel. Drop in your test API key, edit the request, and run it against test mode without leaving the docs.

<p><a href="reference/README.md" class="button primary">Open the reference</a></p>
