---
name: move-gtm-diagnostic
version: 1.0.0
status: draft-for-review
description: Use to audit a go-to-market foundation before scaling or automating it. Works through four questions (Market, Operations, Velocity, Expansion), places the company in one of three fit stages (problem-market, product-market, platform-market), and returns a prioritised list of what to fix first. Use when a company wants a GTM health check, when growth has stalled, or before standing up a new outbound, inbound, or deal engine. This is a diagnosis, not a build. Not for a single channel plan (see demand-lifecycle-model).
sources:
  - "MOVE GTM diagnostic (MIT, Sangram Vajre): the four-question diagnostic (Market, Operations, Velocity, Expansion), the three fit stages with their focus, motion, and growth pattern, the principle that a company cannot scale problem-market fit, and the rule to diagnose before building"
  - "Removed: the revenue thresholds attributed to the source's framework as stage boundaries, and the book references. The stage bands here are the company's own signals, to be checked against its data"
  - "Adapted for GTM-360: the stage classification uses the company's own revenue trajectory, team structure, and retention as evidence; no outside revenue cut-offs are applied"
---

# MOVE GTM diagnostic

## Purpose

Most GTM failures are not caused by a weak product. They come from a motion that was never sound, and then scaled or automated. This skill is the check that comes first. It finds the stage the company is actually in, and tests the four parts of its go-to-market for weakness, so the fixes are chosen before anything new is built.

## When to use

- Before standing up any new outbound, inbound, or deal-process engine.
- When the company believes it has a marketing problem or a sales problem, and the root cause is unclear.
- When growth has stalled.
- When teams disagree about who the customer is, what the motion is, or when to scale.

Route elsewhere when:

- The question is the ICP itself. Use `icp-builder`.
- The question is the organisation design. Use `gtm-planning-org-design`.
- The question is the operating cadence. Use `revenue-operating-cadence`.

## Inputs

- Revenue and its trajectory over the last eight quarters.
- Team structure: who owns each stage of the revenue process, and whether customer success is part of the revenue conversation.
- Win rate, retention, and sales cycle length.
- The current motion: who generates demand, who sells, and who retains.

## The fit stages

Place the company in exactly one stage. Companies routinely place themselves too high.

| Stage | Fit | Focus | Motion | Growth pattern |
|---|---|---|---|---|
| 1. Ideation | Problem-market fit | Leads | Sales-led | Inefficient, searching |
| 2. Transition | Product-market fit | Accounts | Sales and marketing aligned | Efficient |
| 3. Execution | Platform-market fit | Customers | Integrated revenue team | Efficient at scale |

Classify using the signals above. If the evidence conflicts, choose the earlier stage and say why.

## Procedure

1. **Place the stage** from the signals. Record the evidence for each.
2. **Market.** Is the target customer defined in the same terms by sales, marketing, and customer success? Is the problem they pay to solve written down, and does the evidence show they buy it? A mismatch here is the most common cause of every other problem.
3. **Operations.** Does every team use the same stage definitions, the same data, and the same handoffs? Who owns the process from first touch to renewal?
4. **Velocity.** Where do deals slow down? Compare stage-by-stage conversion and time in each stage. A bottleneck is the place to look before adding volume.
5. **Expansion.** Do existing customers grow, and who is accountable for that growth? If customer success is not part of the revenue plan, expansion is probably left to chance.
6. **Prioritise the fixes.** For each weakness, state the evidence, the cost of leaving it, and the smallest change that would test a fix. Order by the stage: at stage 1, market and operations come first. At stage 2, velocity and expansion. Do not start a new engine until the weakness it would depend on is fixed.
7. **State what not to scale.** Name the motion that should stay small until the fix is proven.

## Output

- The stage, with the evidence.
- The four-part assessment, each with a rating, the evidence behind it, and the main weakness.
- A prioritised fix list, with the test for each fix.
- A list of motions to hold back from scaling.

## Quality bar

The stage is supported by evidence, not by the company's own description of itself. Each of the four questions is answered from data where data exists. Fixes are ordered by stage, and each names a test. Watch for a stage placed by aspiration, a fix list with no order, and a recommendation to build a new engine before the basics are sound.
