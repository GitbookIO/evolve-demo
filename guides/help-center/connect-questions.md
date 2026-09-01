---
icon: circles-overlap
description: Connected accounts, splits, payouts, marketplace patterns — the most-asked Connect questions.
---

# Connect questions

## Do I need Connect?

Yes if you take payments **on behalf of others** — marketplaces, B2B platforms paying out to vendors, SaaS apps that route money to customers. No if you only take payments **for yourself** (typical e-commerce, SaaS billing, donations).

If you're not sure: ask "does the money belong to me, or to someone using my product?" If the latter, that's Connect.

## What plan do I need for Connect?

Growth or Enterprise. Starter doesn't include Connect.

| | Growth | Enterprise |
| --- | --- | --- |
| Connected accounts | Up to 100 | Unlimited |
| Hosted onboarding | ✅ | ✅ |
| Embedded checkout | — | ✅ |
| Custom (white-label) onboarding | — | ✅ |
| Per-seller dispute routing | ✅ | ✅ |

For the full per-tier breakdown, see [Connect → Plan availability](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/#plan-availability).

## How do I onboard a seller?

Three integration shapes, in order of how much control they give you:

* **Hosted** — Evolve generates an onboarding URL, you email it to the seller. Fastest to launch, and updates automatically as KYC requirements change. Most platforms start here. The walkthrough is in the [Onboard your first sellers tutorial](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/marketplace/onboard-sellers).
* **Embedded** — the same fields, rendered inside your own site instead of an Evolve-hosted page. Same data requirements as hosted, different wrapper.
* **Custom (programmatic)** — Enterprise-only. You build your own forms; data is submitted directly to Evolve's API. See [Build a custom Connect onboarding flow](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/marketplace/custom-onboarding).

Most teams should use hosted unless brand standards or specific UX requirements demand embedded or custom — you're responsible for keeping a custom flow current as KYC requirements change, which hosted and embedded handle for you.

{% hint style="info" %}
Every connected account needs legal identity info (name, DOB or formation date, government ID, address — plus beneficial ownership ≥25% for businesses) and banking info (payout account, verified via Plaid or micro-deposits). Non-US banks also need a tax form (W-9 or W-8). Most US individuals complete the whole flow in under 10 minutes; international businesses can take days. Full breakdown: [Onboarding sellers](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/platform-setup/onboarding-sellers).
{% endhint %}

Pre-fill whatever your own sign-up flow already collected (name, email, address) at session creation — it saves the seller re-typing it, and they can still edit the values.

## What happens if a seller fails onboarding?

Most failures are recoverable, not permanent rejections:

* **Identity verification fails** — expired document, tampering signal, or selfie mismatch. The seller can retry up to 3 times in 24 hours; after that, your team can manually review from the dashboard.
* **Bank verification fails** — Plaid couldn't reach the bank, or micro-deposit amounts were entered wrong. The flow automatically falls back to the other method.
* **Sanctions match** — rare, and serious. The seller can't be onboarded until your compliance team reviews the match details in the dashboard.
* **Tax form mismatch** — the name on the tax form doesn't match the legal entity name, usually a typo. The seller re-uploads.

Sellers' info also isn't static — bank changes re-verify automatically, address changes beyond a small threshold trigger re-verification, and beneficial-owner changes require re-verifying the new owners. A "Profile changed" badge shows on the seller until that clears, and you can hold their payouts during the change if your risk policy requires it.

## Why is my seller's account `restricted`?

Risk team has flagged something. The seller's record in **Connect → Connected accounts → [account] → Status** shows the specific reason. Common ones:

* High dispute rate (above 1%)
* Sudden volume spike that triggers fraud screening
* Sanctions match found during ongoing monitoring
* Manual review pending after a flagged transaction

Restricted accounts can't take new charges; existing balances pay out normally. Contact your account team to discuss next steps for the specific seller.

## How do I take my platform fee on each payment?

Set `application_fee_amount` when creating the Checkout session:

```http
POST /v2/checkout_sessions
{
  "amount": 10000,
  "currency": "usd",
  "connected_account": "acct_3KsM12pL9q",
  "application_fee_amount": 200
}
```

That's $100 to the buyer, $98 transferred to the seller, $2 to your platform. A split can carry up to three line items — an application fee (% of gross), a flat fee, and the processing fee itself — and you can layer conditional rules on top: by seller tier, product category, transaction size, currency, or even a time-boxed promo. You build those rules in your own code at session-creation time; Evolve doesn't have a built-in rules engine since the right logic is specific to your business model. The [split-payments tutorial](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/marketplace/split-payments) walks through it, and [Splitting payments](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/platform-setup/splitting-payments) has the full reference including the pass-through-fee math.

## How are processing fees split between platform and seller?

By default, the card processing fee (2.9% + $0.30) comes off the platform's application fee. Pass `application_fee_includes_processing: false` to make the seller absorb it instead:

| | Processing comes off platform (default) | Processing comes off seller |
| --- | --- | --- |
| Buyer pays | $100.00 | $100.00 |
| Seller gets | $95.00 | $92.10 |
| Platform nets | $2.10 | $5.00 |

(Assuming a 5% application fee.) Most marketplaces with thin take-rates pass through to sellers. Most marketplaces competing on seller experience absorb it. Pick once at the platform level and keep it consistent.

## Can a seller have a custom payout schedule?

Yes. The platform sets the default in **Connect → Settings → Default payout schedule**, and sellers can override their own (within the schedules you allow) from their seller portal.

| Schedule | When sellers get paid | Best for |
| --- | --- | --- |
| Daily | T+1 (next business day after capture) | Marketplaces, food delivery — anywhere seller cash flow matters |
| Weekly | Every Monday for the prior week | Subscription platforms, B2B SaaS |
| Monthly | 1st of the month for the prior month | Long-tail marketplaces, royalty payouts |
| Manual | Whenever you trigger it | Platforms with custom scheduling logic |

For on-demand payouts (seller taps "Pay me now" for instant cash), enable in **Connect → Settings → Instant payouts**. The 1% fee can be paid by seller, platform, or split, and lands within minutes over RTP/FedNow or within hours otherwise. Available on Enterprise. See the [payout-schedules tutorial](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/marketplace/payout-schedules).

{% hint style="info" %}
Many platforms also hold back a **rolling reserve** — typically 5–10% of a seller's balance for 90 days, common for new sellers or high-dispute-exposure marketplaces. The oldest slice rolls off and becomes payable each day; refunds and disputes during the window are drawn from the reserve first. Configure in **Connect → Settings → Reserves** (Enterprise supports per-seller custom rules).
{% endhint %}

## How do refunds work on a Connect payment?

Like a regular refund, plus one extra decision: how it's split between platform and seller.

* **Default (proportional)** — a refund mirrors the original split. A $100 payment with a $5 application fee, refunded in full, pulls -$5 from the platform and -$95 from the seller. A partial $25 refund pulls -$1.25 platform / -$23.75 seller.
* **Seller absorbs the fee** — pass `refund_application_fee: false` so the seller's balance covers the full refund amount and keeps the platform's fee intact. Typical when the seller caused the issue (defective product, late shipment).
* **Platform absorbs everything** — a goodwill refund funded entirely from the platform's own balance; the seller isn't touched.

By default either the platform or the seller can issue a refund (first to act wins) — restrict this to **platform-only** or **seller-only** in **Connect → Settings → Refund permissions**. Full mechanics: [Refunds and disputes](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/platform-setup/refunds-and-disputes).

## What happens to disputes on a Connect platform?

The **platform is the merchant of record** — disputes are filed against the platform's merchant ID, and the platform's overall dispute rate (monitored against a ~1.0% network threshold) is the sum across every seller's charges. A handful of bad-actor sellers can drag the whole platform's rate down, which is why per-seller dispute monitoring matters.

Three policies for who absorbs the disputed amount + $15 fee:

* **Pass to seller** — most common.
* **Platform absorbs** — for premium-tier sellers as a perk.
* **Split** — platform takes the fee, seller takes the disputed amount.

Set the default in **Connect → Settings → Dispute policy**, override per-seller. The full clock from dispute opened to outcome typically runs 30–75 days, with the disputed funds withheld from whichever balance is responsible during that window. For evidence collection, most platforms delegate to the seller (they have the shipping/product records) — see the [disputes-at-scale tutorial](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/marketplace/disputes-at-scale) and [Refunds and disputes](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/platform-setup/refunds-and-disputes) for the full playbook, including why making refunds easy for buyers is the single best lever for keeping your dispute rate down — a buyer who can't get a refund through you goes to their bank instead, and a bank chargeback costs $15 and dings your dispute rate where a platform refund costs neither.

## Why is a seller's payout `failed`?

Bank account became invalid — closed, frozen, name mismatch, or wrong details. The dashboard shows the bank's reason code. The amount returns to the seller's balance; they update the bank account in their portal and the next scheduled payout includes the failed amount.

Three failed payouts in a row auto-pause the seller until you intervene. See the [community thread on stuck Connect payouts](https://gitbookio.github.io/evolve-demo/connections/community/connect-payout-stuck.html) for the typical playbook.

{% hint style="warning" %}
A failed payout is different from a **held** payout. Holds happen for a risk flag (up to 14 days), a manual platform hold, or a pending compliance re-verification (1–2 days) — the seller keeps taking charges normally in all three cases, only the transfer to their bank pauses. A failed payout, by contrast, means the scheduled transfer itself couldn't land.
{% endhint %}

## Can I have a seller in a country my platform doesn't operate in?

Sometimes — depends on the country pair. Some platform/seller country combinations have regulatory or banking restrictions. Talk to your account team before promising a new seller country to your operators.

For platforms operating in multiple countries themselves, you can configure per-region defaults (different fee structure, different payout schedule) in **Connect → Settings → Per-region**.

## What's the difference between direct charges and destination charges?

| | Direct charge | Destination charge |
| --- | --- | --- |
| Merchant of record | Seller | Platform |
| How you set it | `Evolve-Account: acct_*` header on the charge | Default; a separate transfer moves funds to the seller after the charge |
| Buyer's statement descriptor | Seller's | Platform's |
| Dispute responsibility | Less clear-cut | Clearer — platform is already the merchant of record |

Most Connect platforms use destination charges — buyers see a consistent platform brand, and dispute responsibility is unambiguous. Pick once at the platform level in **Connect → Settings → Charge type**.

## How do I test Connect before going live?

Test mode is a fully separate environment — test connected accounts, onboarding, and payouts don't carry over to live. Sellers onboard once in test (for your integration work) and again for real once you flip to live.

{% hint style="warning" %}
Don't run test and live onboarding in parallel during cutover. Sellers who complete test onboarding and assume they're live will be confused when they don't get paid — turn off test-mode self-serve onboarding before announcing live mode is open.
{% endhint %}

Before flipping production, most platforms: run one real payment end-to-end through a real seller (onboard them, take a $1 live charge with a real card, confirm the transfer lands, then refund it), confirm seller-facing emails point at live URLs (not `dashboard.test.evolve.com`), and lock down who owns the live dispute queue. Full checklist and the steps to flip keys/webhooks: [Test mode and live mode](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/quickstart/test-and-live-mode).

## Where can I find more answers?

* [Community: Stuck Connect payouts](https://gitbookio.github.io/evolve-demo/connections/community/connect-payout-stuck.html)
* [YouTube: Chargebacks at scale](https://gitbookio.github.io/evolve-demo/connections/youtube/chargebacks-at-scale.html)
* [Connect product space](https://app.gitbook.com/s/Xtfxb7OHGyrdfIsObmnu/)
* [Tutorials: Run a marketplace with Connect](https://app.gitbook.com/s/Nankrp40VchJsUblU6h6/#run-a-marketplace-with-connect)
