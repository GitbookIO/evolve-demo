---
icon: puzzle-piece
description: Connect Evolve to the tools you already use — Slack, Zapier, Segment, QuickBooks, NetSuite.
cover: .gitbook/assets/integrations-cover.png
coverY: 0
layout:
  width: wide
  tableOfContents:
    visible: false
---

# Integrations

Evolve plugs into the tools your team already uses. Five officially-supported integrations cover real-time alerts, no-code automation, customer-data routing, and accounting.

{% hint style="info" %}
**Suggesting an integration or a doc edit?** All Integrations pages accept change requests. Click **Edit on GitHub** in the page header, push a branch, and open a change request — our team reviews integration docs weekly.
{% endhint %}

<p><button type="button" class="button primary" data-action="ask" data-icon="gitbook-assistant">Ask the Evolve docs</button></p>

<p><button type="button" class="button secondary" data-action="ask" data-query="How do I set up Slack alerts for disputes?" data-icon="bell">Slack alerts</button> <button type="button" class="button secondary" data-action="ask" data-query="What Zapier triggers does Evolve expose?" data-icon="bolt-lightning">Zapier triggers</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I sync Evolve to QuickBooks?" data-icon="calculator">QuickBooks sync</button> <button type="button" class="button secondary" data-action="ask" data-query="What NetSuite mapping is required?" data-icon="building">NetSuite</button></p>

## Pick an integration

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-slack" style="color:$primary;">:slack:</i></h3></td><td><strong>Slack</strong></td><td>Real-time alerts for disputes, refunds, and platform events. Slash commands for lookups.</td><td><a href="slack/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-bolt-lightning" style="color:$primary;">:bolt-lightning:</i></h3></td><td><strong>Zapier</strong></td><td>Wire Evolve events to 6,000+ apps without writing code.</td><td><a href="zapier/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-circle-nodes" style="color:$primary;">:circle-nodes:</i></h3></td><td><strong>Segment</strong></td><td>Stream Evolve events into Segment as a source, or apply Segment events to customer records.</td><td><a href="segment/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-calculator" style="color:$primary;">:calculator:</i></h3></td><td><strong>QuickBooks</strong></td><td>Auto-create journal entries from each settlement. QuickBooks Online and Desktop.</td><td><a href="quickbooks/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-building" style="color:$primary;">:building:</i></h3></td><td><strong>NetSuite</strong></td><td>Multi-subsidiary journal entries, custom segment mapping, multi-currency reconciliation.</td><td><a href="netsuite/README.md">README.md</a></td></tr></tbody></table>

## Coming soon

The following integrations are in active development. Open change requests are linked from each — comment to influence the design or sign up to be a beta tester.

* **HubSpot** — sync Evolve customers to HubSpot contacts. ([open change request](https://github.com/evolve-pay/docs/pull/142))
* **Pipedrive** — Evolve charges as Pipedrive deal events. ([open change request](https://github.com/evolve-pay/docs/pull/156))
* **Xero** — like QuickBooks, for Xero customers. ([open change request](https://github.com/evolve-pay/docs/pull/161))

## Don't see what you need?

For tools not on this list, two paths:

{% columns %}
{% column width="50%" %}

### <i class="fa-bolt-lightning" style="color:$primary;">:bolt-lightning:</i> Zapier

If your tool integrates with Zapier, [our Zapier integration](zapier/README.md) is the fastest path. No engineering required.

{% endcolumn %}

{% column width="50%" %}

### <i class="fa-code" style="color:$primary;">:code:</i> Build your own

The [Webhooks API](../../developers/v2/webhooks/README.md) plus a few lines of code can wire Evolve to almost anything. The [tutorials](../tutorials/README.md) cover common patterns.

{% endcolumn %}
{% endcolumns %}
