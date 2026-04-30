---
description: Auto-generated reference for every endpoint in the Payments API.
icon: book-open
---

# Reference

This page is **auto-generated** from our OpenAPI specification at `../../openapi/v2/payments.yaml`. Every operation includes the full parameter list, response schema, and an interactive **Test it** panel.

{% hint style="info" %}
**This page renders the OpenAPI block when published.** In the GitBook editor, an OpenAPI Reference is added by clicking **Add new... → OpenAPI Reference** in the table of contents and selecting the `payments` spec. Each operation tag in the spec produces its own subpage with a "Test it" panel.
{% endhint %}

## How operations are organized

Operations are grouped by tag. The spec file uses these tags, each with a `x-page-title`, `x-page-icon`, and `x-page-description`:

| Tag       | Page title | Icon                  |
| --------- | ---------- | --------------------- |
| `charges` | Charges    | `credit-card`         |
| `refunds` | Refunds    | `rotate-left`         |
| `payouts` | Payouts    | `money-bill-transfer` |
| `balance` | Balance    | `scale-balanced`      |

When the OpenAPI block is rendered, each tag becomes a top-level section under this page with the operations listed in spec order.

## Spec source

```
../../openapi/v2/payments.yaml
```

Synced from the live API on every release. To pin a specific version locally, fetch the spec from the public URL:

```
<code class="expression">space.vars.docs_root</code>/openapi/v2/payments.yaml
```

## Hidden operations

Some operations are exposed in the API but not documented (internal endpoints, deprecated paths). These have `x-internal: true` in the spec and don't appear in the rendered reference:

```yaml
paths:
  /internal/some-op:
    post:
      operationId: internalOp
      x-internal: true
```

## Sample: the create-charge operation

For reference, here's how `POST /charges` is defined in the spec — this is the kind of detail the rendered reference will surface for every operation, with a **Test it** panel attached.

```yaml
paths:
  /charges:
    post:
      operationId: createCharge
      summary: Create a charge
      description: |
        Charge a payment method. The default behavior is authorize-and-capture in one step.
        Pass `capture: false` for two-step.
      tags: [charges]
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ChargeCreate'
      responses:
        '200':
          description: Charge succeeded
        '402':
          description: Card declined
        '422':
          description: Processing error — retry with same idempotency key
```

The rendered reference has the full schema documentation expanded in-line, with examples for every parameter.

## Related

* [Overview](../) — what's in v2, what changed since v1, what's coming in v3.
* [Conventions](../../getting-started/conventions.md) — what's true across every operation.
* [Webhooks → Event catalog](../../webhooks/event-catalog.md) — the events Payments emits.
