---
name: paid-automation-controls
version: 1.0.0
status: draft-for-review
description: Use when deciding whether and how to let an ad platform automate targeting, placements, creative, and budget for a B2B lead campaign, or when a manual campaign is being compared with an automated one. Explains how automation changes the levers (creative and conversion data matter more than targeting inputs), the layers a platform may automate, what to keep constrained, when manual control still wins, and the B2B lead-quality features to switch on. Not for the campaign structure in the testing phases (see paid-social-campaign-structure).
sources:
  - "Automated delivery for B2B SaaS on paid social (MIT, Ivan Falco): the shift from manual targeting to creative and conversion data as the main levers, the four layers a platform may automate (audience, placements, creative, and full campaign automation), the B2B lead features (work email validation, phone verification, and lead filtering), and the view that targeting inputs become suggestions rather than limits"
  - "Removed: the named platform products and their launch dates, the platform's cost claims, and the product names for each layer, which are replaced by generic layer descriptions"
  - "Adapted for GTM-360: the rule to automate only after the audience and creative are proven is an author addition consistent with the three-phase structure. The threshold at which manual control is kept is an author default"
---

# Paid automation controls

## Purpose

Ad platforms increasingly choose the audience, placements, creative combinations, and budget themselves. For B2B, this changes what a team controls: the creative and the conversion data it sends matter more than the targeting it chooses. This skill sets when to let the platform automate, what to keep fixed, and which lead-quality features to turn on.

## When to use

- A team is deciding whether to move from manual campaigns to automated ones.
- Automated campaigns are performing, but the team does not know which part is working.
- A B2B lead campaign needs better lead quality from the platform's own forms.

Route elsewhere when:

- The question is the three-phase structure. Use `paid-social-campaign-structure`.
- The question is the audience data. Use `paid-social-audience-strategy`.
- The question is the lead form design. Use `lead-form-quality`.

## What changes under automation

Targeting inputs such as audiences, lookalikes, and interests become suggestions. The platform expands beyond them when it predicts better results. The levers that remain with the team are:
- the creative it supplies, which the platform uses as a signal of who to reach,
- the conversion events it sends back, which tell the platform what success looks like.

The question shifts from "who do I target" to "what creative do I supply, and what outcome data do I send back".

## The layers a platform may automate

1. **Audience:** the platform widens or redirects the audience from the inputs given.
2. **Placements:** the platform chooses where ads run, across the surfaces it owns.
3. **Creative:** the platform builds combinations from the assets supplied, adjusting by placement and segment.
4. **Full campaign:** the platform controls targeting, budget allocation, creative, and placements together.

Each layer can be switched on separately. Turn on one layer at a time and watch its effect on the lagging outcome.

## B2B lead features

Where the platform offers lead features for business audiences, consider switching on:
- **Work email validation,** so people must enter a business address rather than one auto-filled from a personal profile.
- **Phone verification,** to reduce fake or mistyped numbers.
- **Lead filtering,** to pre-qualify before a form is submitted.

Check the effect on cost per lead and on the share of leads sales accepts. Lead filtering can raise cost per lead while lowering cost per qualified lead, so judge it on the qualified figure.

## When manual control still wins

- The offer is high-value and the sales cycle is long, so a few qualified leads matter more than volume.
- Conversion data sent back is thin or unreliable, so the platform is learning from the wrong outcome.
- The audience must be tightly bounded, for example for an account-based campaign.
- The automated results cannot be attributed to any single change.

## Procedure

1. **Check the prerequisites:** the audience has been validated and the creative is proven. If not, keep the manual structure.
2. **Confirm the conversion data** sent back is the qualified stage, not just the form fill.
3. **Turn on one automation layer** and record the baseline first.
4. **Judge the change** on the qualified cost, after a set period.
5. **Keep the layer** only if the qualified result holds. Otherwise return to manual for that layer.
6. **Review the lead features** and judge them on cost per qualified lead.

## Output

- The decision to automate or stay manual, with the reason.
- The layers switched on, and the baseline and result for each.
- The lead features in use, and their effect on qualified cost.

## Quality bar

Automation layers are switched on one at a time against a recorded baseline. Judgement is on the qualified outcome. The prerequisites are checked first. Watch for full automation switched on before the audience or creative is proven, lead filtering judged on raw cost per lead, and automated results reported without a baseline.
