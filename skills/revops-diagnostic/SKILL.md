---
name: revops-diagnostic
version: 1.2.0
description: "Use when revenue problems arrive as symptoms (weak pipeline, a forecast nobody believes, underperforming reps, churn, deals slipping late in the quarter, \"we are busy but nothing moves\") and the real constraint is unknown. Locates the layer of the revenue system where the problem sits, runs the information-focus-action check and the six stages, triages which motion to examine first, and produces one A3-lite with a stop-rule. Route to crisis handling first if several systems are failing at once. Not for the forecast model itself (see `revops-forecasting`)."
---

# RevOps diagnostic

## Purpose

When revenue underperforms, the first proposed fix is usually the wrong one. "Pipeline is weak" triggers a hiring request. "The forecast is wrong" triggers a new tool. Both can be right, but the problem usually sits one layer away from where it appears.

This skill finds the binding constraint before anyone recommends a fix. It is a diagnostic, so its output is a located problem, a single countermeasure, and a test that could prove it wrong.

The core rule: problems almost always sit one layer out from where they appear. Find the layer first, then the constraint, then the fix.

## When to use

- Leadership describes a revenue symptom and wants a remedy.
- The team keeps having the same problem in different forms.
- A new CRO, RevOps lead, or board member needs a credible read of the system in the first 30 days.
- Pipeline, forecast, rep productivity, or retention is missing plan, and the cause is contested.

Route elsewhere when:

- Several systems are failing at once (forecast variance far outside the normal band, coverage falling, retention collapsing, trust in the numbers gone). Triage the emergency first, then return here.
- The question is the forecast mechanics. Use `revops-forecasting`.
- The question is the KPI set or stage design. Use `revops-strategy`.
- The question is the change program after the constraint is found. Use `revops-change-management`.

## Inputs

- ARR, growth rate, and efficiency metrics: net and gross revenue retention, CAC payback, win rate, sales cycle length.
- Current organization chart for revenue functions and their headcount.
- The ICP definition, if one exists.
- Tech stack inventory: CRM, marketing automation, customer success tooling, data sources.
- The meeting cadence: which meetings exist, who attends, and what decisions they produce.
- The top three to five pains as leadership describes them, in their own words.
- The most recent board pack or quarterly review.

## Procedure

### Step 1: Model the system before the problem

Every revenue system has three layers. Direction flows down (strategy sets what to do); results flow up (outcomes tell strategy whether it worked).

- **Governance.** The steering cycle: priorities, KPIs, decision rights, and the rhythm of review. Weekly checks execution, monthly checks progress, quarterly sets bigger steers, and annual re-plans.
- **Enablement.** The infrastructure: people and coaching, processes and handovers, platforms configured for the workflow, and the data spine (shared definitions, data flows, quality, and dashboards everyone reads the same way).
- **Value loops.** Where value is created. The product loop (design, build, measure, learn) and the revenue loop (market, acquire, adopt, renew, expand). The loops are broken when customer learning does not flow back to product or to the ICP.

Note which layer the symptom appears in. The constraint is usually in another one.

### Step 2: Map the symptom to its likely constraint

| Symptom | Common blame | Likely constraint |
|---|---|---|
| Pipeline is weak | Marketing or SDRs | Qualification is loose (enablement), or the ICP is wrong (value loop) |
| Forecast is wrong | The data | Stage definitions differ between teams (governance) |
| Reps underperform | The people | Platform not configured for the workflow, or no coaching rhythm (enablement) |
| Too many initiatives | "People are busy" | No portfolio decisions, no work-in-progress limit (governance) |
| Churn at a fixed month | Customer success | Wrong customers sold, or onboarding does not deliver first value (value loop) |
| "We need a new CRM" | The platform | Processes undefined and data spine missing (enablement) |
| Marketing "does not generate pipeline" | Marketing | No shared ICP, no feedback loop from sales, broken attribution (enablement) |
| Deals slip in the last weeks | The AE | No mutual action plan, single-threaded deals (process and governance) |

Treat the table as a hypothesis list. Confirm each with data before acting.

### Step 3: Run the information-focus-action check

When conversations go in circles or decisions do not stick, test each link of the chain.

**Information:** Do we have the right signals and shared definitions?
- Are stage exit criteria defined, agreed, and audited?
- Are lost and stalled reasons logged, and is there a pattern over the last 60 days?
- Do dashboards show the same picture to every team?

If Information is weak, people debate numbers instead of decisions. Fix definitions and build shared views.

**Focus:** Do we have rhythm, decision rights, and priorities?
- Is there a weekly revenue review with a fixed agenda?
- What counts as a breach that needs immediate action?
- Who makes go or no-go calls on experiments, and what are the stop-rules?
- Are decisions logged with owner, deadline, and expected impact?

If Focus is weak, decisions do not stick. Install a cadence, assign decision rights (see Step 8), set work-in-progress limits, and keep a decision log.

**Action:** Do decisions get executed, and do learnings spread?
- For last month's top three decisions, what is the owner, status, and measured impact?
- When something works, how does it reach other reps?
- Are experiments time-boxed with success metrics and kill criteria?

If Action is weak, there are good discussions and no follow-through.

**Sequence:** If Action is weak, check Focus first, because the decision may not be clear enough to execute. If Focus is weak, check Information, because the data may not support the decision. Fix the weakest link first, since downstream links often recover.

### Step 4: Scan the six stages of check

Before blaming people or adding resources, scan these levels in order. The problem usually sits higher than it appears.

1. **Purpose.** Is the goal clear, and does everyone know what success looks like? If not, no process or tool will help.
2. **Demand.** Is there real demand in the target segment, and is the problem urgent enough to buy? If not, better execution will not fix it.
3. **Capability.** Do people have the skills, tools, and knowledge? If not, train, hire, or tool, but only after Purpose and Demand are confirmed.
4. **Flow.** Is work moving without queues, bottlenecks, or unnecessary handoffs? Measure time in each stage.
5. **System conditions.** Are data quality, configuration, integrations, and team structure supporting the work? If not, fix the infrastructure.
6. **Management thinking.** Does leadership's model of how the business works match the data? This is the hardest to fix and needs an honest conversation about what the numbers show versus what leaders believe.

### Step 5: Triage the motion

Before a full diagnosis of everything, find the motion that matters most. Ask what will move revenue most, then narrow.

- **More new business.** Is the problem generating pipeline or closing it? If closing, diagnose pipeline management first. If generating, check inbound qualified volume, then outbound meeting volume, then partner contribution if a partner motion exists.
- **Net revenue retention.** Is the problem churn or expansion? If churn, diagnose renewals: health signals, renewal process, save plays. If expansion, diagnose expansion signals, whitespace, and the handoff to sales. If both, start with churn, because expansion on a leaking base does not compound.

Common default order: pipeline management, then acquisition (inbound or outbound), then customer success, then partner. Only diagnose partner if the motion exists or is planned.

### Step 6: Check the operational layer of the motion

For the priority motion, find the layer that is broken:

- **Fundamentals.** The process does not exist or is not in the system. Fix: define, document, and implement. Typical effort: two to four weeks.
- **Adoption.** The process exists but people do not follow it. Fix: reporting, coaching, and management cadence. Typical effort: four to eight weeks.
- **Optimization.** People execute, but no one can measure or improve it. Fix: analytics, attribution, and conversion tracking. Typical effort: eight to twelve weeks.
- **Acceleration.** The team wants to scale what works, but it is manual. Fix: automation and advanced tooling. Typical effort: twelve weeks or more. Invest here only when the three layers beneath are solid.

Output: the priority motion, the stuck layer, the effort estimate, and the next step, which is a full diagnosis of that motion.

### Step 7: Audit the alignment of incentives

Pick the top executive goal. Walk each function and ask four questions: what metric do you own that contributes to this goal, how is it measured, how often is it reviewed, and is it in your compensation? A function that cannot answer all four has an alignment gap.

Example: executive goal of raising net revenue retention. If sales compensation is entirely new-logo, if customer success is measured only on satisfaction scores, and if marketing is measured on lead volume, nobody is paid to move retention. Behavior follows what is measured, visible, reviewed, and paid. If the metric is not visible, reviewed regularly, and tied to compensation, it will not move. Change the metric set and the compensation together, or the change will not hold (see `gtm-compensation`).

### Step 8: Find the constraint and write one A3-lite

**The constraint principle.** Every system has one constraint that limits it more than anything else. Improving anything else is activity without leverage. Ask: if we removed only this constraint, would revenue rise? If yes, it is the constraint. If not, keep looking.

Two quick tests:
- If pipeline volume doubled tomorrow, would revenue double? If not, the constraint is downstream of volume.
- If sales headcount doubled tomorrow, would revenue double? If not, the constraint is pipeline quality or process efficiency, not capacity.

**The A3-lite.** One page, five fields:

```
PROBLEM:        A specific, measured problem. Not "pipeline is bad" but
                "win rate fell from 25% to 16% in Q3 for mid-market."
CURRENT STATE:  The facts from data. Not opinions.
ROOT CAUSE:     Traced with the IFA check, the six stages, or five whys.
COUNTERMEASURE: One specific change. Not "improve qualification" but
                "add an economic buyer contact requirement to the
                Proposal stage entry, enforced as a required CRM field."
OWNER, DATE,    Who implements, by when, and how we will know. Include the
CHECK, STOP:    metric, the measurement date, and the stop-rule: the level
                at which the countermeasure is abandoned.
```

**Five whys.** Keep asking why until you reach a systemic cause that, if fixed, would prevent recurrence. Write each answer down, keep answers factual, and stop when a cause is systemic and actionable. Three whys or seven are both fine. If an answer names a person, ask one more why: is it training, incentive, process, or tooling?

**Decision rights.** For each recurring decision that causes confusion, name one Driver, one Approver (only one person), the Contributors, and the Informed. Decisions without a single approver stall.

### Step 9: Propose a two-week experiment

Turn the countermeasure into the smallest change that gives a fast signal. Define the metric, the baseline, the expected movement, and the stop-rule. Run it, then decide to scale, adjust, or stop.

### Advanced checks

**Capacity or productivity.** Low pipeline volume with normal win rates is a capacity problem: add sources. Adequate pipeline with low win rates is a productivity problem: fix qualification, process, and coaching. High activity with low win rates is activity without output. Check whether prospecting is producing qualified meetings, and move the effort toward the inbound or referral sources that qualify better.

**The data-forecast-coaching loop.** Revenue management runs on a loop: clean data produces reliable forecasts, which support coaching, which changes rep behavior, which improves data capture. The most common break is between data quality and forecasts, because inconsistent stage definitions make the forecast untrustworthy, managers stop using it, and coaching drifts away from reality. If that link is broken, fix definitions and data first, then rebuild the forecast model.

**Integration architecture.** Assess integration as a possible root cause when it is a recurring pain. Ask:
- How many systems hold their own copy of customer data? Three or more usually means definitions drift.
- How many direct system-to-system integrations exist? A count above roughly ten is a review trigger, since point-to-point connections multiply maintenance.
- When a metric definition changes, how many places must be updated? More than one means definitions live in code or in individual reports, not in a shared layer.
- Can a new tool access customer data without a bespoke integration project?

The usual pattern is a central system with many point-to-point integrations around it. Fixing the individual integrations treats symptoms; a shared data foundation treats the cause. Thresholds are defaults to calibrate.

**AI maturity.** Audit where AI sits in the revenue workflow, in four levels:

- **Level 1, none.** No generative AI or agents. Forecasting, scoring, and enrichment are manual or rule-based. Start with the workflow where value is easiest to measure, usually lead scoring or enrichment.
- **Level 2, tactical.** AI in one workflow, with manual handoffs and no feedback loop. Capture outcomes (won or lost, contacted or not) and feed them back before adding a second workflow.
- **Level 3, embedded.** Two or more AI-driven steps in sequence, governed by approval thresholds and audit trails. Add anomaly detection and explainability for decisions that affect people.
- **Level 4, agentic.** Agents act on next steps with human oversight at decision gates. Requires Level 3 governance and clean data first.

Constraint check: if the client is at Level 1 and the data is poor, the constraint is data and governance, not AI adoption. Fix those first.

Where AI influences decisions about employees, such as territory allocation or performance-related scoring, record the use and take counsel's view on transparency and consultation obligations before go-live. These are points for counsel, not legal advice.

### Weakest-dimension rule

A revenue engine runs at the level of its weakest dimension. Before adding effort, automation or headcount, find the dimension that limits the rest. Score each dimension on evidence: ask to see the artifact behind it, such as the ICP document, the scoring model, a live sequence, a duplicate count or the notes from the last review. A capability that cannot be shown is not credited.

### Diagnostic questions

1. What exactly is the symptom, in one measured sentence, and who first noticed it?
2. Which layer does the symptom live in, and what evidence says the constraint is one layer away?
3. Which of the three information, focus, and action links is weakest, and what decision did it block last month?
4. If the top three revenue metrics doubled, would anyone's compensation change? Name the function that cannot answer.
5. What is the win rate and the coverage in the segment under discussion, and which of the two constrains output?

## Output

- The layer where the symptom appears, and the layer where the constraint sits.
- The information-focus-action read, with the weakest link named.
- The priority motion, the stuck layer, and the effort estimate.
- The alignment gaps found in the audit.
- One A3-lite, with owner, check, and stop-rule.
- One two-week experiment, with its metric and kill criterion.

## Quality bar

The diagnosis names one constraint, shows the evidence, and proposes one countermeasure with a stop-rule. Watch for fixes proposed before the layer is located, several initiatives launched at once, blame placed on individuals without a why-chain, and a diagnosis that ends with "more of everything".
