---
icon: book-open
description: Operation reference for the v3 preview Payments API.
---

# Reference

The pages below are auto-generated from the `evolve-payments-v3` OpenAPI spec. Every operation has its own page with the full parameter list, request and response schemas, code samples in Node, Python, Go, Ruby, and cURL, and an interactive **Test it** panel.

{% hint style="warning" icon="flask" %}
**v3 is preview.** Endpoints and shapes can change without the usual deprecation cycle. Switch to the v2 variant for production.
{% endhint %}

## What changed from v2

A few naming and shape changes worth knowing while reading the reference:

* Resource renamed: `Charge` → `Payment` (`pay_*` IDs, `POST /payments` instead of `POST /charges`).
* `capture` boolean replaced by `capture_method` enum: `automatic` / `manual` / `automatic_async`.
* Authorization window extended from 7 to 30 days.
* Multi-currency capture: pass `capture_currency` distinct from `currency`.

## Spec source

```
../../openapi/v3/payments.yaml
```

The spec is uploaded to GitBook as `evolve-payments-v3` and synced from this file on every release.

## Related

* [Overview](../README.md) — preview features and what's changing from v2.
* [Conventions](../../getting-started/conventions.md) — what's true across every operation.
* [Webhooks → Event catalog](../../webhooks/event-catalog.md) — the events Payments emits.
