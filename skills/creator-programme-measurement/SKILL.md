---
name: creator-programme-measurement
version: 1.0.0
description: "Use to measure and report the return on a B2B creator programme in a way a finance reviewer can check. Sets the attribution window for creator-sourced traffic (longer than paid ads), the view-through effect that direct-response habits miss, the separation of creator traffic from other channels, the funnel from spend to closed-won, the payback calculation, and the week-one leading indicators. Not for the strategy (see creator-programme-strategy) or the paid channel measures (see paid-measurement-scorecard)."
---

# Creator programme measurement

## Purpose

Creator spend often looks worse than it is, because the measures used for paid ads undercount creator influence. A buyer reads, saves, and asks a colleague before they click, and the click is credited to nothing. This skill fixes the attribution first, then measures the funnel, so the return can be defended to a finance reviewer.

## When to use

- A creator programme needs its return reported to leadership or finance.
- Creator attribution looks poor, and the team is considering cutting the programme.
- A new creator programme needs its measures set before launch.

Route elsewhere when:

- The question is the strategy or tier. Use `creator-programme-strategy`.
- The question is the paid channel measures. Use `paid-measurement-scorecard`.
- The question is the forecast of creator pipeline. Use `paid-search-unit-economics` for the arithmetic.

## Inputs

- Creator posts and their dates, with each creator's tracking link or code.
- Spend per creator and in total.
- The CRM funnel from click to closed-won, with a field that marks creator-sourced records.
- A holdout or before-and-after baseline, to measure view-through lift.
- The attribution window, set before the data is read.

## Fix the attribution first

Correcting three things often changes reported return substantially without any change in spend:

- **Window.** Use a longer window than for paid ads, typically fourteen to thirty days. Creator-sourced clicks reach a qualified lead more slowly, because buyers read, save, and consult colleagues first. Set the window before the data is read.
- **View-through.** Creator posts drive traffic that never credits to the post. Measure the lift with a holdout or a before-and-after comparison, rather than accepting the undercount.
- **Separation.** Keep creator-sourced traffic in its own bucket, not in organic social, so the programme's effect is visible.

## Measure the funnel

Use the standard path: spend, qualified clicks, marketing-qualified leads, sales-qualified leads, opportunities, and closed-won.

Define a qualified click in behavioural terms: tracked to the site, and a minimum time on site set by the team. Use the same definition as the performance deal, if there is one.

## Payback and leading indicators

- **Payback period:** the time from spend to cumulative closed-won revenue covering the spend. Show it as a curve, so the reviewer can see when it crosses.
- **Week-one indicators:** qualified clicks, saves, and direct visits to the site from the creator's post in the first week. These show whether a creator is working before the pipeline arrives.

## Procedure

1. **Set the window, view-through method, and separation** before the data is read.
2. **Define the qualified click** the same way across creators.
3. **Build the funnel** from spend to closed-won, one row per creator, with the window applied.
4. **Calculate payback** and show the curve.
5. **Report the leading indicators** from week one, with the caveat that they are early.
6. **Write the reasoning** alongside the result: the window used, why it was chosen, and what the uncorrected figure would have been.

## Output

- The attribution settings and the reason for each.
- The funnel by creator, with closed-won and payback.
- The leading indicators for the first week.
- A note on how the figure changes if the attribution settings change.

## Quality bar

Attribution settings are fixed before the data is read. The window is long enough for the buyer's timeline. View-through is measured, not assumed. Creator traffic is separated. The report shows reasoning, not only the result. Watch for a seven-day window used for creator content, creator traffic credited to organic social, and a payback figure with no curve.
