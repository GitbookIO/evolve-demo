---
title: Test and live environments
---

Evolve has two fully separate environments. They share no data — keys, customers, charges, and webhooks all exist independently in each.

| Environment | API base URL | Dashboard | Key prefix |
| --- | --- | --- | --- |
| Test | `{{ space.vars.api_test }}` | `{{ space.vars.dashboard_test }}` | `sk_test_` / `pk_test_` |
| Live | `{{ space.vars.api_live }}` | `{{ space.vars.dashboard_live }}` | `sk_live_` / `pk_live_` |

Test mode accepts only test card numbers (see [Create a charge](../../accept-payments/create-a-charge.md#test-cards)). No money moves, and no webhooks fire to anything other than test endpoints.
