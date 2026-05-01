---
icon: id-card
description: Verify customers and partners — documents, selfies, bank accounts, and business records.
cover: .gitbook/assets/identity-cover.png
coverY: 0
layout:
  width: wide
---

# Identity

Evolve Identity verifies the people and businesses you transact with — through document review, biometric selfie checks, bank account verification, and business records (KYB). It's the same platform as Payments, with the same dashboard, the same auth, and the same settlement of fees.

{% hint style="info" icon="gitbook" %}
**A note from GitBook**

This space demonstrates **nested page groups** — the Verification flows section has parent pages (Identity verification, Bank account verification, Business verification) each with their own subpages. It also includes a **hidden page**: [Watchlist screening](verification-flows/identity-verification/watchlist-screening.md) doesn't appear in the sidebar nav but is accessible via direct link. The same adaptive-content patterns from Payments apply here too — try `?persona=partner` to see Enterprise-specific content.
{% endhint %}

{% hint style="info" %}
**Looking for the API reference?** Endpoints, parameters, and SDK examples live in [Developers / Identity API](../../developers/identity-api/README.md). This space focuses on concepts and workflows.
{% endhint %}

<p><button type="button" class="button primary" data-action="ask" data-icon="gitbook-assistant">Ask the Evolve docs</button></p>

<p><button type="button" class="button secondary" data-action="ask" data-query="Which verification flow should I use?" data-icon="route">Which flow?</button> <button type="button" class="button secondary" data-action="ask" data-query="How long does verification take?" data-icon="clock">Timing</button> <button type="button" class="button secondary" data-action="ask" data-query="What documents are accepted in each country?" data-icon="passport">Documents</button> <button type="button" class="button secondary" data-action="ask" data-query="How do I screen against watchlists?" data-icon="shield-halved">Screening</button></p>

## Start here

{% if visitor.claims.unsigned.persona === "new" %}

{% hint style="info" icon="hand-wave" %}
**Not sure what verification you need?** Most teams start with **identity verification** (document + selfie) for individual customers, and add bank verification when they accept ACH. The [Verification flows overview](verification-flows/README.md) has a quick decision tree.
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}

{% hint style="info" icon="arrows-left-right" %}
**Coming from Stripe Identity?** Most flows map directly. Document + selfie is equivalent, watchlist screening replaces Stripe's network-block list, and bank verification works the same with Plaid. See the [Stripe migration guide](../../guides/tutorials/migrating-from-stripe.md#identity).
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "prospect" %}

{% hint style="info" icon="store" %}
**Selling on Shopify?** Shopify handles basic checkout fraud signals on its own — but if you take ACH, accept high-value orders, or sell age-restricted products, you'll want to layer Evolve Identity on top. See the [Shopify integration guide](../../guides/integrations/shopify.md#identity-checks).
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}

{% hint style="info" icon="building" %}
**Setting up enterprise compliance?** Watchlist screening, PEP screening, and ongoing monitoring are Enterprise-only features. The [Compliance section](compliance/audit-logs.md) covers audit trails and regional requirements.
{% endhint %}

{% endif %}

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-rocket" style="color:$primary;">:rocket:</i></h3></td><td><strong>Quickstart</strong></td><td>Run your first verification in five minutes.</td><td><a href="quickstart/run-your-first-verification.md">run-your-first-verification.md</a></td></tr><tr><td><h3><i class="fa-list-check" style="color:$primary;">:list-check:</i></h3></td><td><strong>Verification flows</strong></td><td>Identity, bank, and business verification — when to use which.</td><td><a href="verification-flows/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-scale-balanced" style="color:$primary;">:scale-balanced:</i></h3></td><td><strong>Compliance</strong></td><td>Audit logs, retention, regional requirements.</td><td><a href="compliance/audit-logs.md">audit-logs.md</a></td></tr><tr><td><h3><i class="fa-code" style="color:$primary;">:code:</i></h3></td><td><strong>API reference</strong></td><td>Endpoints, SDKs, and try-it.</td><td><a href="../../developers/identity-api/README.md">README.md</a></td></tr></tbody></table>

## What's new

* **Live document capture in 195 countries** — every country except the dozen on the OFAC blocklist. [Read more](verification-flows/identity-verification/document-review.md).
* **Selfie liveness 2.0** — passive liveness, no head turns required. Lifts completion rates by ~12%. [Read more](verification-flows/identity-verification/selfie-and-liveness.md).
* **Plaid instant for businesses** — same one-tap flow, now for business bank accounts. [Read more](verification-flows/bank-account/plaid-instant.md).

## Get help

{% columns %}
{% column width="50%" %}

### Talk to support

For account-specific questions, compliance reviews, or production incidents, contact your account team or open a ticket from the dashboard.

<p><a href="https://gitbook.com" class="button primary">Open a ticket</a></p>

{% endcolumn %}

{% column width="50%" %}

### Search the docs

Looking for something specific? The Assistant pulls answers from this site, the API reference, and the community forum.

<p><button type="button" class="button secondary" data-action="search" data-icon="magnifying-glass">Search...</button></p>

{% endcolumn %}
{% endcolumns %}
