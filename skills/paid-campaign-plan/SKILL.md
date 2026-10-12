---
name: paid-campaign-plan
version: 1.0.0
status: draft-for-review
description: "Use to plan a paid campaign end to end before anything is launched, so that objectives, channels and budget, targeting, creative, and measurement are fixed in advance. Sets out the four elements every plan needs, a naming convention that makes later reporting possible, and the choice between doing the setup in-house and outsourcing it. Not for choosing the channel (see paid-channel-selection) or for the creative copy (see ad-copy-voice-of-customer)."
sources:
  - "Campaign planning and execution (MIT, Ivan Falco): the four essential elements of a campaign plan (names and objectives, channels and budget, locations and targeting, creative and copy), the naming convention built from region, stage, awareness, objective, and persona, and the DIY and outsourced execution options with the advice on bulk import for large campaign counts"
  - "Removed: the named platforms, the bulk-import tool names, and the freelance marketplace names. The naming convention is kept as a pattern"
  - "Adapted for GTM-360: the naming pattern is a recommendation, and the example values are illustrative. The rule to lock the plan before launch is a hard rule in this library"
---

# Paid campaign plan

## Purpose

Campaigns that are launched first and planned later produce data nobody can read. Campaign names are inconsistent, targeting drifts, and nobody can say afterwards what a campaign was meant to test. This skill fixes four things before launch so that the campaign can be measured and reported.

## When to use

- A new paid campaign is about to be built.
- A set of existing campaigns cannot be reported on consistently.
- A team is deciding whether to run the setup in-house or hand it to someone else.

Route elsewhere when:

- The question is which channel to use. Use `paid-channel-selection`.
- The question is the spend split across stages. Use `paid-budget-by-stage`.
- The question is the audience definition. Use `ad-persona-framework`.

## Inputs

- The objective and the stage the campaign addresses.
- The channels chosen and the budget for each.
- The target geography and the ICP definition.
- The offer and the creative brief.
- The measurement the team will use to judge the campaign.

## The four elements

1. **Campaign names and objectives.** Name each campaign with a convention, and state its purpose in one sentence. The name is what makes later reporting possible.
2. **Channels and budget.** State the budget available, the channels to be used, and the amount for each.
3. **Locations and targeting.** State the geographies and the audience definition. Reference the ad persona document rather than restating it.
4. **Creative and copy.** State the message and the formats. Reference the copy brief.

Each channel has its own targeting logic (keywords for search, audiences for social), but the planning steps are the same across channels.

## Naming convention

Use a fixed structure so every campaign can be filtered and compared:

`[Region]_[Stage]_[Awareness]_[Objective]_[Persona]`

Example: `NA_Capture_SolutionAware_Prospecting_ProductManagers`

The stage and awareness fields come from the team's demand model. Keep the list of allowed values short and fixed, so the convention holds over time.

## Procedure

1. **Fix the four elements** in writing before any campaign is built.
2. **Apply the naming convention** to every campaign and ad group.
3. **Choose the execution model:**
   - **In-house:** use the platform's bulk editing tools for more than about ten campaigns, and format the plan so it can be imported in bulk.
   - **Outsourced:** if budget exists but time does not, hire an internal performance marketer or an agency. Start with referrals before open marketplaces.
4. **Lock the plan.** Changes after launch are logged as changes to the plan, not silent edits.
5. **Set the measurement** the plan will be judged on, referencing `paid-measurement-scorecard`.

## Output

- A one-page plan with the four elements, the naming convention applied, and the execution model.
- A campaign list with names that follow the convention.
- The measurement the campaign will be judged on.

## Quality bar

The four elements are written before launch. Every campaign name follows the convention. The plan can be used to answer, months later, what a campaign was meant to test. Watch for campaigns named ad hoc, targeting that is not written down, and plans changed after launch without a record.
