---
description: Charges, refunds, payouts, and balance — the stable v2 surface.
icon: credit-card
---

# Overview

The Payments API is the workhorse of Evolve — taking money, refunding money, and moving it to your bank. The full reference (every endpoint, every parameter) is auto-generated from our OpenAPI spec and lives at [Reference](reference/).

{% hint style="success" icon="circle-check" %}
**You're viewing v2 — the stable default.** Use the variant dropdown in the top bar to switch to **v1** (deprecated) or **v3** (preview).
{% endhint %}

## Base URL

```
https://api.evolve.com/v2
```

The default version date for v2 is <code class="expression">space.vars.api_version</code>. Pin it in your code with the `Evolve-Version` header — see [Authentication → API versioning](../getting-started/authentication.md#api-versioning).

## Resources

The reference covers every operation. The high-level groupings:

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-credit-card" style="color:$primary;">:credit-card:</i></h4></td><td><strong>Charges</strong></td><td>Create, capture, void, retrieve, list.</td><td><a href="reference/#charges">#charges</a></td></tr><tr><td><h4><i class="fa-rotate-left" style="color:$primary;">:rotate-left:</i></h4></td><td><strong>Refunds</strong></td><td>Full and partial refunds against a charge.</td><td><a href="reference/#refunds">#refunds</a></td></tr><tr><td><h4><i class="fa-money-bill-transfer" style="color:$primary;">:money-bill-transfer:</i></h4></td><td><strong>Payouts</strong></td><td>List, retrieve. Schedule is configured in the dashboard.</td><td><a href="reference/#payouts">#payouts</a></td></tr><tr><td><h4><i class="fa-scale-balanced" style="color:$primary;">:scale-balanced:</i></h4></td><td><strong>Balance</strong></td><td>Available, pending, and reserved balances per currency.</td><td><a href="reference/#balance">#balance</a></td></tr></tbody></table>

## What changed since v1

If you're migrating from v1, the most consequential changes:

* `POST /sources/charge` is gone. Use `POST /charges` directly — the source-type is inferred from the token.
* Error `code` values are stable across languages and won't change within v2.
* Webhook signatures use HMAC-SHA256 (v1 used HMAC-SHA1). See [Verifying signatures](../webhooks/verifying-signatures.md).
* Idempotency keys are required on every write endpoint, not optional.

The full migration walkthrough lives at [Guides → v1 → v2 migration](../../../guides/tutorials/migrate-payments-v1-to-v2.md). v1 sunset is **2026-12-31**.

## What's coming in v3

v3 is in preview today. Use the variant dropdown to flip over and explore. Highlights:

* `Charge` is renamed to `Payment`.
* `capture: true|false` becomes `capture_method: automatic|manual`.
* Authorization window extended from 7 to 30 days.
* Multi-currency capture — authorize in USD, capture in EUR at wholesale FX.

When v3 graduates to stable, we'll publish a migration tool. For now, treat v3 as exploratory.

## Conceptual background

For the product-side concepts behind these endpoints — what a charge actually does, how settlement timing works, when 3-D Secure applies — see the [Payments product space](../../../products/payments/). It's the right complement to the API reference.

## Try it

Every operation in the [Reference](reference/) has a **Test it** panel. Drop in your test API key, edit the request, and run it against test mode without leaving the docs.

<a href="reference/" class="button primary">Open the reference</a>
