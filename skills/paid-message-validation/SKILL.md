---
name: paid-message-validation
version: 1.0.0
description: "Use to find which paid ad messages actually produce valuable pipeline, not just cheap clicks or leads. Launches one message per buyer situation with equal budgets, scores the first qualified conversations on urgency, budget, and fit, ranks each ad by its average quality score rather than cost per lead or click-through, and scales only the messages that pass. Use when platform metrics say an ad is a winner but sales says the leads are poor. Not for the creative angles (see ad-creative-as-filter) or the offer (see paid-offer-strategy)."
---

# Paid message validation

## Purpose

An ad that wins on click-through or cost per lead can still produce poor pipeline, and an ad that looks expensive can produce the best deals. Platform metrics do not show which messages bring buyers worth selling to. This skill validates messages on the quality of the conversations they produce, then scales only what passes.

## When to use

- The platform shows a winning ad, but sales reports poor leads from it.
- A new paid programme is launching, and the team needs to know which messages to scale.
- Budget is about to be increased on the strength of platform metrics alone.

Route elsewhere when:

- The question is the list of angles to test. Use `ad-creative-as-filter`.
- The question is the wording of an ad. Use `ad-copy-voice-of-customer`.
- The question is the audience segment. Use `paid-audience-segment-diagnostic`.

## Inputs

- The list of buyer situations the ideal customer faces, with fifteen to twenty-five as the working range.
- Live ads for each situation, with three to five formats per situation where possible.
- Qualified conversations from the campaign, with the ad each one came from logged.
- The sales team's ability to score each conversation.

## Procedure

Run the four phases in order: launch, score the conversations, rank by quality, then scale what passes.

## Phase one: launch

1. **Create one message per buyer situation.** Each situation is a different angle. Three to five ads per situation, in different formats, test the same angle.
2. **Give each situation equal budget** in the first period. Equal budgets make the comparison fair.
3. **Log each qualified conversation** against the ad it came from.

## Phase two: score the conversations

After roughly twenty qualified conversations, score each one from zero to three on each of three factors:
- **Urgency:** no urgency, to a burning problem that needs a solution now.
- **Budget:** no budget or authority, to budget approved for this category.
- **Fit:** not the ideal customer, to a perfect match.

The maximum score is nine. The person closest to the conversation scores it, and the score is logged with the ad.

## Phase three: rank by quality

1. **Compute the average quality score** for each ad, from its logged conversations.
2. **Sort the ads by average quality score,** not by cost per lead, click-through, or demo rate.
3. **Label the winners.** An ad with high quality is a winner even if its cost per lead is higher. An ad with low cost per lead and low quality is a vanity winner: it is cheap, and it wastes sales time.
4. **Keep the top ads,** typically the three strongest, and stop the rest.

## Phase four: scale what passes

Scale only messages that have passed phase three. Increase budget in steps, within the team's budget limits, and re-score new conversations as the budget grows. A message whose quality falls as budget rises has reached the limit of its audience.

## Output

- The buyer situations, the ads per situation, and the budget split.
- The scoring of each logged conversation, and the average quality per ad.
- The ranked list of ads, with winners and vanity winners labelled.
- The scaling plan for the winners, with the re-score date.

## Quality bar

Ads are ranked on quality, not platform metrics. The same people score the conversations for all ads. Vanity winners are labelled as such. Scaling starts only after the scoring. Watch for a budget raised on cost per lead alone, scores given by different people for different ads, and a winner that loses quality as budget rises.
