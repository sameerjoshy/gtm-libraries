---
name: paid-optimization-signals
version: 1.1.0
description: "Use when deciding which paid media metrics justify action, when to pause an ad, and how to tell a real result from noise. Separates leading signals (fast) from lagging signals (slow), sets breakeven cost formulas from deal size and conversion rate, applies a non-performer rule and a maintenance rule, and keeps an experiment log with a hypothesis, priority, and documented result for each test. Not for the measurement set-up (see paid-measurement-scorecard) or for creative fatigue (see creative-fatigue-rotation)."
---

# Paid optimization signals

## Purpose

Once paid campaigns run, teams either overreact to noise or wait too long to act on real problems. This skill sets which signals to act on, when to act, and how to record what was learned, so decisions are repeatable and not driven by mood.

## When to use

- A campaign is live and someone asks whether to pause, scale, or change an ad.
- A team is reviewing its experiment history.
- A new metric is proposed as a reason to act.

Route elsewhere when:

- The question is whether measurement works at all. Use `paid-measurement-scorecard`.
- The question is when a creative is tired. Use `creative-fatigue-rotation`.
- The question is how far to scale. Use `paid-scaling-quadrant`.

## Inputs

- Leading and lagging results by stage, with dates.
- The experiment history: what changed, when, and what it did.
- The thresholds the team uses for action, where they are set.
- Any new metric proposed as a reason to act, with its source.

### Leading and lagging signals

- **Leading** signals arrive within a month. Use them for quick optimization.
- **Lagging** signals arrive over more than a month. Use them for the directional truth about whether the spend pays back.

Signals by stage, as defaults:

| Stage | Leading | Lagging |
|---|---|---|
| Create | Click-through rate, engagement rate | Inbound leads blended with paid |
| Capture | Cost per lead, cost per marketing-qualified lead | Pipeline per unit of spend, cost per opportunity |
| Accelerate or activate | Accounts reached, click-through rate | Average time to close, influenced revenue |
| Revive | Cost per lead, cost per qualified lead | Pipeline per unit of spend, return on spend |
| Expand | Accounts reached, click-through rate | Expansion revenue |

The key is choosing leading signals that actually move the lagging ones. Expect to change them as the data builds up.

### Breakeven costs

Breakeven cost per lead = average deal size × lead-to-won conversion rate.
Illustration: a $3,000 deal and a 10% lead-to-won rate give a breakeven cost per lead of $300.

Breakeven cost per click = target cost per lead × landing-page conversion rate.
Illustration: $300 × 5% gives a breakeven cost per click of $15.

Use the company's own figures. The illustrations are not benchmarks.

### Pause rules

1. **Non-performer rule.** Applies at any time. Pause a new ad that has spent two to three times the target cost per lead with no conversions. Example: target $300, spend of $600 to $900 with no conversions, pause.
2. **Maintenance rule.** Applies after seven to fourteen days, depending on volume. Pause an older ad whose cost per lead is one and a half to two times target. Example: target $300, current $450 to $600, pause.

These rules are not statistically significant. They are repeatable, easy to follow, and they stop emotional decisions. Say so when the rules are presented.

### Proxy metrics

A proxy metric is a leading signal that stands in for a lagging outcome. A good proxy is stated as: the percentage of customers or users who do at least a minimum action within a set period.

A good proxy is:
- measurable from data the team holds,
- moveable by changes the team makes,
- not an average, because a small group can distort an average,
- correlated with the high-level engagement measure,
- split between new and existing customers,
- hard to game.

First show the proxy correlates with the outcome. Only then treat it as causal.

### Experiment log

- Keep a backlog of ideas and a sprint of approved experiments.
- Write each hypothesis as: if we do X, then we believe Y, as measured by Z.
- Prioritize with RICE: reach, impact, confidence, and effort, each scored one to five, with effort scored so that lower effort scores higher.
- Record each completed experiment: what was tested, the result (success, failure, or inconclusive), the learnings, the budget spent, and the channel and creative used.
- Avoid the activity trap: test to learn, not for the sake of testing. Build each test on the documented learnings.

## Procedure

1. **Name the decision** the signal is meant to inform.
2. **Pick the leading signal** for that decision from the stage table, and confirm it moves the lagging signal.
3. **Apply the pause rules** to individual ads before deciding about the campaign.
4. **Log the experiment** with its hypothesis, priority, and planned measure before it runs.
5. **Record the result** when it ends, including inconclusive results.

## Output

- The signal chosen, and the reason it leads the lagging outcome.
- Any pause decisions, with the rule applied and the figures.
- The experiment log entry, and the documented result for any finished test.

## Quality bar

Every action names the signal and the rule behind it. Pause rules are applied to the figures, not to impressions. Experiments have a written hypothesis and a documented result, including inconclusive ones. Watch for pauses on a single day's data, proxy metrics that are averages, and tests run without a hypothesis.
