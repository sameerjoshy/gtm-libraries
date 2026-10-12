---
name: credit-based-packaging
version: 1.1.0
description: "Use when a product is moving to credits, or a credit-based enterprise deal needs structuring. Translates product actions into a simple credit schedule sized by value delivered rather than compute cost, designs tiers with allowances that feel generous, sets the rate card outside the contract so new capabilities do not reopen procurement, and explains credits to buyers in the value units they already use. Not for choosing the pricing model itself (see usage-pricing-model-selection) or for billing operations (see pricing-monetization-ops)."
---

# Credit based packaging

## Purpose

Credits let a vendor sell an outcome and meter a unit, but a poorly designed credit scheme recreates the bill shock it was meant to remove. This skill sets a credit schedule that a buyer can understand, keeps the rate card stable across accounts, and keeps the contract from needing a new negotiation every time the product gains a capability.

## When to use

- A product is moving from seats or subscriptions to credits.
- An enterprise deal needs a credit allowance and a rate card.
- Buyers do not understand what their credits buy.

Route elsewhere when:

- The question is which pricing model to use at all. Use `usage-pricing-model-selection`.
- The question is how credits are metered and invoiced. Use `pricing-monetization-ops`.

## Inputs

- The product's actions, and the value each one delivers to the buyer.
- Usage data by account, if it exists, or the expected usage per tier.
- The tiers and their prices, if they are set.
- The buyer's own units of value, such as tickets resolved, documents reviewed, or hours saved.

## Procedure

1. **Size each action by value delivered,** not by compute cost. Use a small set of sizes, such as small, medium, large and extra large. Keep the schedule simple. If every action needs a lookup, collapse the sizes.
2. **Choose the denomination for how it reads, not for the arithmetic.** A large number of credits reads as abundant. A small number reads as stingy. Scale the schedule so that a normal allowance looks generous.
3. **Design each tier's allowance** so that most customers in the tier stay within it. As author defaults: quote new customers at about seventy to eighty percent of their expected usage, and size each allowance for roughly eighty percent utilization. Growing into more credits is a conversation about expansion. Credits left unused are a warning of churn.
4. **Allow limited rollover.** Unlimited rollover erases the signal that the customer is ready to expand. Do not charge penalty prices for overage. Credit mechanics should make the buyer feel that they are getting value.
5. **Keep the rate card out of the contract.** Reference it from the contract instead. The rate card can then change as the product gains capabilities without reopening procurement.
6. **Lock the rate-card values** and keep them the same across accounts. When an enterprise buyer wants a lower effective rate, adjust the credit volume in a bundle, not the rate. Bespoke per-account rate cards destroy the trust that consistency builds.
7. **Explain credits in the buyer's terms.** Lead with the outcome, then translate it into a human equivalent, such as the number of reviews a role handles in a week. Show a monthly summary of credits used and the value delivered, from the buyer's own figures, not invented ones.

## Output

- The credit schedule, with each action's size and credit cost, and the reason for each size.
- The tier structure, with allowances and the utilization logic behind them.
- The rate-card terms for the contract, and the rule for changing the rate card.
- The buyer explanation: outcome, human equivalent, and the monthly summary.

## Quality bar

Credits are sized on value delivered. The rate card sits outside the contract and is the same for every account. Allowances let most customers stay in bounds. Watch for allowances so low that buyers hit the limit in the first month, denominations that make normal use feel expensive, and discounts applied to the rate card instead of bundled volume.
