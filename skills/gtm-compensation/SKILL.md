---
name: gtm-compensation
version: 1.0.0
status: draft-for-review
description: "Use when designing, auditing, or explaining sales and customer success compensation: OTE and pay mix, quota setting, commission accelerators and decelerators, SPIFs, clawbacks, ramp, and rollout of a new plan. Gives the plan structure, a health check, and benchmark ranges to calibrate per client. Covers how to pay people, not org design or capacity planning (see gtm-planning-org-design). Not legal or tax advice."
sources:
  - "GTM compensation design (MIT, Rutger Katz / Neon Triforce), AE, SDR, CSM, and leader OTE structures, pay mix, accelerator ladder, decelerators, ramp, quota methodology and pipeline coverage check, SPIF rules, clawback rules, health check, rollout sequence, mid-year change rules, underperformer rule, EU pay transparency considerations"
  - "Benchmark ranges in the source are vendor survey and practice-based figures, labelled as starting points and to be replaced with the client's own market data"
  - "Adapted for GTM-360: the pilot-stage AI SDR pay bands and the AE productivity projections are excluded as unproven; the accelerator and decelerator rules are merged into one ladder; clawback is a plan-design term only; legal points are flagged for local counsel"
---

# GTM compensation design

## Purpose

Compensation is a behaviour system. Every pound or euro of variable pay tells people what the company values. A plan that pays for bookings when the company needs retention will get bookings and poor retention. Design the plan from the company's stage and strategy first, then the numbers.

## When to use

- Designing a new plan, or the change to an existing one.
- Auditing a plan that is not producing the behaviour the company needs.
- Benchmarking an OTE, a pay mix, or a quota.
- Planning the rollout of a change.

Route elsewhere when:

- The question is headcount, territories, or the capacity model. Use `gtm-planning-org-design`.
- The question is whether a forecast is credible. Use `revops-forecasting`.

## Inputs

- Company stage, and the GTM motion (new business, expansion, renewal, or a mix).
- The behaviour the company needs to change, stated plainly.
- Role, level, and location of each person in scope.
- Attainment history: how many reps reach plan, and how the spread looks.
- Quota and territory data: pipeline coverage and historical conversion by segment.
- The CRM fields that can reliably attribute a metric. Anything not in the CRM cannot go in the plan.
- Employment and tax context for each country the team works in. Involve local counsel where needed.

## Core principles

1. **Keep it simple.** If a rep cannot estimate their earnings in their head, the plan is too complex. Aim for two or three components at most.
2. **Match the plan to the stage.** Early-stage companies need hunters who close what moves, so the weight is on new business. Growth-stage companies need efficiency, so add quality gates. Mature companies need retention, so weight toward net retention and expansion.
3. **Pay only for what you can measure.** Every metric in the plan needs a clean CRM source. Reps optimise for what they can see and ignore what they cannot.
4. **Variable pay has to vary.** If most reps land between 90% and 110% of quota every quarter, the plan has no teeth. A healthy spread has top performers well above target, average performers near it, and underperformers clearly below it.
5. **Review once a year and change sparingly.** Mid-year changes destroy trust. Make changes at the start of the fiscal year, unless the business reality has changed.

## Role architecture

### Account executives

Pay mix, by sales motion:

| Motion | Base to variable |
|---|---|
| Full-cycle closers | 50/50 |
| Enterprise, with long cycles | 60/40 |
| Transactional, high volume | 40/60 |

Quota-to-OTE ratio, by motion:

| Motion | Ratio |
|---|---|
| Standard | 5:1 |
| Enterprise or complex | 4:1 |
| Transactional or SMB | 6:1 |
| Self-serve or high velocity | 8:1 or more |

Commission mechanics:

- Linear commission pays a fixed rate on every unit closed. It is simple, but it does not reward over-performance.
- Tiered or accelerated commission pays a base rate up to quota and a higher rate above it. This is the usual choice for B2B.

One accelerator ladder, with example rates to replace with the client's own:

| Attainment | Rate |
|---|---|
| Below 50% | Half the base rate |
| 50% to 100% | Base rate (for example 10%) |
| 100% to 120% | 1.5 times the base rate (for example 15%) |
| 120% and above | 2 times the base rate (for example 20%) |

The decelerator below 50% is there to avoid large payouts on a very poor quarter, without zeroing out early-stage deals.

Commission basis:

- Pay on first-year ACV, not total contract value. Paying on total contract value rewards deep discounting on multi-year deals.
- Pay on net-new ARR, not on bookings that include renewals.

Ramp, by month of tenure:

| Month | Base | Variable |
|---|---|---|
| 1 | 100% | 0%, while learning |
| 2 | 100% | 50%, against a reduced quota |
| 3 | 100% | 75%, against a reduced quota |
| 4 and after | 100% | Full plan |

Ramp quotas should rise roughly 25, 50, 75, and 100% of full quota across the first four months. Enterprise ramps often run six months. Transactional and SMB ramps often run two.

### SDRs

- Pay mix: 70/30 is standard, because SDRs control less of the outcome. 60/40 suits experienced SDRs in high-activity models.
- Primary metric, 70 to 80% of variable: qualified opportunities that sales accepts. The word "accepted" creates a quality gate.
- Secondary metric, 20 to 30% of variable: pipeline value, or opportunities that progress past a defined stage.
- Do not pay on calls, emails, or meetings booked before qualification. Those belong in coaching, not in the plan.
- Build a promotion path to AE, typically 12 to 18 months. SDRs who beat quota for three or more quarters in a row should see a defined route. It is a retention tool as well as a development one.

### Customer success

Pay mix, by the scope of the renewal decision:

| Scope | Base to variable |
|---|---|
| CSM owns the renewal number | 70/30 |
| CSM influences the renewal but does not own it | 80/20 |
| CSM is purely relationship and adoption | 90/10 |

Decide what the CSM is paid for. The two options pull in opposite directions:

- Gross retention focus, 40 to 50% of variable: pays for stopping churn. It drives health monitoring and risk work.
- Net retention or expansion focus, 30 to 40% of variable: pays for growth in the existing base. It drives discovery and upsell.

Choose one as the primary metric, at 60% or more of variable. Use the other as a check. Health or adoption metrics, at 10 to 20% of variable, only if they are measured reliably.

Decide who owns the renewal conversation before designing the plan. If the answer is unclear, renewals slip and people blame each other.

### Sales leaders

Pay mix: 60/40 for frontline managers, 65/35 for directors, 70/30 for VPs.

Frontline manager variable, typical split:

- Team attainment: 60 to 70%.
- Personal pipeline or deals: 0 to 20%, only if they carry a book.
- Team development (ramp time, retention, quota spread): 10 to 20%.

Avoid a large personal quota for managers. A manager carrying 30% or more of a personal number tends to take the best leads and neglect coaching. If they must carry deals, cap their personal share at 20% of variable.

Pay managers on the team's whole performance. Three reps at 150% and five at 60% is poor management, even if the average hits plan.

## Benchmark ranges

Use these as starting points only. They vary with geography, stage, deal complexity, and hiring market. Replace them with the client's own market data, from a benchmark database or a custom survey, every 12 to 18 months.

US ranges, base and OTE:

| Role | Base | OTE |
|---|---|---|
| Junior AE (0 to 2 years) | $60K to $85K | $100K to $140K |
| Mid-level AE (2 to 5 years) | $80K to $110K | $140K to $200K |
| Senior or enterprise AE (5 years or more) | $110K to $150K | $200K to $300K |
| SDR or BDR | $45K to $65K | $65K to $90K |
| Senior SDR or SDR lead | $55K to $75K | $80K to $110K |
| CSM | $70K to $100K | $85K to $120K |
| Senior or enterprise CSM | $100K to $130K | $120K to $160K |
| Frontline sales manager | $120K to $160K | $180K to $250K |
| Director of sales | $150K to $200K | $220K to $320K |
| VP of sales | $180K to $260K | $280K to $420K |
| CRO | $220K to $320K | $350K to $550K |

Quota for AEs, by level: $500K to $750K for junior, $700K to $1.2M for mid-level, and $1M to $2M for senior.

Western European ranges run about 15 to 30% below US levels for equivalent roles. Base and OTE in euros:

| Role | Base | OTE |
|---|---|---|
| Junior AE | €45K to €65K | €70K to €100K |
| Mid-level AE | €60K to €85K | €100K to €150K |
| Senior or enterprise AE | €85K to €120K | €150K to €220K |
| SDR or BDR | €35K to €50K | €50K to €70K |
| CSM | €55K to €80K | €65K to €95K |
| Sales manager | €90K to €130K | €130K to €190K |
| Director | €120K to €160K | €170K to €240K |
| VP of sales | €140K to €200K | €210K to €320K |

## Quota setting

Top-down allocation:

1. Start from the revenue target in the plan.
2. Add a buffer of 10 to 20% above target, because not everyone will reach 100%.
3. Divide the number across segments and territories, by market opportunity.
4. Assign each person a quota based on territory potential, not tenure.
5. Test each quota. A competent rep in that territory should be able to reach 80 to 100% with strong execution.

Bottom-up check:

1. For each rep, count the qualified pipeline at the start of the quarter.
2. Apply historical stage-to-close conversion rates.
3. Add the pipeline expected to be created during the quarter.
4. If the result is below 80% of quota, the quota is unrealistic, or the pipeline plan is too small.

Pipeline coverage: reps should start the quarter with at least 3 times their quota in qualified pipeline. Below 2.5 times, start a pipeline generation push at once. Check this against the win rate (see `revops-forecasting`), because a low win rate needs more coverage.

Common quota errors:

- Last year's number plus 20%. Growth should come from market analysis and capacity, not an arbitrary uplift.
- Equal quotas for unequal territories.
- Flat quarterly quotas where the business is seasonal. If Q4 is historically 35% of annual revenue, the Q4 quota should reflect that.
- Full quota for a rep still ramping.

## SPIFs and clawbacks

SPIFs are short-term incentives for a specific behaviour, such as entering a new segment, adopting a new product, or clearing the end of a quarter. Rules:

- Run for 30 days at most.
- Use simple, clear qualification criteria.
- Pay within the current pay period, not at quarter end.
- Keep the total budget at 5 to 10% of the quarterly variable pool.
- Run no more than two or three a year. Otherwise they become expected, and stop motivating.
- A SPIF is paid on top of the base plan, never instead of it.

Clawbacks reduce commission when a customer churns within a defined window, usually three to six months. This aligns sales with customer quality. Rules:

- Write the clawback into the plan before the deal is signed. Do not apply it retroactively to earnings already paid.
- Claw back the commission amount only, not a penalty.
- Prorate by the time left in the window. A customer churning at month four of a six-month window means a claw back of about a third.
- Claw back variable pay only, never base salary.
- Check enforceability in each country. Some jurisdictions restrict commission clawbacks. Confirm with local employment counsel.

## Health check

Audit a plan against these questions:

- **Alignment:** does the plan reward what the strategy needs? Is each metric tied to revenue outcomes, not just activity? Do sales, marketing, and customer success pull in the same direction?
- **Simplicity:** can a rep work out expected earnings in two minutes? Are there three or fewer variable components? Is the payout schedule predictable?
- **Fairness:** is there a real spread between top and bottom performers? Are quotas based on market opportunity? Do territories offer similar earning potential?
- **Competitiveness:** is OTE within the market range for role, level, and geography? Are ramp and draw terms competitive for hiring?
- **Sustainability:** can the company afford payouts at 120% of attainment? Does the quota-to-OTE ratio fit the unit economics? Does the plan still work if revenue is up, down, or flat?

## Rollout

Before rollout, 60 to 90 days ahead:

1. Brief the CFO and board on cost, expected return, and payback.
2. Run small-group sessions by segment, explaining the reason for the change.
3. Prepare answers to the three likeliest objections: a pay cut, complexity, and unfairness.
4. Optionally, pilot with 10 to 20% of the team and adjust.
5. Write a two-page plan summary that reps can use without calling finance.

Rollout week:

1. An executive-led all-hands, covering the reason and the benchmark data.
2. One-to-one sessions where finance or people walk each rep through their own OTE, quota, and payout schedule.
3. A published FAQ within 24 hours.
4. Short breakout sessions with worked calculations, if the plan is complex.

First 90 days:

1. Weekly pulse checks, asking whether people understand the plan, not only whether they like it.
2. Run payouts manually for the first month, check the calculations, and fix discrepancies within 48 hours.
3. Escalate objections to management, and do not let them sit.
4. If quotas look unrealistic by week eight, pause and reallocate before the quarter end.

Mid-year changes are allowed only when the business has changed, such as a market downturn, a product launch, or a major churn event. Never change the plan because someone is beating quota. Announce any change before it takes effect, and document the reason in writing.

Underperformers: if someone is tracking below 80% of quota by month two of the quarter, escalate now, not in month four. Ask whether the person is capable, or whether the quota or the plan is creating the problem. A comp plan does not fix a capability gap. Management does. Use comp as a diagnostic, not a cure.

## EU considerations

The source flags the EU Pay Transparency Directive, with a transposition deadline of 7 June 2026 and reporting obligations for larger employers. Points to confirm with local counsel, not to rely on from this skill:

- Job postings in member states may need a salary range.
- Salary-history questions may be restricted during recruitment.
- Gender pay reporting may apply above a headcount threshold.
- Penalty levels are set by each member state. Do not quote a figure without checking it.
- Variable pay may be taxed differently across countries, and benefits may be set by statute.
- For people taxed in one country and employed by a company in another, check the pay structure for tax efficiency.

Ask about team geography and cross-border tax early. Compensation cannot be designed apart from employment law and tax.

## Output

- The plan structure for each role in scope: pay mix, OTE, quota, accelerators, ramp, and any SPIF or clawback, with the basis for each number.
- The benchmark range used, its source, and where the client sits in it.
- The health-check result, with each failed item named.
- The modelled payouts at 80%, 100%, and 120% of quota, with the cost against the budget.
- The rollout plan and the list of points to confirm with counsel.

## Quality bar

A good plan pays for the behaviour the company needs, is simple enough to check on paper, spreads payouts so that performance shows, and is paid out accurately. Watch for plans that pay on activity, quotas set by rule of thumb, clawbacks applied retroactively, and benchmark ranges quoted without their source.
