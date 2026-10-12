---
name: creator-rate-band
version: 1.1.0
description: "Use to price a B2B thought-leadership creator from what their content actually does, not from follower count. Weights recent post performance by engagement type, cross-checks the result against a cost-per-thousand-impressions anchor, and produces an initial, budget, and maximum rate band to open a negotiation from. Use for a creator the team knows or a cold creator being priced for the first time. Not for the deal structure (see creator-deal-structure) or the reply to pushback (see creator-negotiation)."
---

# Creator rate band

## Purpose

A creator with a large following can have posts that nobody reads, and a smaller creator can have posts that start buying conversations. Pricing on followers pays for the wrong thing. This skill prices a creator on what their recent posts produce, and returns a band the team can negotiate inside.

## When to use

- A creator asks for a rate and the team has nothing to compare it with.
- A shortlist of creators needs to be priced on the same basis.
- A campaign ceiling needs to be tested against real creator costs.

Route elsewhere when:

- The question is how to structure the payment. Use `creator-deal-structure`.
- The question is the reply to a counter-offer. Use `creator-negotiation`.
- The question is finding creators. Use `creator-discovery-and-vetting`.

## Inputs

- The creator's recent post metrics: impressions, reactions, comments, and shares for a representative sample of recent posts.
- The niche, and the brand the creator would post for.
- The deliverable: a single post, or a package.
- Past closed creator deals, if the team has them, to calibrate the weights.
- The campaign ceiling for creator spend.

## Procedure

1. **Gather the inputs.** Ask for anything missing, especially the sample of recent posts. Without a sample, do not estimate.
2. **Compute average performance** across the sample: impressions, and each engagement type separately.
3. **Weight the engagement.** Comments and shares indicate attention and conversation more strongly than reactions, so weight them higher. The weights are defaults. Replace them with weights calibrated against past closed deals where the team has them.
4. **Compute a weighted-engagement value** per post, and multiply it by the number of posts in the deliverable.
5. **Cross-check with a CPM anchor.** Multiply the expected impressions by a cost-per-thousand-impressions anchor for the niche. Use the team's own figure if it has one. Where the two methods disagree widely, explain the gap before using either.
6. **Set the band:**
   - **Initial** is the opening offer, below the middle of the band.
   - **Budget** is the expected agreed rate.
   - **Maximum** is the highest rate the team will pay, and must sit within the campaign ceiling.
7. **Record the basis** for each figure, so the band can be defended in the negotiation.

## Output

- The average performance and the weighted-engagement value.
- The CPM cross-check and any gap between the two methods.
- The initial, budget, and maximum band, with the basis for each.

## Quality bar

The estimate starts from a sample of recent posts, not follower count. Engagement types are weighted separately. The cross-check is shown, with any gap explained. The maximum sits inside the campaign ceiling. Watch for a rate set from follower count, one viral post standing for the whole sample, and a maximum above the ceiling.
