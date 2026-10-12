---
name: conversion-feedback-to-ad-platforms
version: 1.0.0
status: draft-for-review
description: Use when an ad platform is optimising for form fills rather than pipeline, and the team wants the platform to receive later funnel stages (marketing-qualified, opportunity, and closed-won) from the CRM through a server-side connection. Sets the event hierarchy by lifecycle stage, the choice between a native sync and a middleware route, the deduplication of browser and server events, and the match-quality check. Not for tracking conversions that happen on a third-party page (see off-domain-conversion-tracking).
sources:
  - "Conversions API and funnel events for B2B paid social (MIT, Ivan Falco): the principle to optimise on qualified pipeline rather than form fills, the CRM lifecycle stages as the event source, one server event per lifecycle stage with a priority set in the platform, the deduplication of browser and server events, the preference order between a native CRM sync and middleware, and the match-quality threshold"
  - "Removed: the named CRM, the named middleware, the named platform's event manager, and the example match-quality score. Compliance hashing is restated in general terms"
  - "Adapted for GTM-360: the stage list is the recommended hierarchy, and the match-quality threshold is an author default. The rule to hash personal data before it leaves the company is kept as a hard rule"
---

# Conversion feedback to ad platforms

## Purpose

An ad platform optimises for whatever conversion it is told about. If it is told only about form fills, it finds people who fill in forms, many of whom never become customers. Sending later funnel stages back, from the CRM, lets the platform learn which audiences reach pipeline. This skill sets how that feedback is built and checked.

## When to use

- The platform optimises for leads, but sales reports that the leads do not progress.
- Paid campaigns are judged on cost per lead while the business judges on cost per opportunity.
- A CRM holds reliable stage data that the ad platform cannot see.

Route elsewhere when:

- The conversion happens on a page the company does not control. Use `off-domain-conversion-tracking`.
- The question is which audiences to build from the data. Use `paid-social-audience-strategy`.
- The question is the data model in the CRM. Use `gtm-data-architecture`.

## Inputs

- The CRM lifecycle stages and when each is set.
- The ad platform's event settings and the pixel already installed on the site.
- The contact fields available for matching, such as email, phone, and the platform's click identifier.
- The choice of connection route: native sync, middleware, or a custom backend.

## Event hierarchy

Send one server event per lifecycle stage the business cares about:

| Event | When it is sent | Purpose |
|---|---|---|
| Lead | A contact enters the first form or demo request | Volume at the top of the funnel |
| Marketing-qualified lead | The contact becomes qualified | Qualified intent |
| Opportunity | A deal is created | Pipeline, a strong optimisation target |
| Customer | A deal is closed-won | Revenue, best for value optimisation |

In the platform's event settings, rank the event the campaign should optimise for above browser page views and other events.

## Procedure

1. **Name the optimisation target.** Choose the stage whose volume is high enough to learn from and whose quality matters most. Opportunity is often the right choice for B2B. Lead is often too broad.
2. **Send each stage from the CRM**, so the stage data is the source of truth, and not a copy typed in by hand.
3. **Run the browser pixel and the server events together,** with a shared event identifier, so the platform counts each conversion once. Check the deduplication rate after launch.
4. **Choose the route:**
   - Native sync from the CRM is preferred when it sends the matching fields for all stages and the match-quality score is acceptable.
   - Middleware is needed when match quality stays low, when the business must hash personal data itself, when more than one destination is required, or when custom rules apply, such as sending only deals above a set value.
5. **Hash personal data before it leaves the company,** in the format the platform specifies. Never send plain personal data to a third party.
6. **Check match quality** in the platform after launch. A score of about six out of ten or more is a reasonable default floor. Below it, the match fields need work.
7. **Confirm the loop.** Test that a stage change in the CRM appears as an event in the platform within the expected time.

## Output

- The event hierarchy, with the optimisation target named.
- The connection route, with the reason.
- The deduplication and match-quality checks, and their results.

## Quality bar

The optimisation target is a stage, not a form fill. Each event comes from a CRM stage change. Browser and server events share an identifier. Personal data is hashed before sending. Watch for a campaign that optimises for leads while the business reports on opportunities, server events that double count, and plain personal data sent to a third party.
