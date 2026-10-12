---
name: paid-audience-reach-diagnostic
version: 1.0.0
description: "Use to judge whether paid ads are reaching a target audience or account list well enough and often enough, using penetration (share of the list reached) and frequency (average impressions per reached person). Always reads frequency over a ninety-day basis, judges warm and cold audiences by different measures, separates a saturated pool from a narrow source, and turns each verdict into a specific fix. Use when someone asks whether they are over-serving, whether the audience is too small, or how often people see an ad. Not for who converts (see paid-audience-segment-diagnostic)."
---

# Paid audience reach diagnostic

## Purpose

Frequency and penetration are two of the most misread numbers in paid ABM. Teams panic at a healthy frequency, or they under-serve a warm pool while believing they are saturating it. This skill sets the right window and the right benchmark for each audience, then turns each reading into an action.

## When to use

- Someone asks whether the team is over-serving an audience.
- Someone asks whether an audience is too small to be worth the spend.
- A campaign's results have fallen, and reach is a suspect.
- A list-based campaign needs a reach check before it scales.

Route elsewhere when:

- The question is which segments convert. Use `paid-audience-segment-diagnostic`.
- The question is the account as a whole. Use `paid-account-audit`.
- The question is creative fatigue on a single ad. Use `creative-fatigue-rotation`.

## Inputs

- Reach and frequency for each campaign: impressions, unique people or accounts reached, average frequency, and the date window.
- The size of each audience pool, and the total addressable audience for each, such as all site visitors in the window or the full account list.
- The funnel stage and placement format for each campaign.

## Definitions

- **Penetration** is the share of the target audience reached at all: unique people or accounts reached divided by the total addressable audience. It answers how much of the list has been touched.
- **Frequency** is the average number of impressions per reached person over a window. It answers how often each person sees the ad.

## Procedure

1. **Normalise the window.** Convert any shorter window to a ninety-day basis before judging it. Do not compare a seven-day figure with a ninety-day band.
2. **Classify each audience by role:**
   - warm or retargeting,
   - cold prospecting,
   - right-rail or lower-attention placements.
3. **Judge frequency by role.** As defaults:
   - Warm and retargeting in-feed: a target of about fifteen to twenty-five over ninety days. Below about ten, the pool is under-served. Above about thirty with falling click-through, it is fatigued.
   - Cold in-feed: low and wide, roughly under three to five. Judge cold audiences on penetration, not frequency.
   - Right-rail: tolerates much higher exposure, because each impression carries less weight.
4. **Judge penetration.** A cold audience with low penetration is not saturated. It is under-reached. A warm audience with high penetration may be saturated.
5. **Separate a saturated pool from a narrow source.** A saturated pool has been reached widely and often, so more spend adds little. A narrow source is small by design, so the fix is to widen the source, not to lower frequency.
6. **Turn each verdict into a fix:**
   - under-served warm pool: raise budget or widen the source, and check the pool has enough people;
   - fatigued warm pool: refresh creative or cap frequency;
   - saturated cold pool: widen the audience or add a new source;
   - narrow source: widen the source definition before changing spend.
7. **Check each fix** against the bands at the next review.

## Output

- For each audience, the ninety-day frequency and penetration, with the band it falls in.
- The verdict: under-served, healthy, fatigued, saturated, or narrow.
- The specific fix for each verdict, and the review date.

## Quality bar

Every frequency figure is on a ninety-day basis. Cold audiences are judged on penetration. A saturated pool and a narrow source get different fixes. Watch for a weekly frequency compared with a ninety-day band, a healthy cold audience treated as over-served, and a warm pool under-served but reported as healthy.
