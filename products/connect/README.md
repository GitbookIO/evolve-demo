---
icon: circles-overlap
description: Embed payments in your platform — accept money on behalf of your sellers, take a cut, and pay them out.
cover: .gitbook/assets/connect-cover.png
coverY: 0
layout:
  width: wide
---

# Connect

Evolve Connect is the platform layer of Evolve Payments. If you operate a marketplace, a SaaS that takes payments on behalf of customers, or a vertical platform with embedded financial services, Connect handles the parts that get hard at the platform scale: onboarding sellers, splitting each payment between you and them, paying them out, and managing refunds and disputes across many accounts.

It's built on top of [Payments](../payments/README.md) — your platform uses the same API, the same dashboard, and the same settlement of fees. The Connect-specific concepts on top are <i class="fa-store" style="color:$primary;">:store:</i> connected accounts (your sellers), <i class="fa-percent" style="color:$primary;">:percent:</i> application fees (your cut), and <i class="fa-money-bill-transfer" style="color:$primary;">:money-bill-transfer:</i> transfers (moving funds to seller accounts).

{% hint style="success" icon="gitbook" %}
**A note from GitBook**

This space demonstrates **synced blocks reused from Payments** — the test/live environments table on [Test mode and live mode](quickstart/test-and-live-mode.md) is the same block used in the Payments and Identity spaces. It also leans on **inline icons** and **column blocks** for visual layout (see the "Where Connect fits" section below).
{% endhint %}

{% hint style="info" %}
**Looking for the API reference?** Endpoints, parameters, and SDK examples live in [Developers / Connect API](../../developers/connect-api/README.md). This space focuses on concepts and workflows.
{% endhint %}

## Start here

{% if visitor.claims.unsigned.persona === "new" %}

{% hint style="info" icon="hand-wave" %}
**New to Connect?** If you're not building a marketplace or platform that takes payments on behalf of others, you probably want plain [Payments](../payments/README.md) instead. The [Quickstart](quickstart/onboard-your-first-seller.md) below assumes you do — start there if so.
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "existing" %}

{% hint style="info" icon="arrows-left-right" %}
**Coming from Stripe Connect?** Most concepts map cleanly. Connected accounts, application fees, and transfers all work the same. Express, Standard, and Custom account types are unified into a single configurable account model — see [Onboarding sellers](platform-setup/onboarding-sellers.md).
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "prospect" %}

{% hint style="info" icon="store" %}
**Selling on Shopify?** You don't need Connect — Shopify is the platform here, not you. Connect is for *building* a platform like Shopify, not for selling on one. Stick with [Payments](../payments/README.md).
{% endhint %}

{% endif %}

{% if visitor.claims.unsigned.persona === "partner" %}

{% hint style="info" icon="building" %}
**Setting up enterprise platform features?** White-label embedded checkout, custom seller onboarding flows, and consolidated KYC/KYB across all sellers are the Enterprise-tier capabilities. See [Platform setup](platform-setup/README.md).
{% endhint %}

{% endif %}

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h3><i class="fa-rocket" style="color:$primary;">:rocket:</i></h3></td><td><strong>Quickstart</strong></td><td>Onboard your first seller in five minutes.</td><td><a href="quickstart/onboard-your-first-seller.md">onboard-your-first-seller.md</a></td></tr><tr><td><h3><i class="fa-window-maximize" style="color:$primary;">:window-maximize:</i></h3></td><td><strong>Embedded checkout</strong></td><td>The buyer-facing flow — hosted, embedded, or fully custom.</td><td><a href="embedded-checkout/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-sliders" style="color:$primary;">:sliders:</i></h3></td><td><strong>Platform setup</strong></td><td>Onboarding, splitting, payouts, and dispute handling.</td><td><a href="platform-setup/README.md">README.md</a></td></tr><tr><td><h3><i class="fa-code" style="color:$primary;">:code:</i></h3></td><td><strong>API reference</strong></td><td>Endpoints, SDKs, and try-it.</td><td><a href="../../developers/connect-api/README.md">README.md</a></td></tr></tbody></table>

## Where Connect fits

A typical Connect transaction touches three parties — the **buyer**, the **seller** (your customer), and **you** (the platform). Connect orchestrates the money so each one ends up with the right amount.

{% columns %}
{% column width="33%" %}

### <i class="fa-cart-shopping" style="color:$primary;">:cart-shopping:</i> Buyer

Pays once, sees one charge on their statement (yours or the seller's, your choice). Refunds and support flow back through your platform.

{% endcolumn %}

{% column width="33%" %}

### <i class="fa-store" style="color:$primary;">:store:</i> Seller

Onboarded once via your platform, then receives payouts on a schedule you set. Their identity, banking, and tax records are handled by [Identity](../identity/README.md).

{% endcolumn %}

{% column width="33%" %}

### <i class="fa-circles-overlap" style="color:$primary;">:circles-overlap:</i> Platform

Takes a percentage of each transaction as an application fee, plus optional flat fees. Sees consolidated reporting across all sellers in one dashboard.

{% endcolumn %}
{% endcolumns %}

## What Connect inherits from Payments

Connect is built on top of Payments — most of the concepts there apply unchanged. Worth a re-read if you haven't already:

* [Payment lifecycle](../payments/concepts/payment-lifecycle.md) — same states, same transitions.
* [Payment methods](../payments/concepts/payment-methods.md) — same supported rails.
* [Money movement](../payments/concepts/money-movement.md) — same settlement cadence; Connect adds per-seller payouts on top.
* [Settlement files](../payments/reconciliation/settlement-files.md) — Connect's settlement file groups by seller.

## Plan availability

{% if visitor.claims.unsigned.plan === "starter" %}

{% hint style="warning" icon="lock" %}
**Connect is a Growth and Enterprise feature.** Starter accounts can take payments for themselves but can't onboard third-party sellers. [Talk to your account team](mailto:support@evolve.com) when you're ready to upgrade.
{% endhint %}

{% endif %}

| | Growth | Enterprise |
| --- | :---: | :---: |
| Connected accounts | Up to 100 | Unlimited |
| Hosted checkout | ✅ | ✅ |
| Embedded checkout (Evolve UI in your site) | — | ✅ |
| White-label embedded UI | — | ✅ |
| Custom onboarding flows | — | ✅ |
| Consolidated KYC across sellers | — | ✅ |
| Per-seller dispute routing | ✅ | ✅ |

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
