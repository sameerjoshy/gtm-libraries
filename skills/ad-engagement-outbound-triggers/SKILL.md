---
name: ad-engagement-outbound-triggers
version: 1.0.0
description: "Use to turn engagement with account-based ads into outbound triggers. Structures campaigns so that engagement reveals intent, sets stage thresholds that decide when a sales development rep should act, defines what the alert contains, personalises outreach to the topic the account engaged with rather than the channel, sequences the ads and the outbound over the first twelve weeks, feeds sales learning back into the ads, and measures the lift against the team's own cold baseline. Not for the choice of campaign level (see abm-campaign-level-choice) or for general signal detection (see signal-detection-and-timing)."
---

# Ad engagement outbound triggers

## Purpose

Account-based ads that reach known accounts also show which of those accounts are paying attention. Cold outreach often gets low replies, while outreach to accounts that have already engaged usually does better. This skill turns that engagement into a trigger, so sales time goes to accounts that have shown interest, and the first message refers to the topic that caught their attention.

## When to use

- Account-based ads are running, and sales wants a trigger for outreach.
- Outreach to accounts that have not engaged is getting low replies.
- A team wants to know whether ad engagement predicts meetings.

Route elsewhere when:

- The question is how to structure the campaign by level. Use `abm-campaign-level-choice`.
- The question is which signals to detect in general. Use `signal-detection-and-timing`.
- The question is which play to run for a prospect with a specific event. Use `signal-outbound-plays`.
- The question is writing a single cold email. Use `outbound-cold-email`.

## Inputs

- The active account-based campaigns, with their names and their topics.
- Engagement data per account and per campaign: impressions, clicks and engagements, with dates.
- The stage definitions the team uses, and the owner of each stage.
- The contacts known at each account, with their roles.
- Sales learnings from outreach, and the cold-outreach baseline for comparison.

## Procedure

1. **Name campaigns by intent.** Group the campaigns by the buyer need or problem they address, and name each campaign with its intent, format and stage. An account's engagement then reveals what it cares about, not only how much it engaged.
2. **Separate the two kinds of engagement data:**
   - quantitative: counts of impressions, clicks and engagements, which show how deep the interest is;
   - qualitative: which campaigns an account engaged with, which show what it cares about.
   The qualitative data is what makes the outreach relevant.
3. **Set stage thresholds** that decide when an account moves from ad awareness to active interest. As defaults: five or more clicks, or ten or more engagements, moves an account to interested. Accounts that have only seen ads are not handed to sales.
4. **Define the alert.** Send the rep the account name and profile link, its fit score and tier, the intent tags, the change in engagement over the recent window, the key contacts, and a suggested angle based on the campaign it engaged with.
5. **Personalise to the topic, not the channel.** Refer to the subject the account showed interest in, such as a comparison, a feature area or a case study. Never tell a buyer that they clicked an ad. Lead with their problem, and keep the message short, because the ad has already warmed them.
6. **Sequence the motion over about twelve weeks:**
   - weeks one to four: awareness ads only, with no outreach;
   - weeks four to eight: interested accounts trigger outreach, and ads move towards solution content;
   - weeks eight to twelve: accounts that book a demo are worked by the rep and the account executive together, and ads show case studies and proof;
   - after twelve weeks: measure pipeline per unit of spend, by intent.
   For outreach, use several touches across channels, spread over about ten days, as a default.
7. **Feed sales learning back into the ads.** When prospects repeatedly raise a pain point, a competitor or an objection, create a campaign around it. If personas respond differently, shift budget towards the ones that reply.
8. **Measure the signal, against your own cold baseline:**
   - reply rate from engaged accounts against cold outreach, and the lift between them;
   - meeting rate, engaged against cold;
   - days from interested to demo, with a target of under about fourteen as a default;
   - pipeline from engaged accounts, against pipeline from cold sources;
   - whether the intent tag matched the buyer's real need, as judged by the rep.

## Output

- The campaign naming and intent structure.
- The stage thresholds and the owner of each stage.
- The alert format, with an example for one account.
- The outreach sequence, with the personalisation for each intent.
- The sequence timeline and the feedback loop to the ads.
- The measurement against the cold baseline, with the lift shown.

## Quality bar

Outreach begins only at interested stage, not at seen. Every message refers to a topic and never to a click. Lift is shown against the team's own cold baseline. Sales learning reaches the ads. Watch for a rep contacting accounts that only saw an ad, a message that says an ad was clicked, and a claimed lift without a cold comparison.

## Rules

- Hand accounts to sales only at the interested stage or above.
- Never tell a buyer that they clicked an ad.
- Refer to the topic the account engaged with, not the channel.
- Report the lift against your own cold baseline, not a benchmark.
