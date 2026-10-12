---
name: roi-business-case
version: 1.2.0
description: "Use when a live deal needs a business case the buyer will believe: going into procurement, finance review, or executive sign-off, when a champion needs an internal case, or when a single optimistic ROI figure is drawing skepticism. Builds a one-page case with worst, average, and best scenarios, each tied to the buyer's root-cause problem and their own baselines, with every assumption visible. Not for the discovery-to-demo plan (see `discovery-to-demo-bridge`)."
---

# ROI business case

## Purpose

A single optimistic ROI figure looks like a sales document, and finance discounts it on sight. The champion then has to defend a number they did not build. This skill builds the case as a range: worst, average, and best. The worst case buys credibility, and the best case becomes believable because the downside was shown. It also gives the champion a case they can defend in procurement.

## When to use

- The deal is heading into procurement, finance, or executive sign-off.
- The champion needs an internal justification.
- A single ROI figure has been shown, or is about to be.
- Finance is likely to challenge the numbers.

Do not build the case on a problem whose impact cannot be grounded in the buyer's own baselines. Three scenarios built on invented inputs are three fictions. Getting the baseline is the first task.

Route elsewhere when:

- The question is which pains to demonstrate in the demo. Use `discovery-to-demo-bridge`.
- The question is the pricing or packaging itself. Use `pricing-monetization-ops`.

## Inputs

- Deal context: company, champion and role, stage, the investment, and the contract term.
- The root-cause problem, in the buyer's words.
- Baseline metrics the return depends on, from the buyer's own data.
- The mechanism by which the solution moves each baseline.
- Total cost over the term, so payback is real.
- The reviewers: finance, procurement, or executives, and what each will test.

## Procedure

1. **Anchor to the root cause.** State the problem as a mechanism. Every dollar in the model must trace to fixing it. Value unrelated to the root cause is removed, because it weakens the whole page.
2. **Write the baseline** with its source. Missing values are marked `[CONFIRM WITH BUYER]`, not filled with estimates. A soft baseline is labeled as soft.
3. **Define three scenarios** against the same baseline:
   - Worst: a small, defensible improvement, the level that works even if little goes right.
   - Average: the most likely improvement, given the buyer's context.
   - Best: an ambitious improvement that still rests on a real mechanism.
4. **Make assumptions visible.** For each scenario, state the improvement rate, the timeframe, and the baseline it applies to. A reader should be able to dispute one assumption and re-run the arithmetic.
5. **Compute value, investment, net return, and payback** for each scenario. Show the arithmetic once.
6. **Pre-handle the objection.** Add a short section on which assumption is most sensitive and what the buyer would need to believe for the average case to hold.
7. **Hand the case to the champion** with the reviewers' likely questions listed.

## Output

- One page: root cause, baseline table with sources, three scenarios with assumptions, investment, payback per scenario, and the most sensitive assumption.
- Open `[CONFIRM WITH BUYER]` items, with an owner for each.
- A list of likely reviewer challenges and the answer to each.

## Quality bar

Each scenario has its assumptions visible. The worst case is one the buyer can accept without argument. Every baseline has a source or a confirmation flag. Watch for a single headline number, industry averages standing in for the buyer's data, value that has no mechanism, and investment left out of the payback.
