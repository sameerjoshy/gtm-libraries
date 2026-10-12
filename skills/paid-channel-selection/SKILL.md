---
name: paid-channel-selection
version: 1.0.0
description: "Use when choosing which paid channels to test for a B2B offer, or when a team is spreading spend across too many channels. Groups paid channels into five families (paid social, paid search, review-listing sites, programmatic, and sponsorships), scores each against four criteria (targeting depth, media cost, reach to the ICP, and policy fit), and sequences the channels by budget and buying motion. Not for the campaign plan (see paid-campaign-plan) or the spend split across stages (see paid-budget-by-stage)."
---

# Paid channel selection

## Purpose

Most B2B teams fail with paid channels by spreading small budgets over too many platforms, so no channel gets enough data to judge. This skill narrows the choice. It checks whether a channel can reach the buyer, what it costs to reach them, whether the platform allows the category, and in what order to test.

## When to use

- A team is choosing its first paid channels.
- Spend is split across several channels with no clear reason for each.
- A new channel is proposed, and the team needs a fair way to compare it.
- Budget or sales motion has changed, and the channel mix may no longer fit.

Route elsewhere when:

- The question is the campaign structure. Use `paid-campaign-plan`.
- The question is how much to put into each stage. Use `paid-budget-by-stage`.
- The question is whether the channels a company already runs are working. Use `paid-measurement-scorecard`.

## Inputs

- The ICP, with the job titles, company sizes, and industries the offer is for.
- The available monthly budget, and the minimum budget the team can commit for a test.
- The sales motion: product-led, sales-led, or a mix.
- Any policy restrictions the category faces.

## The five channel families

| Family | What it is | Typical role |
|---|---|---|
| Paid social | Advertising inside social networks, including professional networks | Reach by role, firmographics, and interest |
| Paid search | Advertising against search queries | Capture buyers already looking |
| Paid review sites | Advertising on software review and listing sites | Reach buyers comparing options |
| Programmatic | Display, audio, connected TV, and native placements across the open web | Broad awareness, weak targeting for B2B |
| Sponsorships | Direct deals with influencers, newsletters, events, and podcasts | Credibility with a defined audience |

## Four criteria

Score each shortlisted channel on:

1. **Targeting options.** Can the ICP be described precisely enough on this channel? A channel that cannot target by role or company is weak for B2B.
2. **Media cost.** What does a click and a thousand impressions cost to reach the ICP? Get the real figure from a test, not from a published average.
3. **Reach.** How many ICP members are reachable with the targeting available? A channel with cheap impressions and a tiny reachable audience will exhaust quickly.
4. **Policy.** Does the platform allow the category without restriction? Check before any spend.

## Procedure

1. **Shortlist** the families that can plausibly reach the ICP. Drop any family the policy check rules out.
2. **Run a small test** on each shortlisted channel to measure real cost per click and per thousand impressions. Set the test budget so that a meaningful number of clicks can be measured. The aim is cost data, not results.
3. **Score each channel** against the four criteria, using the test data.
4. **Sequence the channels** by budget and buying motion:
   - A small budget should go to one or two channels with the best targeting and cost. Spreading it thinner than the test size leaves nothing to measure.
   - Search suits buyers already searching for the problem, so it often leads when demand exists.
   - Sponsorships and review sites suit a sales-led motion where buyers compare before a demo.
   - Programmatic is rarely the first choice for a narrow B2B audience.
5. **Set a review date** to decide whether to add or drop a channel, based on its cost and reach data.

## Output

- The shortlist, with each channel scored on the four criteria and the test figures used.
- The recommended first channels and the order of testing.
- The budget for each test and the date of the review.

## Quality bar

Every channel has a measured cost, not a published average. Policy is checked before spend. The first test is funded well enough to produce usable numbers. Watch for a budget spread across many channels that each receive too little to judge, and for programmatic chosen for a narrow B2B audience.
