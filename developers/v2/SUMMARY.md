# Table of contents

* [Developers](README.md)

## Getting started

* [Quickstart](getting-started/quickstart.md)
* [Authentication](getting-started/authentication.md)
* [SDKs](getting-started/sdks.md)
* [Conventions](getting-started/conventions.md)
* [For AI agents](getting-started/for-ai-agents.md)

## Payments API

* [Overview](payments-api/payments-api.md)
* ```yaml
  props:
    models: false
    downloadLink: true
  type: builtin:openapi
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: evolve-payments-v2
  ```

## Identity API

* [Overview](identity-api/identity-api.md)
* ```yaml
  props:
    models: false
    downloadLink: true
  type: builtin:openapi
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: evolve-identity-v2
  ```

## Connect API

* [Overview](connect-api/connect-api.md)
* ```yaml
  props:
    models: false
    downloadLink: true
  type: builtin:openapi
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: evolve-connect-v2
  ```

## Webhooks

* [Overview](webhooks/webhooks.md)
* [Verifying signatures](webhooks/verifying-signatures.md)
* [Event catalog](webhooks/event-catalog.md)
* [Retries and replay](webhooks/retries-and-replay.md)

## MCP

* [Overview](mcp/mcp.md)
* [Connecting an agent](mcp/connecting-an-agent.md)
