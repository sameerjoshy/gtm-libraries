---
name: usage-pricing-model-selection
version: 1.0.0
status: draft-for-review
description: Use to choose or defend a pricing model for a product that does work on the buyer's behalf, such as an automated agent, a workflow tool or an assistant. Compares four models (per agent or seat, per action, per workflow, per outcome) by the product's breadth, workload predictability, attribution, and the budget it displaces, recommends one or a hybrid, and sets price anchors against the cost of the work done another way rather than against compute. Not for billing operations (see pricing-monetisation-ops) or for credit schedules (see credit-based-packaging).
sources:
  - "AI pricing model picker (MIT, Manny Medina): profiling the product on breadth of responsibility, workload predictability, attribution and autonomy, and the budget displaced, the four-model comparison with its fit and risks, the rule of thumb for seat, outcome and hybrid models, anchoring on the cost of the work done another way rather than on compute, and the failure modes of token pricing, unmeasured outcomes, and seat pricing that shrinks with success"
  - "Removed: the named example companies and their prices, the market salary and outsourcing figures quoted in the source, and the named framework source. The model comparison is kept in general terms; no market figure is restated"
  - "Adapted for GTM-360: the rule that a recommendation must name the model chosen and why each other model loses is kept as a hard rule. The hybrid shape (subscription floor with a usage layer) is described as a common pattern, not a verified rate"
---

# Usage pricing model selection

## Purpose

A product that works on the buyer's behalf can be priced by seat, by use, by workflow, or by result. Each choice changes what the buyer compares the product with and how the vendor's revenue moves as the product improves. This skill picks the model from the product's facts and sets anchors the buyer can defend.

## When to use

- A team is deciding how to price an automated or assistant-style product.
- An existing price is fighting the product: customers resist seats for an agent that reduces seats, or usage bills surprise them.

Route elsewhere when:

- The question is how usage is metered and invoiced. Use `pricing-monetisation-ops`.
- The question is the credit schedule once a model is chosen. Use `credit-based-packaging`.

## Inputs

- What the product does, end to end, and which tasks it covers.
- Expected workload by month, and how much it varies.
- How a completed outcome is attributed to the product, and how autonomous it is: does it finish the work alone, or suggest actions for a person?
- The budget the product displaces: headcount, outsourced service spend, tool spend, or a performance line.

## Procedure

1. **Profile the product on four questions:**
   - Breadth: does it cover a whole job function, or discrete tasks?
   - Predictability: is the workload steady, or does it swing widely?
   - Attribution and autonomy: can a completed outcome be credited to the product? Does it finish work alone, or only suggest it?
   - Budget displaced: which budget line does it take from? The displaced budget moves the price more than any other input.
2. **Compare the four models:**

   | Model | Fits when | Main risk |
   |---|---|---|
   | Per agent or seat, a fixed fee | a whole function, steady workload, a headcount budget | little to separate it from a cheaper rival |
   | Per action, metered | varied discrete tasks, unpredictable frequency, an outsourcing budget | the strongest pressure to cut price |
   | Per workflow | multi-step sequences with a standard deliverable at each step | standard workflows invite price cuts; complex ones can lose margin |
   | Per outcome | high autonomy, clear attribution, a result the buyer already tracks | attribution disputes, and contracts that multiply |

3. **Choose the model, as a rule of thumb.** Low autonomy and loose attribution point to a seat or subscription. High autonomy and clear attribution point to outcome pricing. In between, use workflow pricing, or a hybrid: a subscription floor with a usage layer on top. The hybrid is a common shape, not a guarantee.
4. **Anchor on the cost of the work done another way.** Never anchor on compute or model cost, which falls over time and invites a race to zero. Anchor on what the buyer pays today for the same work, from their own figures. Express the price as a share of that cost, then check the margin against the product's worst-case cost to run.
5. **Structure the tiers.** Keep an entry tier that a champion can approve without a wider budget decision. If usage varies, add an allowance inside the subscription, sized so most customers stay within it, and use real usage data to decide the next step.
6. **For outcome pricing,** agree the metric and how it is measured before signing, not afterwards. Name who verifies it.
7. **State the recommendation,** the model chosen, and why each of the other three loses.

## Output

- The product profile on the four questions.
- The recommended model or hybrid, with the reason.
- Why each other model loses.
- The price anchor, expressed as a share of the displaced cost, with the margin check.
- The tier structure, and for outcome pricing the agreed metric and its verifier.

## Quality bar

The model is chosen from the product's facts, and the other three models have a stated reason for losing. Anchors come from the buyer's own cost of the work, not from compute. Outcome pricing names its metric and verifier. Watch for pricing by tokens, outcome pricing without measurement, and seat pricing for a product that reduces seats.
