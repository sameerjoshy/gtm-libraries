---
name: revenue-operating-cadence
version: 1.0.0
description: "Use to design or fix the revenue meeting system: the rhythm from daily pulse to board meeting, what each meeting decides and who attends, the data each one needs and who builds it, the board deck structure, the anti-patterns that waste meetings, and an asynchronous version for distributed teams. Covers meeting structure and inputs, not forecast methodology (see revops-forecasting) or metric definitions (see revenue-metrics)."
---

# Revenue operating cadence

## Purpose

The rhythm of meetings decides whether a company runs revenue on evidence or on firefighting. Each meeting should produce a decision, a logged action, or both. A meeting that does neither should become an email. The cadence rests on a data pyramid: clean activity data feeds pipeline, pipeline feeds the forecast, and the forecast feeds the board. If the base is wrong, everything above it is wrong.

## When to use

- Meetings are status updates and nothing is decided.
- The board is surprised by numbers it should have seen earlier.
- Actions from meetings are forgotten within days.
- A distributed team needs the same accountability without constant calls.
- A new revenue leader is setting up the rhythm.

Route elsewhere when:

- The question is how to build the forecast. Use `revops-forecasting`.
- The question is which metrics to track. Use `revenue-metrics`.
- The question is whether the CRM data is trustworthy. Use `revops-data-governance`.

## Inputs

- The current meeting calendar, with attendees and purpose for each meeting.
- The CRM views and reports that exist today, and who builds them.
- The stage model and forecast categories in use.
- The board's reporting expectations and calendar.
- How the team works: co-located, distributed, or mixed.

## Procedure

### Step 1: Check the data base first

Every decision depends on activity data that is logged accurately. Audit that before designing any meeting.

- Who is logging activities, and are they logged on time?
- Are stage changes real, or made at random?
- Does every open deal have an owner, a next step, and a close date?

Monthly, run an audit: take a sample of open deals and check each one against the record. If the sample fails, fix the logging before adding more reporting.

### Step 2: Answer seven questions for every meeting

Before a meeting is scheduled, it must have answers to these.

| Element | Question | Weak answer | Strong answer |
|---|---|---|---|
| Purpose | What decision does it produce? | "Check on things" | "Lock the forecast by Friday noon" |
| Frequency | How often, and why? | "Weekly, because we always have" | "Weekly for accountability, monthly for trends" |
| Participants | Who must attend? | "The whole team" | "Sales managers and the CRO. RevOps attends in writing." |
| Inputs | What preparation is needed? | People arrive unprepared | A forecast model and deal-aging report, sent 24 hours before |
| Agenda | How is time spent? | Wandering | Fifteen minutes of data, thirty of decisions, five of actions |
| Outputs | What leaves the room? | "We will work it out" | A logged forecast and actions with owners |
| Accountability | Who follows up? | Nobody | An action log with owners and due dates |

Rule: if a meeting produces no decision and no logged action, replace it with an email.

### Step 3: Set the rhythm

The default structure, from most frequent to least:

**Daily pipeline pulse (15 minutes, team level).** Surface blockers, and coordinate same-day wins. Each rep names one deal that is stuck, one that has moved, and any help needed. RevOps is not required in the room, but the CRM views should make the data available without asking.

**Weekly pipeline review (45 minutes per team, sales manager and team).** Inspect deal progress, find stalled deals, and set the week's commit.

- Pre-read from RevOps: stage movement over seven days, deal aging by stage (a deal with no movement for 14 days is flagged), forecast accuracy against last week, and win and loss summary.
- Agenda: context from the manager (5 minutes), review of deals older than seven days and risky deals (30 minutes), commit against best case for the week (5 minutes), and logged actions with owners and dates (5 minutes).
- Output: each rep's updated forecast, recorded in the CRM.

**Weekly forecast roll-up (30 minutes, CRO, sales managers, and RevOps).** Aggregate the teams into a company view and identify the gap to plan.

- Pre-read: consolidated forecast, variance to plan, confidence by stage, and the top ten at-risk deals.
- Output: a locked company forecast, and an action log for closing the gap.

**Fortnightly funnel review (60 minutes, marketing, sales, customer success, and RevOps).** Diagnose where the funnel is leaking.

- Pre-read: conversion by stage against baseline, lead-to-opportunity speed, lead quality, bottlenecks, and win rate by segment and region.
- Output: owners for the cross-functional actions, and experiments to run, such as changing lead routing to speed opportunities.

**Monthly business review (90 minutes, leadership, RevOps, and finance).** Review performance against plan, spot trends, and give small steers.

- Pre-read: eight to ten slides at most. Revenue against plan, pipeline health, efficiency, retention and expansion, what is working in go-to-market, risks and escalations, and asks.
- Rule: no more than one chart per slide. If five charts are needed to explain a point, the point is not yet understood.

**Quarterly review (half day, leadership).** Assess strategy execution, make major steers, and adjust the plan.

- Inputs: full-year performance against plan, pipeline trends, customer health and cohort analysis, efficiency trends, market shifts, and team capacity against target.
- Agenda: revenue health, go-to-market performance, pipeline and forecast confidence, customer and retention, what is working and what is not, and steers on resources.
- Output: an updated quarterly plan, a board deck draft, and resource decisions.

**Quarterly board meeting (two to three hours).** Governance and accountability.

Board deck, eight to ten slides:

1. Summary and the decisions needed from the board. Lead with the narrative in three bullet points.
2. Revenue against plan, with the bridge from starting to ending recurring revenue, and the variance explained as a story.
3. Pipeline and forecast: coverage, cycle-time trend, win rate by segment, and confidence in this quarter's number.
4. Efficiency: acquisition cost, payback, lifetime-to-acquisition ratio, burn multiple, and the Rule of 40, with quarter-on-quarter trends.
5. Retention and expansion: net and gross retention, cohort trends, the main churn reasons with actions, and expansion trends.
6. Go-to-market update: what is working, what is broken and the fix in progress, competitive shifts, and experiments running.
7. Strategic initiatives: status, timeline, key risks and mitigations, and resource needs.
8. Asks: votes required, budget requests with the expected return, and decision dates.

Golden rules for the deck: lead with the narrative, not the data. Show trends, not snapshots. Put risks and asks early. Use no more than three metrics per slide. Connect every number to the strategy.

RevOps builds the data foundation. The CEO or CRO owns the narrative.

### Step 4: Name the data owner for each ceremony

| Ceremony | Must-have data | Built by |
|---|---|---|
| Daily pulse | Deal status, activity log | Sales teams |
| Weekly pipeline review | Stage movement, deal aging, forecast accuracy | RevOps |
| Weekly forecast roll-up | Consolidated forecast, variance to plan, confidence | RevOps |
| Fortnightly funnel review | Conversion, velocity, bottlenecks | RevOps and marketing |
| Monthly business review | Revenue, pipeline, efficiency, retention | RevOps and finance |
| Quarterly review | Full business dashboard | RevOps |
| Board meeting | Summary and KPI deck | RevOps builds the data, the CEO writes the narrative |

### Step 5: Remove the anti-patterns

| Anti-pattern | Cost | Fix |
|---|---|---|
| Meetings without a pre-read | Fifteen minutes of every meeting spent reading slides | Send slides 24 hours ahead. Questions already answered on slide two go back to the reader. |
| Reviews without actions | Decisions made Monday, forgotten by Wednesday | Log every action with an owner, a date, and a success measure. Review the log at the start of the next meeting. |
| Forecast as negotiation | "I'll commit to 95% but it could be 110%" makes the forecast useless | Keep the forecast analytical. Commit, best case, and at-risk are data, not bargaining positions. |
| Dashboard theatre | Forty metrics shown, five matter, the board is confused | Three to five metrics per meeting. Each number must connect to a decision. |
| Cadence without accountability | Actions slip and priorities are not priorities | Name the owner, publish the date, review at the next meeting, and escalate what is not done. |
| Unvalidated activity data | Everything above the base is unreliable | Audit the CRM each month, as in Step 1. |

### Step 6: Run it asynchronously, if the team is distributed

Not every team can meet weekly. An asynchronous version keeps the accountability.

| Ceremony | Mode | How |
|---|---|---|
| Daily pulse | Async | A written thread. Each rep posts wins, blockers needing escalation, and one forecast update. |
| Weekly pipeline review | Async, with an optional decision call | RevOps posts the pre-built report by Monday morning. Team comments on risky deals in the thread. A thirty-minute call is optional, or decisions go in the log. |
| Weekly forecast roll-up | Synchronous, compressed to 15 minutes | The CRO reads the thread, then confirms or adjusts the forecast and assigns actions. Pre-read 24 hours ahead. |
| Monthly business review | Synchronous, 60 minutes | One hour of asynchronous preparation in the thread, then a meeting that goes straight to decisions. |
| Quarterly review | Synchronous, full day | Too many decisions to log asynchronously. Pre-reads are still required. |

Decision log: capture each decision at the end of an asynchronous review, with the decision, owner, due date, success measure, and status. The thread is the accountability record. Pin the previous log at the top of each new review, and start by checking what was completed, not by repeating open items.

Recorded updates work well for distributed teams. A short recorded video from the CRO each week, covering where the team stands against plan, the gap, and the response, replaces most of the live forecast status. Board pre-reads can be a short video, with questions answered in writing and the live call used for decisions.

When async breaks down: if more than 20% of the team have not contributed to a decision thread by its deadline, move the decision to a synchronous call. Deal escalations get a 24-hour synchronous slot. Live crisis decisions do not wait in a thread overnight.

## Output

- The meeting calendar, with each meeting's purpose, attendees, inputs, agenda, outputs, and owner.
- The data owner and the due time for each pre-read.
- The decision log template, for synchronous or asynchronous use.
- The board deck outline, with the three metrics per slide the company will use.
- The list of anti-patterns found in the current cadence, with the fix for each.

## Quality bar

Every meeting produces a decision or a logged action, and no meeting survives without one. Pre-reads go out in time. Actions have owners and dates, and are reviewed at the next meeting. The board is not surprised by a number it could have seen earlier. The data base is audited, not assumed. Watch for status meetings, forecast negotiation, dashboards with more numbers than decisions, and an async thread that nobody reads.
