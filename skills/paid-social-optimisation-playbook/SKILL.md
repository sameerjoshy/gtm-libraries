---
name: paid-social-optimisation-playbook
version: 1.0.0
status: draft-for-review
description: Use to diagnose and fix a live paid social campaign for a high-value B2B offer. Sets the decision rhythm (no judgement on less than seven days of data), three diagnosis paths (cost per action rising, click-through falling, lead quality poor), a kill, optimise or scale rule, a learning-phase rule for what resets delivery, and a swap rule that never pauses an ad without a replacement ready. Not for the first launch (see paid-social-launch-checklist) or for the account-wide audit (see paid-account-audit).
sources:
  - "Meta Ads optimisation playbook (MIT, Ivan Falco): the seven-day rule for judgement, the diagnosis order for rising cost per action (tracking first, then frequency and creative fatigue, then learning phase), the diagnosis of falling click-through and of poor lead quality, the kill, optimise and scale criteria, the rules that reset learning, the consolidation advice, and the 80/20 rule for campaign management"
  - "Meta Ads operating system (MIT, Ivan Falco): the swap rules (never pause without a replacement, with the replacement timed by the reason for the swap), the rule to redirect budget to proven ads when the pipeline is empty, and the weekly decision cadence"
  - "Removed: the platform benchmark tables for 2025 to 2026, the seasonal cost swings, the named platform's delivery labels and relevance scores, and the platform's placement and format claims. Benchmarks are not restated because they could not be verified"
  - "Adapted for GTM-360: every threshold is an author default to calibrate against the account's own history. The rule that a campaign is judged against the team's own target cost per action, not a benchmark, is an author addition"
---

# Paid social optimisation playbook

## Purpose

A live paid social campaign changes every day, and teams often act on the noise. They change the audience, the budget or the creative in response to a dip, which restarts delivery and kills campaigns that were working. This playbook sets the order of diagnosis, the rule for when to act, and the rule that stops a team from pausing an ad before it has a replacement.

## When to use

- Cost per action has risen above target, and the team needs to know why.
- Click-through has fallen from its own baseline.
- Leads are arriving but do not match the buyer.
- A campaign needs a kill, optimise or scale decision.

Route elsewhere when:

- The campaign has not launched. Use `paid-social-launch-checklist`.
- The question is the whole account. Use `paid-account-audit`.
- The question is the creative concept. Use `ad-creative-as-filter` for the angles.

## Inputs

- Daily results for each campaign, ad set and ad over at least the last fourteen days: spend, reach, frequency, click-through, cost per action, and actions that reached the CRM.
- The target cost per action, and the baseline click-through for each campaign.
- The learning history: changes made to audience, budget, creative and optimisation event, with dates.
- Lead quality data from the CRM: role, company size and email type for each lead.

## Procedure

### Rhythm

1. **No judgement on less than seven days of data.** Daily swings are normal. Changes made every two to four days because a figure dipped are the most common way to kill a working campaign.
2. **Decide on a fixed day each week.** Use the same review point every week. Act on what the window shows, not on the last day.

### Diagnose a rising cost per action

When the cost per action runs about twenty percent or more above target for two or more consecutive days, work through these in order:

1. **Check tracking first.** Confirm the pixel fires on the completion event, and that the server-side events are sending. A broken conversion path looks like a cost problem.
2. **Check frequency and creative fatigue.** Cold frequency above about four, or click-through down about twenty percent from baseline, points to fatigue. Prepare replacement creative now. Frequency between three and four is a warning.
3. **Check the learning phase** (below). A campaign that has just been changed is still learning, and its cost will swing.

### Diagnose falling click-through

Work through these in order. Most often the cause is the first:

- **Creative fatigue.** Cold frequency above about two and a half, or the same ads running for two weeks or more. Rotate creative. A campaign with only one or two concepts needs three or four new ones.
- **Audience exhaustion.** A small audience with high frequency, or the same audience running for a month or more. Widen the audience or build a new segment.
- **Format.** All static, or all video. Test the other format.
- **Message.** Check whether the offer still fits the market. Make the copy more specific to the buyer.

### Diagnose poor lead quality

Leads with the wrong role, the wrong company size, or a personal email address, or leads who do not recall signing up, point to one of these:
- **The form.** Ask for a work email, and add one or two qualifying questions.
- **The targeting.** The audience is too broad or includes people outside the buyer group.
- **The offer.** The offer attracts curiosity rather than intent. Change the offer before the audience.

### Kill, optimise or scale

- **Kill now** if the campaign has no conversions after roughly five to ten times the target cost per action, if frequency is high with falling results, or if it has not left the learning phase after about fourteen days. Author defaults.
- **Optimise** if the cost per action is within twenty to thirty percent of target but inconsistent, if click-through has plateaued, or if lead quality is mixed. Fix in this order: creative, audience, budget or bid, landing page, offer.
- **Scale** only when all of these hold: at least fifty conversions a week for two consecutive weeks; the cost per action at or below target for three consecutive days; frequency below about three; and lead quality confirmed in the CRM, not only in volume.

### Learning phase

- Delivery is unstable while the platform learns. Budget for enough conversions per ad set per week. As a planning default, around fifty, verified against the platform's current guidance.
- These changes reset learning: a change of audience, a budget increase of more than about thirty percent at once, a new creative asset, a change of optimisation event, and a change of bid strategy.
- These do not: a budget change under about ten percent, a copy change to the headline or description, and a pause of under a day.
- If the campaign is stuck, either raise the budget, or optimise for an earlier event such as landing-page views or form starts. Consolidate ad sets: one ad set with a larger budget learns faster than several small ones.

### Swap rule

- **Never pause an ad without a replacement ready.** Pausing without replacing shrinks the campaign, and the pipeline falls with it.
- Time each replacement by the reason for the swap. As author defaults: a delivery failure is replaced immediately with a different hook or format, since iterating on it rarely works. A low-quality result is replaced within about forty-eight hours, with ICP language added. A cost above about one and a half times the target is replaced within about forty-eight hours with a different hook or call to action.
- If the pipeline is empty, move budget to the proven ads first. The replacement must be live within seven days at most.

### Keep the 80/20 rule

About a fifth of campaigns usually produce most of the qualified pipeline. Identify that fifth. Pause the rest entirely rather than trimming their budgets. Put about a fifth of the budget into new concepts, tested in controlled batches, not in scattered launches.

## Output

- The diagnosis for each flagged campaign, with the path taken and the evidence at each step.
- A kill, optimise or scale decision for each, with the rule it met.
- The swap list: which ad is replaced, why, and the date the replacement goes live.
- The learning-phase changes to avoid, and any consolidation proposed.
- The next review date.

## Quality bar

No decision is made on less than seven days of data. Tracking is checked before creative. Every pause has a replacement. Scale decisions meet all four conditions. Watch for a campaign changed every few days, a budget raised past the learning threshold in one step, and an ad paused with nothing ready to take its place.

## Rules

- Judge only on seven or more days of data.
- Check tracking before changing creative or audience.
- Never pause an ad without a live or ready replacement.
- Do not reset learning without a reason the decision record can show.
- Measure against the team's own target cost per action, not a benchmark.
