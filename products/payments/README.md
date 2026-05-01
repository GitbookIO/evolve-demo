---
icon: credit-card
description: Route, reconcile, and report on every payment.
cover: .gitbook/assets/payments-cover.png
coverY: 0
layout:
  width: wide
---

# Payments

Evolve Payments handles the work between a customer's "pay" click and the money landing in your account — card and bank-rail processing, network routing, 3-D Secure, settlement, and reporting. This space covers everything from the first test charge to enterprise routing rules.

{% hint style="success" icon="gitbook" %}
**A note from GitBook**

This space is the deepest in the demo and shows off three GitBook features: **adaptive content** (hints and entire blocks change with the visitor), **space variables** (URLs and constants pulled from `vars.yaml`), and **synced blocks** (the test/live environments table is reused across all three product spaces).

Try a persona to see adaptive content in action:

<p><a href="?persona=new" class="button secondary">As a new user</a> <a href="?persona=existing" class="button secondary">As an existing customer</a> <a href="?persona=prospect" class="button secondary">As a prospect</a> <a href="?persona=partner" class="button secondary">As a partner</a></p>

Or stack with `?plan=starter`, `?plan=growth`, or `?plan=enterprise` for plan-tier-gated content.
{% endhint %}

{% hint style="info" %}
**Looking for the API reference?** Endpoints, parameters, and SDK examples live in [Developers / Payments API](../../developers/payments-api/README.md). This space focuses on concepts and workflows.
{% endhint %}

<p><button type="button" class="button primary" data-action="ask" data-icon="gitbook-assistant">Ask the Evolve docs</button></p>

<p><button type="button" class="button secondary" data-action="ask" data-query="How do I accept my first payment?" data-icon="rocket">First payment</button> <button type="button" class="button secondary" data-action="ask" data-query="What's in a settlement file?" data-icon="file-csv">Settlement files</button> <button type="button" class="button secondary" data-action="ask" data-query="When do I need 3-D Secure?" data-icon="shield-halved">3-D Secure</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I route around card declines?" data-icon="route">Smart routing</button></p>

## Start here

{% if visitor.claims.unsigned.persona === "new" %}

{% hint style="info" icon="hand-wave" %}
**New to Evolve?** Welcome. The Quickstart below takes about five minutes and ends with a real test charge in your dashboard. You don't need to write any code yet — the dashboard works on its own.
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}

{% hint style="info" icon="arrows-left-right" %}
**Migrating from Stripe?** Most of our APIs map cleanly. Start with the [Stripe migration guide](../../guides/tutorials/migrating-from-stripe.md) — it covers field mapping, webhook differences, and how to run both processors in parallel during cutover.
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "prospect" %}

{% hint style="info" icon="store" %}
**Evaluating Evolve for Shopify?** Our [Shopify integration guide](../../guides/integrations/shopify.md) covers setup, supported payment methods by region, and how Evolve handles refunds initiated from the Shopify admin. You can run it against a test store today.
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}

{% hint style="info" icon="building" %}
**Setting up enterprise features?** Smart routing, network selection, and failover are documented under [Accept payments](accept-payments/README.md). For SSO, audit logs, and account hierarchy, see your account team or the [Enterprise admin guide](../../guides/tutorials/enterprise-admin-setup.md).
{% endhint %}

{% endif %}

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-rocket" style="color:$primary;">:rocket:</i></h3></td><td><strong>Quickstart</strong></td><td>Take your first test payment in five minutes.</td><td><a href="quickstart/accept-your-first-payment.md">accept-your-first-payment.md</a></td></tr><tr><td><h3><i class="fa-book-open" style="color:$primary;">:book-open:</i></h3></td><td><strong>Concepts</strong></td><td>How payments move through Evolve.</td><td><a href="concepts/payment-lifecycle.md">payment-lifecycle.md</a></td></tr><tr><td><h3><i class="fa-bolt" style="color:$primary;">:bolt:</i></h3></td><td><strong>Accept payments</strong></td><td>Charges, saved methods, 3-D Secure, routing.</td><td><a href="accept-payments/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-scale-balanced" style="color:$primary;">:scale-balanced:</i></h3></td><td><strong>Reconciliation</strong></td><td>Settlement files, refunds, disputes.</td><td><a href="reconciliation/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-chart-line" style="color:$primary;">:chart-line:</i></h3></td><td><strong>Reporting</strong></td><td>Daily reports, exports, and finance pushes.</td><td><a href="reporting/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-code" style="color:$primary;">:code:</i></h3></td><td><strong>API reference</strong></td><td>Endpoints, SDKs, and try-it.</td><td><a href="../../developers/payments-api/README.md">README.md</a></td></tr></tbody></table>

## What's new

The biggest recent shipments — see the full [changelog](../../changelog/README.md) for the back-catalog.

* **Smart routing v2** — per-network success-rate optimization, available on Growth and Enterprise. [Read more](accept-payments/smart-routing.md).
* **Same-day payouts** — opt-in for Enterprise customers in the US. [Read more](concepts/money-movement.md).
* **Disputes API** — programmatic evidence submission, replacing the legacy CSV upload. [Read more](reconciliation/disputes.md).

## Get help

{% columns %}
{% column width="50%" %}

### Talk to support

For account-specific questions, billing, or production incidents, contact your account team or open a ticket from the dashboard.

<p><a href="https://gitbook.com" class="button primary">Open a ticket</a></p>

{% endcolumn %}

{% column width="50%" %}

### Search the docs

Looking for something specific? The Assistant pulls answers from this site, the API reference, and the community forum.

<p><button type="button" class="button secondary" data-action="search" data-icon="magnifying-glass">Search...</button></p>

{% endcolumn %}
{% endcolumns %}
