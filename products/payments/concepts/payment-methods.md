---
description: >-
  Which payment methods Evolve supports, and which ones are available on your
  plan.
icon: wallet
---

# Payment methods

Evolve supports cards, bank transfers, and direct debits. Your available methods depend on your plan and settlement currency.

## Methods by plan

{% if visitor.claims.unsigned.plan === "starter" %}
{% hint style="info" icon="layer-group" %}
**Starter plan.** Accept card payments in USD. Upgrade to [Growth](https://gitbook.com) to accept ACH, debit, or international payment methods.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.plan === "growth" %}
{% hint style="info" icon="layer-group" %}
**Growth plan.** Accept cards, ACH, and debit. Wire transfers, SEPA, and BACS require Enterprise. Contact your account team to enable them.
{% endhint %}
{% endif %}

{% if visitor.claims.unsigned.plan === "enterprise" %}
{% hint style="success" icon="layer-group" %}
**Enterprise plan.** All listed methods are available, including international payment methods. Multi-currency settlement is enabled by default.
{% endhint %}
{% endif %}

<table><thead><tr><th>Method</th><th data-type="checkbox">Starter</th><th data-type="checkbox">Growth</th><th data-type="checkbox">Enterprise</th><th>Settlement</th></tr></thead><tbody><tr><td>Card (Visa, Mastercard, Amex, Discover)</td><td>true</td><td>true</td><td>true</td><td>T+1–3</td></tr><tr><td>Card (JCB, UnionPay, Diners)</td><td>false</td><td>true</td><td>true</td><td>T+2–3</td></tr><tr><td>ACH debit (US)</td><td>false</td><td>true</td><td>true</td><td>T+3 (initial), T+1 (verified)</td></tr><tr><td>Debit card (US)</td><td>true</td><td>true</td><td>true</td><td>T+1–2</td></tr><tr><td>Wire transfer (US)</td><td>false</td><td>false</td><td>true</td><td>Same day</td></tr><tr><td>SEPA (EU)</td><td>false</td><td>false</td><td>true</td><td>T+1</td></tr><tr><td>BACS Direct Debit (UK)</td><td>false</td><td>false</td><td>true</td><td>T+3</td></tr><tr><td>Multi-currency (USD, CAD, GBP, EUR)</td><td>false</td><td>true</td><td>true</td><td>Per-currency payout</td></tr><tr><td>Multi-currency (135 currencies)</td><td>false</td><td>false</td><td>true</td><td>Per-currency payout</td></tr></tbody></table>

## Choose payment methods

Choose the methods available for each payment. In the dashboard, **Settings → Payment methods** sets defaults for new payment links and Checkout sessions.

Override those defaults for an individual session. For example, offer only wire transfers for a B2B invoice.

## Consider risk

Each payment method has a different risk profile.

<details>

<summary>Cards</summary>

Cards usually have the highest authorization rate. They also have the greatest dispute exposure. Chargebacks can arrive up to 120 days after payment.

Use [3-D Secure](../accept-payments/3d-secure.md) for high-value transactions to shift liability.

</details>

<details>

<summary>ACH debit</summary>

ACH debit has lower fees. However, consumer-account payments can be reversed for up to 60 days.

Verify accounts before large charges. Evolve supports instant verification through Plaid. See [Identity / Bank verification](https://app.gitbook.com/s/w7NRnYZuokE4h1mm2pJB/verification-flows/bank-account).

</details>

<details>

<summary>Wire transfer</summary>

Wire transfers are final on the same day and cannot be reversed. They work well for high-value B2B payments.

Customers send funds to a unique virtual account number. Evolve matches each transfer to its charge using the reference code.

</details>

## Related

* [Money movement and settlement](money-movement.md) — learn when funds from each method arrive.
* [3-D Secure and SCA](../accept-payments/3d-secure.md) — learn when cardholder authentication is required.
* [Identity / Bank verification](https://app.gitbook.com/s/w7NRnYZuokE4h1mm2pJB/verification-flows/bank-account) — verify ACH accounts before you debit them.
