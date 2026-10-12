---
name: commercial-base-audit
version: 1.0.0
description: "Use when a percentage in a commercial term is being set, questioned, or is producing a number nobody expected, such as sales commission, revenue share, affiliate or creator payouts, channel margin, agency or referral fees, or rebates. Finds what the percentage multiplies, identifies the condition under which two competing bases diverge, quantifies the gap per unit and at scale, and works backwards when a payout misses its model. Not for designing the pay plan (see gtm-compensation) or for approving a discount (see deal-desk-operations)."
---

# Commercial base audit

## Purpose

Percentages get negotiated loudly. Bases get agreed in a subordinate clause. The rate is what people argue about, but the base decides the money. This skill checks the base, states what it finds, and then returns to the question actually asked.

This is a check, not the answer. State the finding in a line or two, then answer the decision.

## When to use

- A commission, share, fee or payout does not match what the model predicted.
- A renegotiation is about to start on a percentage term.
- Someone asks whether a rate is fair, or what a promotion actually costs.

Route elsewhere when:
- The question is the pay plan itself. Use `gtm-compensation`.
- The question is approving a discount. Use `deal-desk-operations`.
- The question is the partner economics as a whole. Use `partner-channel-operations`.

## Inputs

- The clause or term, with its percentage and the noun it applies to.
- The payout actually made, by period, with the population and unit it covers.
- The model the payout was expected to follow, with its rate.
- Any tiers, caps, minimums, clawbacks or fixed fees in the term.
- The affected volume, where it is known: deals, orders, contracts or spend.

## Procedure

1. **Find the multiplicand.** Name the noun the percentage applies to: bookings, billings, recognised revenue or cash collected; list price or price paid; order total or product subtotal; gross or net spend; first-year, total or collected contract value. Read the clause. Do not assume an industry default.
2. **Test the definition.** A base is undefined unless the clause states where it sits relative to fees, tax and refunds. Where it is undefined, name both readings and price the gap. Where it is defined, confirm it in one sentence and move on.
3. **Find the divergence condition.** Name the event under which the competing bases differ, such as a discount, a refund, non-payment, early cancellation, a returned item or a change in platform fees. Compute both bases at that event.
4. **Quantify.** State the per-unit gap as a rate, for example each unit of discount costs one amount on one base and another on the other. Multiply by the affected volume where it is known. The scaled exposure decides whether the clause is worth reopening.
5. **Work backwards when the payout misses the model.** If the rate is unchanged and there are no tiers, caps or clawbacks, the base ratio is actual payout divided by modelled payout. The unexplained base is the gap between them divided by the rate. Use that magnitude as a filter across candidate components. First confirm that actual and model cover the same period, event, population and unit, because a lag or an accrual mismatch looks exactly like a base error.
6. **Do not name a cause from the ratio alone.** A total cannot separate an inflated base from a raised rate. Check the effective rate per line first.
7. **Frame the ask.** A base change can be easier to agree than a rate cut, because the headline percentage stays where it is. Where the two bases coincide on normal business, say so and quantify it. Where they differ on every transaction, present the change as a real transfer.

## Output

- The multiplicand, with a reference to the clause.
- Whether the base is defined, with both readings if it is not.
- The divergence condition and both bases at that condition.
- The per-unit gap as a rate, and the scaled exposure where volume is known.
- For a payout miss: the ratio, the unexplained magnitude, and the candidate components to check.
- The answer to the question asked, with this finding as one input.

## Quality bar

The base is named before the rate is judged. The figure is per unit and, where possible, at scale. Confident wording is not treated as a definition. A payout miss gives a magnitude to search for, not a named cause. Watch for an answer that audits the clause and never addresses the decision, a base change presented as a rate cut, and a standard base assumed without reading the clause.

## Rules

- Answer the question that was asked. The base audit is an input to the answer, not a replacement for it.
- Name the multiplicand before discussing whether the rate is fair.
- Treat a base as undefined unless the clause states its position on fees, tax and refunds.
- Never assume a standard base or infer what the parties presumably meant.
- Never present a base change as a rate cut.
- Where the base is unknown, model both readings and recommend neither.
