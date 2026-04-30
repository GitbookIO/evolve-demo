# Table of contents

* [Developers](README.md)

## Getting started

* [Quickstart](getting-started/quickstart.md)
* [Authentication](getting-started/authentication.md)
* [SDKs](getting-started/sdks.md)
* [Conventions](getting-started/conventions.md)
* [For AI agents](getting-started/for-ai-agents.md)

## Payments API

* [Overview](payments-api/README.md)
* [Reference](payments-api/reference/README.md)
  * ```yaml
    type: builtin:openapi
    props:
      models: true
      downloadLink: true
    dependencies:
      spec:
        ref:
          kind: openapi
          spec: evolve-payments-v2
    ```

## Identity API

* [Overview](identity-api/README.md)
* [Reference](identity-api/reference.md)

## Connect API

* [Overview](connect-api/README.md)
* [Reference](connect-api/reference.md)

## Webhooks

* [Overview](webhooks/README.md)
* [Verifying signatures](webhooks/verifying-signatures.md)
* [Event catalog](webhooks/event-catalog.md)
* [Retries and replay](webhooks/retries-and-replay.md)

## MCP

* [Overview](mcp/README.md)
* [Connecting an agent](mcp/connecting-an-agent.md)
