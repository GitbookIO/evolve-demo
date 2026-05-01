---
description: >-
  Payments, identity, and platform infrastructure — built for businesses that
  scale.
icon: house
cover: .gitbook/assets/home-cover.png
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
    visible: false
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
---

# Welcome to Evolve

Take payments, verify customers, and run a marketplace — all on one platform. Evolve is the financial infrastructure for modern businesses, used by thousands of teams from early-stage startups to global enterprises.

## Ask anything

<button type="button" class="button primary" data-action="ask" data-icon="gitbook-assistant">Ask the Evolve docs</button>

<button type="button" class="button secondary" data-action="ask" data-query="How do I take my first payment?" data-icon="rocket">First payment</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I verify a customer&#x27;s identity?" data-icon="id-card">Verification</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I onboard sellers on a marketplace?" data-icon="circles-overlap">Marketplace</button> <button type="button" class="button secondary" data-action="ask" data-query="How is Evolve different from Stripe?" data-icon="arrows-left-right">vs Stripe</button>



***



## Start where you are

{% hint style="success" icon="gitbook" %}
**A note from GitBook**

This site is a demo of GitBook's enterprise features applied to a fictional fintech, **Evolve**. It shows what a real customer-facing docs site looks like end-to-end — adaptive content, OpenAPI variants, the AI Assistant with Connections, change-request workflows, hidden pages with public/authenticated flips, and more.

{% if !visitor.claims.unsigned.persona %}
Try a persona to see adaptive content in action across the site:

<a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=new&#x26;plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New sign-up</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=existing&#x26;plan=growth" class="button secondary" data-icon="user">Existing user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=partner&#x26;plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a> <a class="button secondary" data-icon="trash-can"></a>
{% endif %}

{% if visitor.claims.unsigned.persona === "prospect" %}
<a class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=new&#x26;plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New sign-up</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=existing&#x26;plan=growth" class="button secondary" data-icon="user">Existing user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=partner&#x26;plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=" class="button secondary" data-icon="trash-can"></a>
{% endif %}

{% if visitor.claims.unsigned.persona === "new" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a class="button secondary" data-icon="arrow-right-to-bracket">New sign-up</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=existing&#x26;plan=growth" class="button secondary" data-icon="user">Existing user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=partner&#x26;plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=" class="button secondary" data-icon="trash-can"></a>
{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=new&#x26;plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New sign-up</a> <a class="button secondary" data-icon="user">Existing user</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=partner&#x26;plan=enterprise" class="button secondary" data-icon="handshake-angle">Partner</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=" class="button secondary" data-icon="trash-can"></a>
{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}
<a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=prospect" class="button secondary" data-icon="bag-shopping">Prospect</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=new&#x26;plan=starter" class="button secondary" data-icon="arrow-right-to-bracket">New sign-up</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=existing&#x26;plan=growth" class="button secondary" data-icon="user">Existing user</a> <a class="button secondary" data-icon="handshake-angle">Partner</a> <a href="https://enterprise-demos.gitbook.io/evolve-docs?visitor.persona=" class="button secondary" data-icon="trash-can"></a>
{% endif %}

{% if visitor.claims.unsigned.persona %}
<i class="fa-circle-info" style="color:$info;">:circle-info:</i> <mark style="color:$info;">You are currently</mark> <code class="expression">visitor.claims.unsigned.persona === "prospect" ? "a prospect" : visitor.claims.unsigned.persona === "new" ? "a new user" : visitor.claims.unsigned.persona === "existing" ? "an existing user" : visitor.claims.unsigned.persona === "partner" ? "a partner" : ""</code> <mark style="color:$info;">on the</mark> <code class="expression">visitor.claims.unsigned.plan.charAt(0).toUpperCase() + visitor.claims.unsigned.plan.slice(1)</code> <mark style="color:$info;">plan.</mark>
{% endif %}
{% endhint %}

{% if visitor.claims.unsigned.persona === "prospect" %}
{% hint style="info" icon="store" %}
**Evaluating Evolve?** The [Help Center](../guides/help-center/) answers the questions most prospects ask — pricing, going live, supported countries. For a deeper look, the [Payments product space](../products/payments/) covers the full feature set without the API noise.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.persona === "new" %}
{% hint style="info" icon="hand-wave" %}
**Welcome to Evolve.** If you've just signed up, the [Payments quickstart](../products/payments/quickstart/accept-your-first-payment.md) gets you to a real test charge in five minutes — no code required. From there, the [tutorials](../guides/tutorials/) cover the most-asked-about workflows.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}
{% hint style="info" icon="arrows-left-right" %}
**Migrating from Stripe?** Most concepts map cleanly. Start with the [Stripe migration tutorial](../guides/tutorials/payment-flows/migrate-from-stripe.md) — it covers field mapping, the parallel-run pattern, and the cutover checklist. Most teams complete migration in 2–6 weeks.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}
{% hint style="info" icon="handshake" %}
**Welcome back.** The [partner portal](../partners/) has your deal-registration form, marketing assets, and direct line to your partner success manager. New product updates that affect partners go to the [changelog](../changelog/) tagged `platform`.
{% endhint %}
{% endif %}

## Three products, one platform

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-credit-card" style="color:$primary;">:credit-card:</i></h4></td><td><strong>Payments</strong></td><td>Accept card and bank-rail payments. Smart routing, 3-D Secure, settlement, reporting.</td><td><a href="../products/payments/">payments</a></td></tr><tr><td><h4><i class="fa-id-card" style="color:$primary;">:id-card:</i></h4></td><td><strong>Identity</strong></td><td>Verify customers and businesses. Document review, selfie liveness, bank verification, KYB.</td><td><a href="../products/identity/">identity</a></td></tr><tr><td><h4><i class="fa-circles-overlap" style="color:$primary;">:circles-overlap:</i></h4></td><td><strong>Connect</strong></td><td>Embed payments in your platform. Onboard sellers, split payments, run a marketplace.</td><td><a href="../products/connect/">connect</a></td></tr></tbody></table>

## For developers

API references, SDKs, and the agent integrations across all three products. Pick where to dive in:

{% columns %}
{% column width="25%" %}
#### <i class="fa-rocket" style="color:$primary;">:rocket:</i> Quickstart

Make your first API call in five minutes.

[Quickstart →](../developers/v2/getting-started/quickstart.md)
{% endcolumn %}

{% column width="25%" %}
#### <i class="fa-key" style="color:$primary;">:key:</i> Authentication

Keys, restricted scopes, signature verification.

[Authentication →](../developers/v2/getting-started/authentication.md)
{% endcolumn %}

{% column width="25%" %}
#### <i class="fa-cubes" style="color:$primary;">:cubes:</i> SDKs

Node, Python, Go, Ruby — official and idiomatic.

[SDKs →](../developers/v2/getting-started/sdks.md)
{% endcolumn %}

{% column width="25%" %}
#### <i class="fa-robot" style="color:$primary;">:robot:</i> AI agents

llms.txt, MCP server, agent best practices.

[For AI agents →](../developers/v2/getting-started/for-ai-agents.md)
{% endcolumn %}
{% endcolumns %}

## Learn and explore

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-graduation-cap" style="color:$primary;">:graduation-cap:</i></h4></td><td><strong>Tutorials</strong></td><td>Step-by-step builds for common workflows. 15 tutorials with video walkthroughs.</td><td><a href="../guides/tutorials/">tutorials</a></td></tr><tr><td><h4><i class="fa-life-ring" style="color:$primary;">:life-ring:</i></h4></td><td><strong>Help Center</strong></td><td>Focused answers to common questions. The Assistant pulls from here, the forum, and YouTube.</td><td><a href="../guides/help-center/">help-center</a></td></tr><tr><td><h4><i class="fa-puzzle-piece" style="color:$primary;">:puzzle-piece:</i></h4></td><td><strong>Integrations</strong></td><td>Slack, Zapier, Segment, QuickBooks, NetSuite — and more in active development.</td><td><a href="../guides/integrations/">integrations</a></td></tr><tr><td><h4><i class="fa-clock-rotate-left" style="color:$primary;">:clock-rotate-left:</i></h4></td><td><strong>Changelog</strong></td><td>Six months of product updates, filterable by Payments, Identity, Connect, or Platform.</td><td><a href="../changelog/">changelog</a></td></tr></tbody></table>

## What's new

The biggest recent shipments — see the full [changelog](../changelog/) for the back-catalog.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-route" style="color:$primary;">:route:</i></h4></td><td><strong>Smart routing v2</strong></td><td>Per-network success-rate optimization. 1–3% lift in approval rate, no code changes.</td><td><a href="../products/payments/accept-payments/smart-routing.md">smart-routing.md</a></td></tr><tr><td><h4><i class="fa-flask" style="color:$primary;">:flask:</i></h4></td><td><strong>Payments API v3-beta</strong></td><td>Renamed Payment object, capture_method enum, 30-day auth, multi-currency capture.</td><td><a href="../developers/v2/payments-api/">payments-api</a></td></tr><tr><td><h4><i class="fa-face-smile" style="color:$primary;">:face-smile:</i></h4></td><td><strong>Selfie liveness 2.0</strong></td><td>Passive liveness — no head turns. Lifts completion rates by ~12%.</td><td><a href="../products/identity/verification-flows/identity-verification/selfie-and-liveness.md">selfie-and-liveness.md</a></td></tr></tbody></table>

## Partner with us

{% columns %}
{% column width="50%" %}
#### <i class="fa-handshake" style="color:$primary;">:handshake:</i> Become a partner

Solution, implementation, and technology partners earn revenue share, get co-marketing support, and a direct line to your partner success manager.

<a href="https://gitbook.com" class="button primary">Apply to the program</a> <a href="../partners/" class="button secondary">Learn more</a>
{% endcolumn %}

{% column width="50%" %}
#### <i class="fa-key" style="color:$primary;">:key:</i> Already a partner?

Sign in to the partner portal for deal registration, marketing resources, training, and support.

<a href="https://gitbook.com" class="button primary">Sign in</a> <a href="../partners/" class="button secondary">Open the portal</a>
{% endcolumn %}
{% endcolumns %}

## Get help

{% columns %}
{% column width="33%" %}
#### <i class="fa-headset" style="color:$primary;">:headset:</i> Talk to support

For account-specific questions, integration help, or production incidents, open a ticket from your dashboard.

<a href="https://gitbook.com" class="button primary">Open a ticket</a>
{% endcolumn %}

{% column width="33%" %}
#### <i class="fa-circle-check" style="color:$primary;">:circle-check:</i> Platform status

Real-time status of every Evolve service. Subscribe via email or RSS for incident updates.

<a href="https://gitbook.com" class="button secondary">View status</a>
{% endcolumn %}

{% column width="33%" %}
#### <i class="fa-comments" style="color:$primary;">:comments:</i> Community

Real-time discussion with other Evolve customers and our team. Most product questions have a thread.

<a href="https://gitbook.com" class="button secondary">Join the forum</a>
{% endcolumn %}
{% endcolumns %}
