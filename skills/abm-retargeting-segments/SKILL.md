---
name: abm-retargeting-segments
version: 1.0.0
description: "Use to segment and sequence retargeting for known target accounts, by recency and depth of engagement, with a priority order and a monthly budget split by segment. Covers the buying committee as a retargeting segment, the recency and frequency matrix, the engagement depth scores, and the setup of audiences before any campaign runs. Not for the campaign level (see abm-campaign-level-choice) or for the audience attributes (see linkedin-audience-targeting)."
---

# ABM retargeting segments

## Purpose

Retargeting for a known account is not the same as retargeting a website visitor. It targets people at accounts already in the ICP, it reaches different roles with different messages, and it coordinates ads with outreach. This skill segments that retargeting by recency and depth of engagement, sets the priority of each segment, and sets the budget split between them.

## When to use

- A programme has target accounts that have engaged and then stalled.
- Retargeting is running as one undifferentiated audience and needs segments.
- A team is deciding how to split a monthly retargeting budget.

Route elsewhere when:
- The question is the campaign level. Use `abm-campaign-level-choice`.
- The question is the audience attributes and exclusions. Use `linkedin-audience-targeting`.
- The question is turning engagement into outreach. Use `ad-engagement-outbound-triggers`.

## Inputs

- The target accounts, with their contacts and roles.
- Engagement data by account and person, with dates: site visits, ad clicks, content engagement, webinar attendance.
- Visits to high-intent pages, such as pricing or demo pages.
- Lost and churned opportunities, with their dates.
- The monthly retargeting budget.

## Procedure

1. **Set up the audiences before any campaign runs.** Retargeting audiences only collect people from the moment they are created. Build the segments in step 2 before launch, or the early engagement is lost.
2. **Define the core segments:**
   - Recent engagers: engaged within the last two weeks.
   - Warm traffic: engaged 30 to 90 days ago and not converted.
   - Page-specific visitors: visited pricing, demo or case study pages in the last 30 to 60 days.
   - Content engagers: downloaded content, watched video or attended a webinar in the last 60 to 90 days.
   - Company list, not yet engaged: known accounts with no engagement.
   - Buying committee: several contacts at the same account.
   The windows are the source's defaults.
3. **Set the priority and the budget share.** As defaults, recent engagers take 30 to 40 percent of the monthly budget, page-specific visitors 25 to 30 percent, warm traffic 20 to 25 percent, content engagers 10 to 15 percent, and company-list accounts 5 to 10 percent. Adjust to the team's results.
4. **Score depth of engagement.** Count touchpoints per account. One or two is light, and the message is awareness content. Three to five is moderate, and the message is solution content. Six to ten is heavy, and the message is conversion content. Ten or more is a hot account, and it goes to outreach with a direct offer.
5. **Apply the recency and frequency matrix.** Recent engagers with five or more visits go to the sales development team as a priority. Recent engagers with one visit get nurture. Older accounts that were hot and have gone quiet get a win-back message. The matrix cuts are defaults.
6. **Map the buying committee.** Give each role at the account a message that fits its part in the decision, and avoid showing the same ad to every contact.
7. **Coordinate with outreach.** Ads, email and direct outreach run to a shared sequence, so one account does not receive conflicting messages on the same day.

## Output

- The segment list, with each segment's definition, window and purpose.
- The priority order and the budget split, with the defaults marked.
- The depth scores and the message type for each band.
- The recency and frequency matrix, with the action for each cell.
- The setup checklist, with the audiences to be built before launch.

## Quality bar

Every segment has a definition, a window and a purpose. The budget split is labelled as a default or the team's own. Audiences exist before the campaign starts. Watch for one undifferentiated retargeting audience, a win-back message sent to accounts still in an active sales cycle, and ads that contradict the outreach.

## Rules

- Set up retargeting audiences before launch. They are not retroactive.
- Label the windows, shares and cut-offs as defaults unless they come from the team's own data.
- Coordinate ads with outreach on a shared sequence.
- Do not send a win-back message to an account with an open deal.
