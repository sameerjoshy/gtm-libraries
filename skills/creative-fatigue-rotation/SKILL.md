---
name: creative-fatigue-rotation
version: 1.2.0
description: "Use when a paid ad creative is losing effect and needs rotation, for B2B paid campaigns. Sets out the warning signals (frequency, click-through decline, rising cost per thousand impressions, and low relevance diagnostics), frequency thresholds by campaign type, a weekly detection routine with a classification for each ad, typical creative lifespans, and a rotation mix. Not for writing new creative (see `ad-copy-voice-of-customer`)."
---

# Creative fatigue and rotation

## Purpose

An ad that worked in its first week often stops working by the fourth. The audience has seen it, stopped reacting, and the platform keeps serving it at rising cost. This skill catches fatigue early, classifies each ad, and sets a rotation so the team always has fresh creative in market.

## When to use

Run this when any of these are true:

- A weekly paid optimization review is due.
- Cost per result is rising with no change in the offer or targeting.
- A campaign has been running unchanged for several weeks.
- A creative refresh needs planning.

Route elsewhere when:
- The question is writing the new creative. Use `ad-copy-voice-of-customer`.
- The question is the pause rules for cost per lead. Use `paid-optimization-signals`.
- The question is measurement setup. Use `paid-measurement-scorecard`.

## Inputs

- Daily results per ad over the last several weeks: frequency, click-through, cost per thousand impressions, and cost per result.
- The baseline click-through for each campaign.
- Relevance diagnostics, where the platform reports them.
- The current creative inventory and the age of each asset.

## Procedure

Work the weekly routine in order, using the thresholds and lifespans below.

### Signals, in order of urgency

| Signal | Default threshold | Urgency |
|---|---|---|
| Frequency above the critical level for the campaign type | See the frequency table | Urgent |
| Click-through rate down 20% or more from baseline over seven days | Creative dying | Warning |
| Cost per thousand impressions up 30% or more over two weeks | Delivery getting harder | Warning |
| Any relevance diagnostic rated below average | Quality issue | Warning |
| Cost per result rising with stable targeting | Likely fatigue, after other causes ruled out | Monitor |

### Frequency thresholds

Frequency is the average number of times one person has seen the ad.

| Campaign type | Safe | Warning | Critical |
|---|---|---|---|
| Cold prospecting | 1.0 to 2.5 | 2.5 to 3.5 | Above 4.0 |
| Retargeting | 2.0 to 4.0 | 4.0 to 5.5 | Above 6.0 |
| Account-based | 2.0 to 5.0 | 5.0 to 7.0 | Above 8.0 |

Account-based audiences tolerate more repetition because they are small and the message is intentional. Even so, returns fall past five or six impressions per person per week.

### Creative lifespans

Typical lifespans, as defaults:

| Creative type | Typical lifespan |
|---|---|
| Static image | 14 to 28 days |
| Short video (under 30 seconds) | 21 to 35 days |
| Carousel | 21 to 35 days |
| Customer testimonial or user-generated style | 28 to 42 days |

B2B audiences are smaller, so frequency builds faster, but they also give each ad less attention. For most B2B campaigns, plan a refresh every 14 to 21 days.

### Weekly detection routine

1. **Pull frequency** for each ad over the last seven and fourteen days, and flag any above the threshold for its campaign type.
2. **Compare click-through rate** this week with the previous two weeks. A fall of 15 to 20% or more suggests fatigue. If click-through is steady but frequency is rising, schedule a refresh within seven days.
3. **Check cost per thousand impressions.** A rise with a stable audience means delivery is struggling, often an early sign before click-through falls. Check competition in the auction before blaming the creative.
4. **Check relevance diagnostics** and replace any ad rated below average.
5. **Classify each ad** using the table below.

| Classification | Criteria | Action |
|---|---|---|
| Healthy | Click-through stable, frequency below threshold, relevance acceptable | Keep running |
| Warning | Click-through declining, or frequency nearing threshold | Prepare a replacement and launch within seven days |
| Urgent | Frequency above threshold, click-through down 20% or more, relevance falling | Replace within 24 to 48 hours |
| Depleted | Running four weeks or more, frequency above 5.0, results well below baseline | Pause. Do not iterate. The concept is exhausted. |

### Rotation mix

Keep the active creative library split:

- 50% proven winners, currently performing and being scaled,
- 30% iterations on winners, the same angle with a new hook, format, or design,
- 20% new concepts, to replace the winners when they fatigue.

### Rotation steps

1. **Run the weekly routine** on every active ad.
2. **Set the replacements** for every warning and urgent ad, from the 30% and 20% pools.
3. **Pause depleted ads** and record the concept as exhausted so it is not relaunched unchanged.
4. **Check the mix** against the 50/30/20 split each week.

## Output

- The classification of every active ad, with the signals behind it.
- Replacements scheduled for warning and urgent ads, with launch dates.
- Depleted concepts recorded.
- The current library mix against the target.

## Quality bar

Every ad is classified from its signals, not from a feeling. Urgent replacements launch within two days. Depleted concepts are not relaunched unchanged. The library keeps a supply of new concepts. Watch for ads kept running on a single healthy week, fatigue blamed without checking auction competition, and a library made only of winners with nothing in the pipeline.

## Rules

- Nothing goes live without a named approver. The paid channel owner approves new creative and any change to spend before it runs.

Before you rotate creative or change spend, ask: who is the named approver releasing this?
