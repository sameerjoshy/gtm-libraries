---
name: abm-strategy-planner
version: 1.1.0
description: "Use when someone wants an ABM strategy or plan, a LinkedIn ABM campaign plan, a budget and audience plan for account-based marketing, or needs to know how many ads or campaigns their budget supports. Builds a funnel-based plan from stated goals and economics. Not for measuring results (see abm-measurement-framework) or for choosing the campaign level (see abm-campaign-level-choice)."
---

# ABM strategy planner

Turns a short interview plus research into a funnel-based ABM plan with budget, campaign structure, and a pre-launch checklist.

## Purpose

Produce a plan a finance lead can check. Every number traces back to a stated input, and every assumption is labelled.

## When to use

- A LinkedIn account-based program needs a funnel-based plan with budget, campaign structure and a launch checklist.

Route elsewhere when:
- The question is reporting on a running program. Use `abm-account-engagement-report`.
- The question is how to define the measures. Use `abm-measurement-framework`.

## Inputs

Ask in small batches. Offer a default for each. Never block on a missing number.

1. Company website. Research it yourself. Do not ask the user to describe the product.
2. ABM revenue goal, and whether it is monthly (MRR) or annual (ARR).
3. Average contract value (ACV). Normalize to match the goal's basis.
4. Close rate, qualified to closed-won. Default 15%.
5. Qualification rate, demo to qualified. Default 75%.
6. Landing-page conversion, visit to booked demo or form. Default 0.8%.
7. LinkedIn CPC. Default $8. Use a live figure if a connector is available.
8. Planned monthly LinkedIn budget.
9. Target audiences (geography and industry). Seed from research and confirm.
10. Top jobs-to-be-done per audience and the core problem solved.

**Data order:** a live connector first, then the user's real figures, then the defaults above. Any figure that comes from a default must be labelled as a benchmark on the output.

## Procedure

1. **Interview** as above.
2. **Research** the website: product, use cases, customers. Draft the ICP and jobs-to-be-done, and show them to the user to confirm.
3. **Compute the funnel backwards:** goal, then deals needed, then demos needed, then qualified accounts needed, then clicks, then budget. Show the key numbers to the user before building the document.
4. **Budget math:** time to run = total budget needed / stated monthly budget. Report ROAS and pipeline per dollar.
5. **Affordable ads:** from budget and CPC, how many ads can run at once. Allocate across formats (single image, text, video, document, lead form) with the objective set per format.
6. **Allocation by ad set:** percent of spend and dollars per month, at both the stated budget and the recommended budget.
7. **Build the document** with: header (company, website, audience, date); goals and deal math; campaign structure with the flowchart; campaign content mapped to each audience's jobs-to-be-done; format best practices; launch practices; performance tracking; pre-launch checklist.

## Output

A self-contained HTML plan titled "[Company] LinkedIn ABM Strategy", with inline CSS and no external scripts, plus a PDF export of the same content. One campaign block per audience.

## Quality bar

- Revenue and ACV are on the same basis (both monthly, or both annual).
- Each figure from a default is labelled as a benchmark.
- The document states that all outputs are directional planning figures, not forecasts.
- Budget allocation percentages sum to 100 at each budget level.
- No budget is gated on CTR. CTR does not drive the budget math.

## Rules

- Planning only. For auditing existing spend, use `linkedin-ads-audit`.
- Do not present defaults as market data.
