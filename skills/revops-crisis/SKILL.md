---
name: revops-crisis
version: 1.0.0
status: draft-for-review
description: Use when a revenue function is in crisis, meaning several systems are failing at once and the basic machinery can no longer be trusted. Typical signals are repeated forecast misses, win rates falling for several quarters, pipeline coverage dropping, retention collapsing, data that nobody believes, or functions blaming each other. Gives a four-week emergency triage, a 30-60-90 recovery plan, four crisis playbooks, and rules for leading through the blame. Use before the diagnostic, not instead of it. Not for routine diagnosis (see revops-diagnostic).
sources:
  - "RevOps crisis triage (MIT, Rutger Katz / Neon Triforce): crisis recognition triggers, the multi-system failure pattern, the four-week emergency triage (data audit, cash diagnosis, root cause in fast mode, constraint identification), the 30-60-90 recovery plan, four playbooks (forecast, pipeline, churn, trust), the blame and confidence guidance, and the list of things not to do"
  - "Removed as unverified: the win-rate medians, retention percentiles, coverage-to-quota percentages, and forecast-variance improvement figures attributed to industry reports, and the claim that automated alerting detects crises three to five days earlier. The thresholds are kept as defaults to calibrate"
  - "Corrected: the source's pipeline playbook gave both a 2.8x trigger and a 2.1x example without a rule for choosing. This skill uses the win-rate-based required multiple, consistent with revops-strategy and revops-revenue-planning. The source's forecast playbook cited an accuracy target sourced to an analyst report, which is removed"
  - "Adapted for GTM-360: the crisis thresholds, the data completeness targets, the 2-hour cash diagnosis, the 120-day renewal lead time, and the save-call ARR threshold are defaults. Set the currency and the thresholds from the client's size"
---

# RevOps crisis triage

## Purpose

Existing diagnostic skills assume the basics work. A diagnostic is useless when the data is unreliable, and a maturity assessment is academic when the functions do not talk to each other. In a crisis, the first job is to make the machinery trustworthy enough to steer, not to understand everything.

The core rule: speed of stabilisation beats completeness of diagnosis. Find the one thing that unlocks the others, fix it, and move to the next constraint. Do not try to fix six things at once.

This skill is emergency response. Once the company is stable, move to `revops-diagnostic` for the deeper work.

## When to use

Use this skill when more than one of these is true, or when any one of them is severe:

- Forecast variance is at or above about 30% for two or more consecutive quarters.
- Win rate has fallen five or more points over three quarters.
- Pipeline coverage is below the required multiple and still falling. The required multiple is 1 divided by the win rate (see `revops-strategy`).
- Net revenue retention is below about 90%, or gross retention is at a level the business cannot survive.
- Critical deal fields are less than about 70% complete, or the CRM and finance disagree on revenue by more than about 10%.
- Three or more functions blame each other, in order.
- Two or more top performers leave in one quarter, or cynicism is open in meetings.

The thresholds are defaults for a company of mid-market size. Calibrate them to the client's history.

Route elsewhere when:

- One metric is off and the rest of the system works. Use `revops-diagnostic`.
- The question is the forecast mechanics once things are stable. Use `revops-forecasting`.
- The question is the comp plan. Do not change it mid-quarter (see the list of things not to do).

## Inputs

- Forecast history: committed, best case, and actual, for the last four quarters.
- Pipeline by stage, segment, and close date, plus coverage trend.
- Win and loss records, with reasons, for the last two quarters.
- Retention data: gross and net, by cohort and segment.
- The list of open deals closing in the next 90 days, and renewals due in the next 90 days.
- Team structure and the names of the executive owners for each function.

## Procedure

### Step 1: Confirm the crisis and name it in one line

The pattern to recognise is this: data breaks, then process fails, then people fracture, and then nobody can execute reliably. Once trust collapses, the company is in crisis mode, and normal planning stops working.

Write the crisis as one sentence with numbers. "Forecast missed by 35% for two quarters, and sales and marketing disagree on what a qualified lead is" is useful. "Things are bad" is not.

### Step 2: Week 1, audit whether the data can be trusted

If critical data is below about 70% complete, stop. Nothing else works until the data is usable.

Sample about two hundred open deals at random and check these fields against defaults to calibrate:

- Deal amount populated: target about 95%.
- Close date updated in the last two weeks: about 95%.
- Stage assigned and consistent with the activity: about 98%.
- Contact roles assigned: about 80%.
- Activity logged in the last thirty days: about 85%.
- Next step recorded: about 80%.
- Won or lost reason recorded on closed deals: about 95%.
- Customer name matches the finance system: about 99%.

Scoring:
- Below 70% on the critical fields: a data crisis. Run a five-day blitz.
- 70% to 84%: acceptable, with caveats on every forecast. Target 85% or more for reliable execution.
- 85% or more: good enough to forecast from, with normal care.

**The five-day blitz.** Day 1: sort deals by completeness, and find the teams and reps with the worst records. Work out whether the cause is effort, unclear definitions, or a tool fault. Days 2 and 3: RevOps and the CRM administrator make bulk corrections from objective sources, and reps update their own deals. Fix validation rules that are blocking good entries. Days 4 and 5: start a fifteen-minute daily data stand-up, publish a weekly audit, and name a data owner for each team.

### Step 3: Weeks 1 and 2, protect cash first

In a crisis, the first question is what revenue is at risk in the next few months. Do this in two hours:

1. List open deals closing in the next thirty to sixty days, and renewals due in the next thirty to ninety days.
2. Rank them by amount.
3. Flag each one at risk if any of these holds: no recent activity, no champion, a competitor in the deal, or no economic buyer engaged.
4. The top ten at-risk deals are the downside exposure. Give that figure to leadership.
5. Assign an executive owner to each. A CRO or VP, not the deal owner.
6. Set the next concrete action and a date. "This week," not "soon."

Start a daily cash stand-up on the first working day of week two. Fifteen minutes, with the CRO, the head of sales, the head of customer success, and RevOps. One line per deal: status, next action, owner, and date. Run it for sixty days, then review whether it is still needed.

### Step 4: Weeks 2 and 3, find the root cause quickly

Scan the six stages of check in fast mode, one day each. The full method is in `revops-diagnostic`.

- **Day 1, purpose.** Is success defined, and do the targets conflict?
- **Day 2, demand.** Is there real demand in the target segment, and is the ICP still right?
- **Day 3, capability.** Do the skills, tools, and structure match the motion being run?
- **Day 4, flow.** Pick twenty random deals and track where they stall.
- **Day 5, system conditions and thinking.** Is the data trusted? Are stage exit criteria defined? Does leadership's view of the business match the numbers?

Write a one-page root cause summary:

```
CRISIS:       One line, with the numbers
EVIDENCE:     The data that proves it is real
ROOT CAUSE:   Purpose / Demand / Capability / Flow / System / Thinking (mark the broken ones)
IMMEDIATE FIX: The one thing that unblocks the rest
OWNER:        A named person
TIMELINE:     One to three weeks
```

### Step 5: Weeks 3 and 4, identify the constraint

Score each of four areas from 1 to 2. Crisis scoring is coarse on purpose. Nuance comes later.

- **Governance.** Are decisions being made, and does a steering mechanism exist?
- **Enablement.** Do the data, process, and tools work together?
- **Revenue engine.** Is sales or customer success producing outcomes?
- **Customer insight.** Does the company know its ICP, and why it wins and loses?

The emergency constraint is the area scoring 1 while the others score 2. If all four score 1, start with governance, because the company needs a steering mechanism before anything else.

Unlock logic, one action per constraint:
- **Governance at 1.** Install a daily stand-up and name one decision driver (usually the CRO). The unlock is that leadership knows what matters.
- **Enablement at 1.** Complete the data audit from week one, and define three non-negotiable processes. The unlock is that teams can execute consistently.
- **Revenue engine at 1.** Analyse win rate, and speak to five recent lost deals quickly. The unlock is knowing where to focus: discovery, closing, or multi-threading.
- **Customer insight at 1.** Pull the five best and five worst recent outcomes, and look for patterns. The unlock is that the company stops guessing about its ICP.

## The 30-60-90 recovery plan

### Days 1 to 30: stabilise

- Data audit complete, with the blitz run if needed.
- Top ten at-risk deals named, each with an executive sponsor.
- Daily cash stand-up running.
- Root cause identified, with the broken stage named.
- First structural fix in place: stage criteria, validation rules, or a governance step.
- One visible quick win, however small.
- All non-essential projects paused.

### Days 31 to 60: diagnose and fix

- Full diagnostic complete, using `revops-diagnostic`.
- Capability maturity assessed.
- A fix roadmap with no more than three initiatives, ranked by the constraint each one unlocks.
- The first structural change designed, with stakeholders mapped.
- Change management started, using `revops-change-management`.
- A weekly leadership update: what broke, and how it is being fixed.
- Day-one baselines measured again: data quality, forecast accuracy, and win rate.

### Days 61 to 90: rebuild

- The first structural change at about 70% adoption.
- Initiatives two and three in design, not yet launched. Do not launch three at once.
- An operating cadence in place: a weekly operations review of about thirty minutes, a monthly deep-dive of about ninety minutes, and a quarterly reset. Use `revenue-operating-cadence`.
- The forecast rebuilt on a sound method (`revops-forecasting`).
- A metrics dashboard live and trusted (`revenue-metrics`).
- A team pulse check that shows trust improving.
- Handover to `revops-diagnostic` for the deeper work.

## Four crisis playbooks

### A: The forecast crisis (missed several quarters running)

Common root causes:
1. Bad data: amounts missing, close dates stale, stages wrong.
2. Sandbagging: deals entered late, pipeline hidden.
3. Inflated pipeline: stalled deals still counted, no stage exit criteria.
4. Method: forecasts built on rep confidence, not on history.

Emergency fix, weeks one and two:
- Build a shadow forecast from the CRM, validated against finance.
- Compare it with the current forecast. A variance above about 15% points to a data problem.
- Run three methods: rep probability, historical conversion, and high-confidence deals only.
- Take the lowest of the three as the realistic number, and say so.
- Ask each day: how many deals closed that were, or were not, in the forecast?

Structural fix, weeks three to eight: define stage exit criteria, choose the forecast method (start conservative, then blend once there are two clean quarters), run weekly deal inspection on every deal in qualified stages, and measure accuracy monthly. A target band of plus or minus 10% within two to three quarters is a reasonable default.

### B: The pipeline crisis (coverage falling)

Common root causes:
1. Top of funnel has dried up.
2. ICP drift: many leads, few that convert.
3. Account executives are not prospecting from their own accounts.
4. Qualification is too strict and rejects good opportunities.
5. Deals are stuck early, and capacity is full of discovery.

Emergency fix, weeks one and two: audit pipeline by coverage, source, and velocity. Then follow the branch that matches the evidence:
- Top of funnel: reactivate dormant prospects and refocus development reps on outbound.
- ICP drift: pull ten wins and ten losses, and identify the attributes that separate them.
- Passive account executives: list high-usage existing customers and build an expansion list.
- Qualification too strict: run a blind review of twenty rejected leads, and see how many a good rep would have pursued.
- Slow velocity: run a manager sweep of every deal stalled over sixty days.

Structural fix, weeks three to eight: a pipeline generation plan with named source owners and weekly accountability. Enforce the ICP score on every lead, with a stated threshold for what counts as a qualified lead. Set velocity targets by stage from the client's history. Plan the pipeline needed as the target divided by the win rate, with a buffer, as a starting formula (see `revops-revenue-planning` for the coverage method).

### C: The churn crisis (retention collapsing)

Common root causes:
1. Product no longer fits the market, or a competitor is ahead.
2. Customer success is under-resourced, onboarding is weak, and support is slow.
3. No health scoring, so churn is a surprise.
4. The renewal process starts too late and depends on one contact.
5. Acquisition quality: the company is winning customers who will not stay.

Emergency fix, weeks one and two:
- Diagnose the churn: rate by cohort, timing, stated reason, and segment.
- Flag every account renewing within ninety days that shows two or more risk indicators: no activity for thirty days, declining usage, unresolved tickets, or no contact for sixty days.
- Hold an executive save call for each at-risk account above a set ARR threshold. The CRO or a VP makes the call, not the account manager.
- Match the quick fix to the pattern: a senior customer success manager on the highest-risk accounts; a simple health score built this week from five to seven indicators; renewal conversations started at about 120 days, not 30; and a pre-close check on acquisition quality.

Structural fix, weeks three to eight: a health scoring system with escalation rules, a renewal calendar visible 120 days ahead, a customer success coverage model by segment, and a monthly list of expansion signals. Use `cs-operations` and `renewal-save-motion`.

### D: The trust crisis (functions blame each other)

Root cause: no shared metrics, no shared cadence, and no shared accountability. Each function optimises its own numbers, the numbers conflict, and the blame cycle follows.

Emergency fix, weeks one and two:
- One shared dashboard that every function sees daily: ARR, pipeline, churn, and acquisition cost.
- A shared definitions session with all the vice presidents. Ask "what is a qualified lead?" and agree one definition per handoff. Write it down as a rule.
- One weekly meeting of forty-five minutes: CRO, heads of sales, marketing, and customer success, and RevOps. Metrics, open issues, actions from last week, and actions for next week.
- A one-to-one with the loudest voice in each function: "What would need to be true for you to trust this team?" Then fix that specific gap.
- A visible quick win: fix one handoff, such as adding sales input to lead scoring.

Structural fix, weeks three to eight: a shared metrics dashboard owned by RevOps, a one-page definition for each major concept, a weekly governance meeting with a decision log, and cross-functional playbooks for the main motions. Use `revenue-operating-cadence` and `revenue-handoffs`.

## Leading through the crisis

### The blame cycle

Each function will say the others caused it. Sales says marketing sent poor leads. Marketing says sales did not follow up. Customer success says the product is broken. Product says sales over-promised. Blame protects turf, and it feels like control.

What to do:
- **Describe it as a system.** In the first leadership meeting, say plainly that the miss came from unreliable data and unclear process, and that every function owns part of that.
- **Show the data.** Display the audit results. Problems stated as numbers are harder to argue with than opinions. "Thirty percent of open deals have no close date" is a process gap, not a character flaw.
- **Name the constraints separately.** If demand, velocity, and retention all fell, those are three problems. Fix them in order, not by assigning blame.
- **One owner per crisis phase.** The CRO owns the forecast crisis. The head of customer success owns the churn crisis. Everyone else executes.

### Rebuilding confidence

Confidence breaks when forecasts miss, the board worries, people fear for their jobs, and the best performers start interviewing elsewhere. Rebuild it in four ways:
- **Show progress daily.** Call out small wins at the stand-up. Momentum matters more than size.
- **Share the plan.** Give the full team the 30-60-90 plan, the order of work, and where things stand. People trust plans they can see.
- **Get senior people on deals.** When the CRO or CEO calls a customer or a prospect directly, reps feel supported. In a crisis this is one of the strongest levers.
- **Credit structural wins.** When stage criteria or a new pipeline source goes live, name it and say why it matters.

### Difficult conversations

Address these early:
- An underperforming rep the whole team already knows about. Deal with it in week two, not week six. Ambiguity damages morale.
- A manager who is part of the problem, such as one hoarding deals or not coaching. Raise it one to one, immediately.
- A function blocking progress, such as product holding up an integration or finance delaying data access. Escalate the constraint to the executive who can move it, and keep the conversation on the constraint, not the person.

How to run them:
- Focus on the constraint. "We need real-time deal visibility within two days. What do you need from RevOps to make that happen?" rather than "You are not being transparent."
- Ask for a binary commitment: "Can you deliver X by this date, yes or no?" In a crisis, a maybe delays the timeline.
- If someone refuses a crisis priority, bring in their manager or the CEO. A crisis is not the time for building consensus.

## Things not to do in a crisis

- Do not change compensation plans mid-quarter. It adds chaos to chaos. Lock it, and announce changes for the next period.
- Do not fire the head of sales straight away. Most failures in a crisis are system failures. Run the diagnostic first. If it is a people problem, two weeks of evidence will show it.
- Do not buy a new tool. Technology does not fix a broken process.
- Do not launch ten initiatives. Scattered focus makes a crisis worse. Fix one thing hard.
- Do not hide the numbers from the board. They will find out. Show the bad numbers and the plan together.
- Do not blame the market. External conditions explain the variance, but they do not fix revenue.
- Do not drop the daily stand-up. It is the main way information reaches leaders. Keep it for sixty days.
- Do not fix data, process, and people at the same time. Pick one. Data first, then process, since clean data makes process work visible. Then people, since trust rebuilds once the data and process hold.

## How to use this skill

**"Everything is broken."** Recognise the crisis, run the four-week emergency triage, then the 30-60-90 plan.

**"The forecast cannot be trusted."** Playbook A: shadow forecast, then pattern identification, then the structural fix.

**"There is not enough pipeline."** Playbook B: audit the composition, find the root cause, and activate the branch that matches the evidence.

**"We are losing customers."** Playbook C: at-risk identification, executive save calls, then the structural customer success fix.

**"The teams do not trust each other."** Playbook D: shared dashboard, shared definitions, then the weekly meeting.

**"The data is unusable."** Run the week-one data audit before anything else. Nothing else works until the data does.

**After day ninety.** Hand off to `revops-diagnostic` for the deeper analysis. Crisis work stabilises. Long-term improvement needs a different approach.

## Output

- The one-line crisis statement with evidence.
- The data audit scores, with the blitz plan if needed.
- The top ten at-risk deals, each with an executive owner and a dated action.
- The root cause summary, with the one immediate fix.
- The emergency constraint and its unlock action.
- The 30-60-90 plan with owners.
- The playbook applied, with its fix in weeks one and two.

## Diagnostic questions

1. Which metric crossed the crisis line, and for how many quarters?
2. What share of the critical deal fields are populated today, and who is accountable for that number?
3. What is the executive-level downside: the value of the top ten at-risk deals and renewals?
4. Which function is blaming which, and what single shared metric would they all accept?
5. What is the one thing that, if fixed this week, would unlock the most?

## Quality bar

The crisis is named with numbers. The data is trusted enough to steer by. The top at-risk revenue has named executive owners and dated actions. One constraint is being fixed at a time, with an owner. Watch for several initiatives launched together, comp changes during the quarter, blame without a system view, and a plan that skips the data audit.
