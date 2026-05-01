---
icon: credit-card
description: The legacy v1 Payments API — deprecated, sunset 2026-12-31.
---

# Payments API

This is the **v1 Payments API** — the original Evolve API that's been deprecated since 2025-07. New integrations should not use it. Existing integrations should migrate to v2 before the sunset date. The operation reference is auto-generated and listed below this page in the sidebar.

{% hint style="warning" icon="triangle-exclamation" %}
**v1 is deprecated.** It will be sunset on **<code class="expression">space.vars.variant_sunset</code>**. After that date, every v1 endpoint returns `410 Gone`. Use the variant dropdown to switch to **v2** (stable, recommended).
{% endhint %}

## Base URL

```
https://api.evolve.com/v1
```

The default version date for v1 is <code class="expression">space.vars.api_version</code>. v1 has not received version-date updates since 2025-07-01 — only security patches.

## Resources

The v1 surface is source-prefixed:

* **Charges** — `POST /sources/charge` (deprecated), `GET /charges/{id}`.
* **Refunds** — `POST /sources/refund` against a charge.
* **Payouts** — list, retrieve.

## What's different from v2

The most consequential differences if you're reading v1 docs by accident:

* **Endpoints are source-prefixed.** `POST /sources/charge` instead of `POST /charges`. Different paths per source type.
* **Webhook signatures use HMAC-SHA1.** v2 uses HMAC-SHA256 — make sure you don't carry your v1 verifier into a v2 integration.
* **Idempotency keys are optional.** They're enforced on every write endpoint in v2.
* **Errors have language-specific messages.** v2 standardized `code` values; v1 messages varied by SDK locale.
* **No `Evolve-Version` header.** v1 was already a versioned URL path; we didn't have dated versioning yet.

## Migrating to v2

Most teams migrate in 2–4 days of engineering time. The [v1 → v2 migration guide](../../../guides/tutorials/migrate-payments-v1-to-v2.md) covers:

* Endpoint renaming.
* Webhook handler updates (SHA-1 → SHA-256).
* Idempotency-key generation.
* Field-by-field response shape diffs.

You can run v1 and v2 in parallel during cutover — both will accept production traffic until 2026-12-31.

<p><a href="../../../guides/tutorials/migrate-payments-v1-to-v2.md" class="button primary">Migration guide</a></p>

## Support during sunset

If you're on v1 and not yet migrated:

* Until 2026-09-30: full support, including bug fixes and security patches.
* 2026-10-01 to 2026-12-30: security patches only. New bug fixes go to v2.
* 2026-12-31: hard sunset. v1 endpoints return `410 Gone`.

[Contact your account team](mailto:support@evolve.com) if you need a migration extension or hands-on help.
