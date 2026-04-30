---
icon: book-open
description: Operation reference for the v2 Payments API — the stable default.
---

# Reference

The pages below are auto-generated from the `evolve-payments-v2` OpenAPI spec. Every operation has its own page with the full parameter list, request and response schemas, code samples in Node, Python, Go, Ruby, and cURL, and an interactive **Test it** panel.

## Spec source

```
../../openapi/v2/payments.yaml
```

The spec is uploaded to GitBook as `evolve-payments-v2` and synced from this file on every release.

## Hidden operations

Some operations are exposed in the API but not documented (internal endpoints, deprecated paths). These have `x-internal: true` in the spec and don't appear in the rendered reference:

```yaml
paths:
  /internal/some-op:
    post:
      operationId: internalOp
      x-internal: true
```

## Related

* [Overview](../README.md) — what's in v2, what changed since v1, what's coming in v3.
* [Conventions](../../getting-started/conventions.md) — what's true across every operation.
* [Webhooks → Event catalog](../../webhooks/event-catalog.md) — the events Payments emits.
