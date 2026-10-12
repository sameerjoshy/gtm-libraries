---
name: revops-revenue-planning
version: 1.2.0
description: "Use when building an annual or quarterly revenue plan, reconciling a bottoms-up capacity plan with a top-down finance target, versioning the plan of record, deciding when to reforecast, or aligning FP&A with RevOps. Use when the forecast and the budget disagree, when a stretch target arrives without owners, or when the team asks when to start planning. Not for in-quarter forecasting mechanics (see `revops-forecasting`), GTM structure (see `gtm-planning-org-design`), or quota and commission design (see `gtm-compensation`)."
---

# Revenue planning

## Purpose

A revenue plan is a commitment between revenue, finance, and the market. It is not a board slide. The plan of record is the single agreed number everything else is measured against, and it is only worth having if the sales team can defend it.

This skill covers how to build the plan from capacity, reconcile it with the top-down ambition, keep the versions that make learning possible, and change the plan on triggers rather than on mood.

The core rule: start with what the team can produce, then decide what gap to close, and name the owner for every part of that gap.

## When to use

- The annual or quarterly plan has to be built, or rebuilt after a material change.
- Finance's target sits above what the bottoms-up build supports.
- The forecast and the budget disagree, and nobody can say which assumption broke.
- The team asks when to start planning, or how long the cycle should take.
- A reforecast is being discussed and nobody agrees on whether the trigger has fired.

Route elsewhere when:
- The question is weekly deal inspection or the in-quarter forecast call. Use `revops-forecasting`.
- The question is the territory design or headcount model. Use `gtm-planning-org-design`.
- The question is quota or commission. Use `gtm-compensation`.

## Inputs

- Capacity data: ramped-equivalent reps, their productivity and their pipeline.
- Finance's target and the ambition behind it.
- Market opportunity sizing for the segments in scope.
- The prior plan of record and every earlier version, kept for the audit trail.
- The reforecast triggers agreed in advance.

## Procedure

Work through the planning calendar, then build bottoms-up, reconcile, set versions and governance, and reforecast on triggers.

### Core principles

1. **Bottoms-up first, then top-down.** Build from current capacity and known pipeline. Finance adds ambition. Reconcile the gap with named scenarios, not by spreading a number across teams.
2. **Separate three questions.** What can we produce (capacity)? What do we want to produce (strategy)? What does the market allow (opportunity sizing)? Three analyses, three answers. Conflating them creates noise.
3. **Keep every version.** The original bottoms-up plan, the finance iteration, and the plan of record all persist. Every reforecast preserves the prior baseline. This is the audit trail that lets the team learn from misses.
4. **Stretch is a scenario, not a directive.** A target above bottoms-up becomes named scenarios with owners, assumptions, and dependencies. A stretch without owners is a wish.
5. **Reforecast on triggers, not on mood.** Fixed windows plus explicit triggers. Continuous re-planning erodes ownership.
6. **FP&A and RevOps decide jointly.** RevOps owns pipeline reality and capacity. FP&A owns financial implications. A forecast that does not reconcile across both is revised before it is approved.

### Planning calendar

Build backwards from the fixed date: board approval, or the date the plan must be in market. Compressed cycles can shorten data gathering and validation. They should not shorten reconciliation.

A default twelve-week cycle for a calendar-year business, with phase lengths to calibrate:

- **Phase 1, data and retrospective (weeks 1 to 2).** Pull the prior year's close-out and the current-year variance. Open the input window for sales capacity, market intelligence, and customer feedback.
- **Phase 2, bottoms-up build (weeks 3 to 5).** Account planning by segment: current ARR, known expansion, and new-business pipeline. Capacity model: hires, ramp, retention. Roll up segment totals.
- **Phase 3, top-down and reconciliation (weeks 6 to 8).** Finance shares the top-down model. Run the reconciliation meeting. Revise the plan with scenarios, and model the cost of hiring and spend.
- **Phase 4, validation (weeks 9 to 10).** Executive alignment. Validate assumptions against current pipeline. Lock the plan of record. Run sensitivity analysis and draft the board narrative.
- **Phase 5, approval (weeks 11 to 12).** Board materials and presentation. Budget allocation to departments.
- **Buffer.** Implementation: enablement, quota setting, and incentive finalization.

For a fiscal year that starts in a different month, shift the whole calendar by the difference. For example, a plan that goes live in April starts roughly three months earlier than a calendar-year plan.

### Bottoms-up build

Bottoms-up is not a line-by-line forecast. It is a capacity-grounded estimate of what the team should produce given known constraints.

**Step 1: segment the base.** Split accounts by tier (SMB, mid-market, enterprise) and by revenue type (new business, expansion, renewal). Baseline current ARR or bookings for each.

**Step 2: capacity model.** Capacity uses ramped-equivalent reps, not heads.

```
Bookings capacity = Sum over reps of (ramp factor x annual quota)

Example:
  7 account executives: 3 in ramp at 80% effective, 4 tenured at 100%
  Effective reps: 3 x 0.8 + 4 x 1.0 = 6.4
  Annual quota per AE: $850K
  Bookings capacity: 6.4 x $850K = $5.44M
```

Add inbound and self-sourced pipeline and expansion as separate lines, each with its own source and assumption. Do not add a percentage uplift without showing where it comes from. Use the ramp curve from `sales-ramp-enablement`.

**Step 3: overlay named pipeline.** Audit the CRM for named deals above a threshold. These have confirmed timelines, so use their stage-based probabilities, not the blended average.

```
Named pipeline, next six months:
  Deal A  $45K   70%   September
  Deal B  $180K  50%   October
  Deal C  $120K  85%   August
  Total named:               $345K
  Probability-weighted:      $223.5K
```

If named pipeline exceeds the capacity model, document the delta and its source. If it falls short, that shortfall is the pipeline-generation gap for the year.

**Step 4: segment growth assumptions.** Each revenue type has its own logic.

- **New business.** The most variable. Capacity model times the historical attainment per rep, less known losses from churn and any new market entries.
- **Expansion.** Current expansion base times retention times growth. Example: $2.2M base x 92% retention x 1.12 growth = about $2.27M.
- **Renewal.** Current renewal base times gross retention. Example: $1.3M x 97% = $1.26M.

Sum the segments for the company total.

**Step 5: document assumptions in one shared sheet.** Every assumption has a value, a source, an owner, and a confidence rating. This sheet is the contract between revenue and finance. Finance should be able to challenge any line.

Example rows: renewal gross retention (source: customer success data, high confidence); expansion growth (source: three-year trend, medium); new-business rep capacity (source: quota times ramp model, medium); inbound to outbound mix (source: sourcing audit, low).

### Reconciliation

Finance's top-down target comes from growth strategy, board expectations, or a fundraising narrative. The reconciliation meeting closes the gap between it and the bottoms-up.

**Pre-meeting.** Finance brings the top-down target, its drivers, and a sensitivity analysis at different growth rates. Revenue brings the segment bottoms-up, the capacity model, and the named pipeline overlay.

**Ninety-minute structure.**

1. **Set the frame (5 minutes).** This is a diagnostic, not a negotiation. Where the two analyses converge, confidence is high. Where they diverge, something is true that needs learning.
2. **Present bottoms-up (20 minutes).** Segment by segment, with the assumptions highlighted.
3. **Present top-down (10 minutes).** The target, its drivers, and its sensitivity.
4. **Close the gap (40 minutes).** Work through named scenarios. Each scenario has an owner, a dependency, and a value. Example: two net new AEs hired early in the year, with a ramp, add a stated amount of capacity; an investment in customer success adds expansion; additional targeted pipeline spend adds new-business pipeline. Sum the scenarios and check they close the gap.
5. **Lock the plan of record (10 minutes).** The plan of record is the base (bottoms-up) plus the stretch (scenarios with owners).
6. **Document scenarios and owners (5 minutes).** If hiring slips, the plan adjusts visibly.

If the gap cannot close with credible scenarios, say so. Escalate the decision with the bets required and the owners of each bet. Do not close it with a number nobody owns.

### Versions and governance

Three versions persist:

- **Bottoms-up original.** Drafted by revenue in the build phase. Locked after reconciliation, never overwritten.
- **Finance stretch iteration.** The top-down target and its assumptions. Locked after reconciliation. The comparison baseline for reforecasts.
- **Plan of record.** The final agreed plan with its scenarios. The single source of truth that every team executes against.

Reforecasts are saved as dated versions and kept. Each one compares the current projection against both the plan of record and the original bottoms-up. Example at a mid-year reforecast: plan of record at 8.5M, bottoms-up at 7.8M, current forecast at 7.9M. The variance from plan is minus 0.6M, about 7%. The question is why: did pipeline generation miss, did deals slip, or did an assumption break? Comparing against both baselines shows whether the miss was capacity or execution.

### Reforecasting

Reforecasting is disciplined re-evaluation on a fixed cadence or when a trigger fires. It is not continuous re-planning.

**Cadence.**
- Monthly: a one-hour review of current forecast against the plan of record. Flag variances beyond a set band (default plus or minus 10%) for deeper analysis.
- Quarterly: a full reforecast. Update assumptions, recalculate segments, reconcile across revenue and finance, and record scenario changes.
- On trigger: a full reforecast within five business days of the trigger.

**Triggers (defaults to calibrate).**

Revenue-side:
- Pipeline coverage falls below the required multiple. Required multiple is 1 divided by the historical win rate, so a 25% win rate needs about 4x. A flat 2.5x or 3x is only a starting point.
- Month-end close rate falls below a set share of plan (default 60%).
- Forecast accuracy outside a set band for two consecutive months (default plus or minus 20%).
- Named-deal slippage above a set share (default 50%).

Unit economics:
- Net revenue retention falls below plan (default 105%).
- CAC payback exceeds plan by a set margin (default 14 months).
- Gross margin falls more than a set amount below plan (default 3 points).

Execution:
- Actual revenue variance above a set band (default 15%) for two consecutive periods.
- Hiring plan slips.
- A single churn event above the materiality threshold. Set this as a share of ARR. A fixed dollar figure only fits a company of one size.

External:
- Competitive change affecting win rate.
- A macro shock with material impact.
- A product delay that moves pipeline by six or more weeks.

**Locked and flexible parameters.** Some things do not change mid-year: quota targets, the headcount plan committed to the board, compensation structure, and the ICP definition. Others move freely: the revenue target, pipeline assumptions, scenario owners, and the reforecast cadence itself. Mixing the two is the main cause of reforecasting chaos. Lock what must hold, and reforecast what is meant to move.

### Benchmarks as context

Use benchmarks to ask questions, not to set targets.

- **Forecast accuracy.** Monthly actuals against the month-start forecast. Bands used as defaults: within 5% is strong, within 10% is good, 15 to 20% is common, and 25% or more means the process needs structural fixing.
- **Quota attainment.** If fewer than half the reps are at quota across the organization, check the quota-setting process before blaming reps.
- **Coverage.** Use the win-rate formula above, not a fixed multiple.
- **Reforecast frequency.** Quarterly at minimum, so the plan does not drift from reality. Weekly is too often: the overhead of re-planning exceeds the signal. Monthly reviews with quarterly full reforecasts is a common and workable default.

### FP&A and RevOps collaboration

RevOps is the pipeline operator: deal inspection, forecast categories, stage accuracy, sandbagging detection, and the weekly forecast call. FP&A is the financial modeler: cash, working capital, burn, expense budgets, and the board narrative.

**Joint decisions.** The plan of record is signed by both. Reforecasts are validated by both. Stretch scenarios are assessed for feasibility by RevOps and modeled financially by FP&A. The headcount plan has RevOps owning the capacity math and FP&A owning cost allocation.

**Rhythm.** A thirty-minute weekly sync flags any material change in the forecast or pipeline, so surprises do not reach the board first. A quarterly reconciliation recalibrates top-down against bottoms-up, with assumptions debated openly and resolved on data.

### AI in planning

Forecasting tools and AI-assisted deal scoring can reduce the manual effort in the forecast call and surface outliers. Use their outputs as inputs to the triggers above, not as replacements for them. Two checks before relying on them: confirm the model's accuracy against the client's own past forecasts, and confirm which decisions a person must still approve. AI-driven forecasts that nobody can explain do not survive a board question.

Where AI-driven tools change headcount assumptions, for example by replacing part of the sales development capacity, model both the human and the automated motions explicitly, with their own cost and ramp.

### Diagnostic: ten questions

Answer each yes or no. Any "no" or "unknown" marks a process risk in that area.

1. Is there a planning calendar with locked dates for each phase?
2. Can the bottoms-up be produced without finance input, from capacity and pipeline alone?
3. Are all three versions preserved: bottoms-up, finance stretch, and plan of record?
4. Can every dollar of stretch be explained with a named scenario, an owner, and assumptions?
5. Does every reforecast compare against both the plan of record and the original bottoms-up?
6. Is the list of what may not change mid-year written down?
7. Do FP&A and RevOps review every material forecast change together?
8. Are the reforecast triggers defined, with numbers, before they fire?
9. Do reps know the plan of record and their segment targets?
10. When the plan misses, can the miss be traced to a specific assumption?

Scoring: eight or more yes is strong discipline. Five to seven means process gaps to fix in the next cycle. Fewer than five means plan the planning process before setting revenue targets.

### How to use this skill

**"We need an annual plan from scratch."** Start from the board date and build the calendar backwards. Run the bottoms-up. Overlay named pipeline. Reconcile against the top-down target. Lock the plan of record with its three versions.

**"Our plan and forecast do not align."** Compare the two documents. The plan is annual strategy; the forecast is the current expectation. A mismatch usually means an assumption broke: retention lower, velocity slower, or deal sizes smaller. Check which trigger fired.

**"Finance gave us a stretch we do not believe."** Make each part of the stretch a named scenario with an owner and a dependency. If the scenarios do not close the gap, escalate with the specific bets required: "The market will not support this plan unless we make these three bets. We own two. The third depends on product. What is product committing to?"

**"We reforecast monthly and it is chaos."** Set the cadence: quarterly minimum, monthly only where the business is highly volatile. Define the triggers with numbers. Expose which function is destabilizing the process.

## Output

- The planning calendar with locked dates.
- The bottoms-up build: segments, capacity model with ramp, named pipeline overlay.
- The shared assumptions sheet with owners and confidence ratings.
- The reconciliation: bottoms-up, top-down, the gap, and the named scenarios.
- The three versions and the reforecast log.
- The trigger definitions and the locked and flexible parameter list.

## Quality bar

The plan starts from capacity, every stretch dollar has an owner, all three versions survive, and triggers are defined with numbers before they fire. Watch for targets spread across teams without scenarios, reforecasts triggered by mood, one number used for both the board and the territory plan, and benchmark figures presented as targets.
