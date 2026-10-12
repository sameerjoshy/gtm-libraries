---
name: off-domain-conversion-tracking
version: 1.0.0
status: draft-for-review
description: Use when paid ads send people to a webinar, event, or registration page hosted on a third-party platform, and the ad platform needs to see the sign-up even though it happens off the company's domain. Sets out the problem (the sign-up is invisible to a pixel on the company's own site), the two decisions (where the conversion is tracked, and how it is passed back), and the checks that the signal arrives. Not for conversions on the company's own site (see conversion-feedback-to-ad-platforms).
sources:
  - "Off-domain conversion tracking for webinars and events (MIT, Ivan Falco): the problem of a sign-up that completes on a third-party platform, the two decisions (pixel in the platform versus confirmation page on the company's site), and the rule to confirm the signal reaches the ad platform before spend scales"
  - "Removed: the named event and webinar platforms, and their settings paths. The choice is restated as a general decision"
  - "Adapted for GTM-360: the rule to confirm the signal before scaling spend is an author addition"
---

# Off-domain conversion tracking

## Purpose

A paid campaign for a webinar or event often sends people to a registration page that belongs to another platform. The sign-up completes there, so the company's own pixel never sees it. The ad platform then optimises on clicks it cannot connect to registrations. This skill sets how the sign-up is captured and passed back.

## When to use

- Paid ads promote a webinar, event, or course whose sign-up happens off the company's site.
- Campaign reporting shows clicks and landing-page visits but no registrations.
- A new event platform is being chosen for a campaign.

Route elsewhere when:

- The conversion happens on the company's own site or in its CRM. Use `conversion-feedback-to-ad-platforms`.
- The question is the offer for the event. Use `paid-offer-strategy`.

## Inputs

- The third-party platform used for registration, and whether it supports the ad platform's pixel.
- The company's landing page, and the link that sends visitors to the registration page.
- The conversion the campaign should optimise for: registration, attendance, or a later stage.
- Any confirmation page the company controls.

## The problem

1. A visitor lands on the company's page, with campaign tracking parameters attached.
2. The visitor clicks through to the registration page on another platform.
3. The sign-up completes there. The company's pixel, installed only on its own site, never fires for the sign-up.

Without a fix, the platform sees the click and not the registration.

## Two decisions

**1. Where the conversion is tracked.**
- **Pixel on the registration platform,** where the platform supports it and the company can add its pixel there. This is the most direct signal, because the sign-up is seen where it happens.
- **Confirmation page on the company's site,** where the platform does not support a pixel. The registration platform redirects to a page the company controls after sign-up, and the pixel fires on that page.

**2. How the signal is passed back.** Use the pixel signal from the chosen location. If the campaign also needs later stages, such as attendance or pipeline, pass them from the CRM as set out in `conversion-feedback-to-ad-platforms`.

## Procedure

1. **Name the conversion** the campaign will optimise for.
2. **Choose the tracking location** using the two options above.
3. **Set the registration platform** to fire the pixel or redirect to the confirmation page.
4. **Test the signal.** Register a test sign-up and confirm it appears in the ad platform's event view within the expected time, with the campaign's tracking parameters attached.
5. **Check the match.** Confirm registrations can be linked back to the campaign, so cost per registration can be calculated.
6. **Confirm before scaling spend.** Do not increase budget until the signal has been seen to arrive.

## Output

- The tracking location and the reason for it.
- The test sign-up result, and the event view check.
- The cost-per-registration measure the team will use.

## Quality bar

The conversion is tested with a real sign-up before budget is scaled. Registrations are linked to campaign parameters. Watch for campaigns scaled on click data alone, a pixel placed only on the landing page, and a confirmation page that is not reached after sign-up.
