---
name: abm-campaign-level-choice
version: 1.0.0
status: draft-for-review
description: "Use to choose how to run an account-based paid campaign at the right level: one named account (1:1), a named list of about ten to twenty accounts (1:few), or a segment of many accounts (1:many). Sets whether to target by company list or by contact list, splits mixed lists into homogeneous segments so large accounts do not absorb the budget, checks how many of the list's accounts are actually reached, and caps frequency per account. Not for the budget arithmetic (see abm-strategy-planner) or for the choice of audience attributes (see paid-social-audience-strategy)."
sources:
  - "LinkedIn ABM at 1:1, 1:few and 1:many (MIT, Ivan Falco): the three campaign levels and their targeting methods, the preference for company lists over contact lists and the reasons, the rule to split a mixed list by size so that large accounts do not take the budget, per-company reach reporting and the action when an account is not reached, the structure for each level, the building of account lists from closed-won, late-stage pipeline and intent sources, the check that a company has enough members to reach, and the frequency and exclusion rules"
  - "Removed: the named platform's list minimums and audience-size floors, its benchmark performance comparisons, its named reporting screens, and its named exclusion feature. Platform minimums must be checked against the platform's current rules before any list is built"
  - "Adapted for GTM-360: the frequency target (about four impressions a week per person in a target account) and the impression threshold for exclusion are the source's defaults, kept as defaults to calibrate. The rule that reach is checked per account before the budget is judged is kept as a hard rule"
---

# ABM campaign level choice

## Purpose

An account-based campaign can be run at three levels, and the choice decides the targeting method, the budget per account and the reporting. A large, mixed list uploaded as one campaign usually sends most of the budget to the easiest-to-reach accounts and leaves the rest untouched. This skill chooses the level, builds the lists so each segment gets a fair share, and checks reach account by account.

## When to use

- A named account programme is about to start, and the team has to choose between one account, a named list or a segment.
- A list has been uploaded, and some accounts receive no impressions.
- Frequency within target accounts is rising, or a few decision-makers are seeing the ads too often.

Route elsewhere when:

- The question is how much budget the programme needs. Use `abm-strategy-planner`.
- The question is which audience attributes to use. Use `paid-social-audience-strategy`.
- The question is whether a reach figure is a frequency problem. Use `paid-audience-reach-diagnostic`.

## Inputs

- The target account list, with each account's size band, sector and stage.
- The objective: the single strategic account, the named programme, or the vertical.
- The budget per month, and the expected deal value per account.
- The contacts known at target accounts, and whether their emails are verified.
- Closed-won and late-stage pipeline data, to build the list.

## Procedure

1. **Choose the level:**
   - 1:1, for one strategic account where the deal value justifies a high cost per account. Target the company directly. Run decision-maker and influencer messages, and coordinate timing with sales.
   - 1:few, for a named list of about ten to twenty accounts. Upload a company list, split it into homogeneous sub-lists, and run an awareness campaign and a retargeting campaign for each.
   - 1:many, for a vertical or segment. Use a broad company list, layer on job function and seniority, and split by region or size as the campaigns grow.
2. **Prefer company lists to contact lists** for most programmes. Company lists are easier to obtain, match more reliably, and need less upkeep, because people change jobs faster than companies change names. Use a contact list only for named decision-makers whose business emails are verified, and expect to update it often.
3. **Split mixed lists by size or segment.** As a default, split enterprise, mid-market and small accounts into separate lists and campaigns, with a budget per account that suits each group. Segmenting by sector, region, pipeline stage or revenue tier also works.
4. **Check that each account has enough people to reach.** Cross-check each company's size on the platform. Very small companies may have too few members to serve ads to. Check the platform's current audience-size rules before the list is built, since they change.
5. **Judge the budget per account.** At 1:1, a high cost per account is acceptable where the deal justifies it. At 1:few, each account needs a meaningful share of impressions. At 1:many, treat the campaign as scaled prospecting with list-based precision.
6. **Report reach per account every week.** For each account, record impressions and engagement. Where an account receives none, move it into its own campaign, so the programme does not ignore it.
7. **Cap frequency per account.** As a default, aim for about four impressions a week for each person in a target account. Allow more near a decision, up to about fifteen in thirty days. When an account passes a set impression count in a window, such as about five hundred in seven days as a starting point, exclude it temporarily, and lower or raise that threshold based on fatigue.
8. **Build the account list from the strongest sources:** the accounts behind closed-won deals, the accounts in late-stage pipeline, intent data showing active research in the category, and the customer lists of competitors where that is permitted.

## Output

- The campaign level for each segment, with the reason.
- The list structure: company or contact, split by segment, with sizes.
- Per-account reach for the last period, and the accounts moved to their own campaigns.
- The frequency cap and the exclusion rule, with the threshold used.
- The list-building sources and the validation result for each account.

## Quality bar

Each list has a stated level and a stated reason. Large mixed lists are split. Reach is reported per account, not averaged. Frequency is capped and reviewed. Watch for one campaign spending on the easiest accounts, an account list that cannot be reached at all, and a contact list that is stale.

## Rules

- Check reach per account before judging a programme's budget.
- Use company lists unless a named decision-maker needs a contact list.
- Confirm platform audience rules before building a list.
- Cap frequency for each account, not only for the campaign as a whole.
