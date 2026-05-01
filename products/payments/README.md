---
description: Route, reconcile, and report on every payment.
icon: credit-card
cover: .gitbook/assets/payments-cover.png
coverY: 0
layout:
  width: wide
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
---

# Payments

Evolve Payments handles the work between a customer's "pay" click and the money landing in your account — card and bank-rail processing, network routing, 3-D Secure, settlement, and reporting. This space covers everything from the first test charge to enterprise routing rules.

{% hint style="success" icon="gitbook" %}
**A note from GitBook**

This space is the deepest in the demo and shows off three GitBook features: **adaptive content** (hints and entire blocks change with the visitor), **space variables** (URLs and constants pulled from `vars.yaml`), and **synced blocks** (the test/live environments table is reused across all three product spaces).

{% if !visitor.claims.unsigned.persona %}
Try a persona to see adaptive content in action across the site:

<a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=new&#x26;visitor.plan=starter" class="button secondary" data-icon="seedling">New user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=existing&#x26;visitor.plan=growth" class="button secondary" data-icon="rocket">Migrator</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=partner&#x26;visitor.plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a>
{% endif %}

{% if visitor.claims.unsigned.persona %}
<i class="fa-id-card-clip" style="color:$info;">:id-card-clip:</i> You are currently <code class="expression">visitor.claims.unsigned.persona === "prospect" ? "a prospect user exploring the product" : visitor.claims.unsigned.persona === "new" ? "a new user" : visitor.claims.unsigned.persona === "existing" ? "an existing user" : visitor.claims.unsigned.persona === "partner" ? "a partner" : ""</code><code class="expression">visitor.claims.unsigned.plan ? ` on the ${visitor.claims.unsigned.plan.charAt(0).toUpperCase() + visitor.claims.unsigned.plan.slice(1)} plan` : ""</code>. [<mark style="color:$primary;">Reset</mark>](https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=)
{% endif %}

{% if visitor.claims.unsigned.persona === "prospect" %}
<a class="button primary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=new&#x26;visitor.plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=existing&#x26;visitor.plan=growth" class="button secondary" data-icon="rocket">Migrator</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=partner&#x26;visitor.plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a>
{% endif %}

{% if visitor.claims.unsigned.persona === "new" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a class="button primary" data-icon="arrow-right-to-bracket">New user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=existing&#x26;visitor.plan=growth" class="button secondary" data-icon="rocket">Migrator</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=partner&#x26;plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a>
{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=new&#x26;visitor.plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New user</a> <a class="button primary" data-icon="rocket">Migrator</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=partner&#x26;visitor.plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a>
{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=new&#x26;plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs/payments?visitor.persona=existing&#x26;visitor.plan=growth" class="button secondary" data-icon="rocket">Migrator</a> <a class="button primary" data-icon="handshake-angle">Partner</a>
{% endif %}
{% endhint %}

{% hint style="info" %}
**Looking for the API reference?** Endpoints, parameters, and SDK examples live in [Developers / Payments API](../../developers/payments-api/). This space focuses on concepts and workflows.
{% endhint %}

<button type="button" class="button primary" data-action="ask" data-icon="gitbook-assistant">Ask the Evolve docs</button>

<button type="button" class="button secondary" data-action="ask" data-query="How do I accept my first payment?" data-icon="rocket">First payment</button> <button type="button" class="button secondary" data-action="ask" data-query="What&#x27;s in a settlement file?" data-icon="file-csv">Settlement files</button> <button type="button" class="button secondary" data-action="ask" data-query="When do I need 3-D Secure?" data-icon="shield-halved">3-D Secure</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I route around card declines?" data-icon="route">Smart routing</button>

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
**Setting up enterprise features?** Smart routing, network selection, and failover are documented under [Accept payments](accept-payments/). For SSO, audit logs, and account hierarchy, see your account team or the [Enterprise admin guide](../../guides/tutorials/enterprise-admin-setup.md).
{% endhint %}
{% endif %}

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-rocket" style="color:$primary;">:rocket:</i></h4></td><td><strong>Quickstart</strong></td><td>Take your first test payment in five minutes.</td><td><a href="quickstart/accept-your-first-payment.md">accept-your-first-payment.md</a></td></tr><tr><td><h4><i class="fa-book-open" style="color:$primary;">:book-open:</i></h4></td><td><strong>Concepts</strong></td><td>How payments move through Evolve.</td><td><a href="concepts/payment-lifecycle.md">payment-lifecycle.md</a></td></tr><tr><td><h4><i class="fa-bolt" style="color:$primary;">:bolt:</i></h4></td><td><strong>Accept payments</strong></td><td>Charges, saved methods, 3-D Secure, routing.</td><td><a href="accept-payments/">accept-payments</a></td></tr><tr><td><h4><i class="fa-scale-balanced" style="color:$primary;">:scale-balanced:</i></h4></td><td><strong>Reconciliation</strong></td><td>Settlement files, refunds, disputes.</td><td><a href="reconciliation/">reconciliation</a></td></tr><tr><td><h4><i class="fa-chart-line" style="color:$primary;">:chart-line:</i></h4></td><td><strong>Reporting</strong></td><td>Daily reports, exports, and finance pushes.</td><td><a href="reporting/">reporting</a></td></tr><tr><td><h4><i class="fa-code" style="color:$primary;">:code:</i></h4></td><td><strong>API reference</strong></td><td>Endpoints, SDKs, and try-it.</td><td><a href="../../developers/payments-api/">payments-api</a></td></tr></tbody></table>

## What's new

The biggest recent shipments — see the full [changelog](../../changelog/) for the back-catalog.

* **Smart routing v2** — per-network success-rate optimization, available on Growth and Enterprise. [Read more](accept-payments/smart-routing.md).
* **Same-day payouts** — opt-in for Enterprise customers in the US. [Read more](concepts/money-movement.md).
* **Disputes API** — programmatic evidence submission, replacing the legacy CSV upload. [Read more](reconciliation/disputes.md).

## Get help

{% columns %}
{% column width="50%" %}
#### Talk to support

For account-specific questions, billing, or production incidents, contact your account team or open a ticket from the dashboard.

<a href="https://gitbook.com" class="button primary">Open a ticket</a>
{% endcolumn %}

{% column width="50%" %}
#### Search the docs

Looking for something specific? The Assistant pulls answers from this site, the API reference, and the community forum.

<button type="button" class="button secondary" data-action="search" data-icon="magnifying-glass">Search...</button>
{% endcolumn %}
{% endcolumns %}
