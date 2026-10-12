---
name: abm-measurement-framework
version: 1.0.0
status: draft-for-review
description: Use when measuring account-based marketing success, setting ABM metrics by account stage, choosing an attribution model, or working out ABM ROI and cost per account. Method only, no client data. Not for the ABM plan or budget (see abm-strategy-planner) or an account audit (see linkedin-ads-audit).
sources:
  - "ABM measurement framework (MIT, Ivan Falco, Frontal), stage metrics, attribution, ROI formulas"
---

# ABM measurement framework

Defines how to measure an account-based programme. It is a method reference, used by the reporting and planning skills.

## Purpose

Measure accounts moving through buying stages, not leads moving through a funnel. A programme measured with lead metrics will be judged wrongly.

## When to use

- A programme's measurement is being defined before launch or reviewed mid-flight.
- A team is judging an account-based programme with lead metrics and needs account-level measures.

Route elsewhere when:
- The question is the dashboard for a client. Use `abm-account-engagement-report`.
- The question is the plan and budget. Use `abm-strategy-planner`.

## Inputs

- Target account list, with a match status for each account.
- Ad and engagement data at account level.
- Pipeline and closed-won data at account and opportunity level.
- Programme spend.

## Stage model

| Stage | Definition | Primary measure |
|---|---|---|
| Coverage | Share of target accounts reachable | Match rate |
| Awareness | Accounts that have seen the brand | Accounts with 50 or more impressions |
| Engagement | Accounts interacting | Accounts with 5 or more clicks, or 10 or more engagements |
| Pipeline | Accounts with an open opportunity | Influenced pipeline, accounts in pipeline |
| Revenue | Closed-won from target accounts | Closed-won value, win rate |

Stage thresholds such as 50 impressions and 5 clicks are defaults from the source. Set them per client and record the reason.

## Procedure

1. **Baseline first.** Before launch, record win rate, deal size, sales cycle, cost per opportunity, and pipeline per dollar from the CRM. Without a baseline, no uplift can be claimed.
2. **Targets.** Set a target against each baseline measure, with a timeline.
3. **Measure coverage and awareness** as account counts, not lead counts.
4. **Measure engagement** as the share of aware accounts that are engaged.
5. **Measure pipeline and revenue** with multi-touch attribution at account level. Choose the model using the table below.
6. **Calculate efficiency:** pipeline per dollar, cost per engaged account, cost per pipeline account, blended cost per new customer, lifetime value to cost.
7. **Set the reporting cadence:** campaign dashboard (live), account progression (weekly), pipeline influence (fortnightly), executive summary (monthly or quarterly).
8. **Check the maturity level** the team is at (basic, intermediate, advanced, optimised) and list what is missing before reporting on revenue.

## Attribution choice

| Model | Suitable for ABM | Reason |
|---|---|---|
| First touch only | No | Ignores the nurture work |
| Last touch only | No | Over-credits sales |
| Lead-based MQL attribution | No | ABM measures accounts |
| Account-level multi-touch | Yes | Credits all account touches |
| W-shaped | Yes, for long cycles with clear stage gates | Credits first touch, lead, and opportunity creation |

Run two models side by side where possible, and report the difference.

## Formulas

- Account reach = accounts with 50 or more impressions divided by target accounts.
- Engagement rate = engaged accounts divided by aware accounts.
- Pipeline per dollar = pipeline value divided by programme spend.
- ABM ROI = (revenue from ABM accounts minus programme cost) divided by programme cost.
- Cost per engaged account = programme spend divided by engaged accounts.
- Cost per pipeline account = programme spend divided by accounts in pipeline.
- Pipeline velocity = (opportunities x win rate x average deal size) divided by sales cycle length in days.

## Output

A measurement plan with: the baseline table, targets by stage, the attribution model chosen and why, the formulas used, the reporting cadence, and the maturity assessment.

## Quality bar

- Every target has a baseline behind it.
- Benchmarks shown are labelled as reference points from a named source, not as standards.
- Revenue claims separate exposure, influence, and attribution.
- No single programme's results are used as the benchmark for another.

## Boundaries

- Method only. Dashboards go to `abm-account-engagement-report`. Plans go to `abm-strategy-planner`.
