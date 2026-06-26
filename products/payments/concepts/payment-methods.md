---
description: >-
  Which payment methods Evolve supports, and which ones are available on your
  plan.
icon: wallet
---

# Payment methods

Evolve supports cards, bank rails, and direct-debit schemes. The methods available to you depend on your plan and on the destination currency.

## Methods by plan

{% if visitor.claims.unsigned.plan === "starter" %}
{% hint style="info" icon="layer-group" %}
**You're on Starter.** Card payments only, in USD. To accept ACH, debit, or international rails, [upgrade to Growth](https://gitbook.com).
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.plan === "growth" %}
{% hint style="info" icon="layer-group" %}
**You're on Growth.** Cards, ACH, and debit are enabled. Wires, SEPA, and BACS are Enterprise features — talk to your account team if you need them.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.plan === "enterprise" %}
{% hint style="success" icon="layer-group" %}
**You're on Enterprise.** All methods listed below are enabled, including international rails. Multi-currency settlement is on by default.
{% endhint %}
{% endif %}

<table><thead><tr><th>Method</th><th data-type="checkbox">Starter</th><th data-type="checkbox">Growth</th><th data-type="checkbox">Enterprise</th><th>Settlement</th></tr></thead><tbody><tr><td>Card (Visa, Mastercard, Amex, Discover)</td><td>true</td><td>true</td><td>true</td><td>T+1–3</td></tr><tr><td>Card (JCB, UnionPay, Diners)</td><td>false</td><td>true</td><td>true</td><td>T+2–3</td></tr><tr><td>ACH debit (US)</td><td>false</td><td>true</td><td>true</td><td>T+3 (initial), T+1 (verified)</td></tr><tr><td>Debit card (US)</td><td>true</td><td>true</td><td>true</td><td>T+1–2</td></tr><tr><td>Wire transfer (US)</td><td>false</td><td>false</td><td>true</td><td>Same day</td></tr><tr><td>SEPA (EU)</td><td>false</td><td>false</td><td>true</td><td>T+1</td></tr><tr><td>BACS Direct Debit (UK)</td><td>false</td><td>false</td><td>true</td><td>T+3</td></tr><tr><td>Multi-currency (USD, CAD, GBP, EUR)</td><td>false</td><td>true</td><td>true</td><td>Per-currency payout</td></tr><tr><td>Multi-currency (135 currencies)</td><td>false</td><td>false</td><td>true</td><td>Per-currency payout</td></tr></tbody></table>

## Choosing which methods to offer

You decide which methods to offer on each payment. In the dashboard, **Settings → Payment methods** sets the default set for new payment links and Checkout sessions. You can override per session — for example, if you want a B2B invoice to accept wire only.

## Risk considerations

Different methods carry different risk profiles:

<details>

<summary>Cards</summary>

Highest authorization rate, highest dispute exposure. Chargebacks can land up to 120 days after the charge. Use [3-D Secure](../accept-payments/3d-secure.md) on high-value transactions to shift liability.

</details>

<details>

<summary>ACH debit</summary>

Lower fees, but reversal risk lasts 60 days for consumer accounts. Verify the account before charging large amounts — Evolve supports instant verification via Plaid (see [Identity / Bank verification](https://app.gitbook.com/s/w7NRnYZuokE4h1mm2pJB/verification-flows/bank-account)).

</details>

<details>

<summary>Wire transfer</summary>

Same-day finality, no reversals. Best for high-value B2B. Customer pushes funds to a unique virtual account number; Evolve matches them to your charge by reference code.

</details>

## Related

* [Money movement and settlement](money-movement.md) — when each method's funds arrive in your account.
* [3-D Secure and SCA](../accept-payments/3d-secure.md) — when to require additional cardholder authentication.
* [Identity / Bank verification](https://app.gitbook.com/s/w7NRnYZuokE4h1mm2pJB/verification-flows/bank-account) — verifying ACH accounts before debit.
