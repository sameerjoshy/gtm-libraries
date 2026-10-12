---
name: linkedin-ads-audit
version: 1.0.0
description: "Use when someone wants to review, grade, or improve their own LinkedIn ad results, ABM programme, or spend over the last 30 days, for example \"audit my LinkedIn ads\", \"why is my CPC high\", \"which format is working\", \"are my ads decaying\". Produces a graded report with a prioritised fix list. Not for planning a new campaign."
---

# LinkedIn ads audit

Grades a company's own LinkedIn ad performance over the last 30 days against benchmarks, and returns a short, ranked fix list.

## Purpose

Find where money is wasted, which formats and accounts deserve more spend, and which ads are decaying. Report what the data shows, and say when it cannot show something.

## When to use

- A company wants a grade of its own LinkedIn ad performance over the last 30 days, with a ranked fix list.
- Spend needs reallocating between formats, or ads need checking for decay.

Route elsewhere when:
- The question is the last full month's recap. Use `linkedin-ads-monthly-report`.
- The question is the whole paid account across platforms. Use `paid-account-audit`.

## Inputs

- **Ad performance export or live connector** covering the last 30 days, and the previous 30 days for trend comparison. Needed fields: spend, impressions, clicks, landing-page clicks, ad format, ad name, campaign name, date.
- **CRM export (optional).** Needed for deal influence by format. Without it, skip that section and say what is missing.
- **Account engagement data (optional).** Needed for the accounts section.

If no data is available, stop and say so. Do not estimate or invent figures.

## Procedure

1. **Confirm the window.** Last 30 days against the 30 days before. State the dates used.
2. **Check the ad count.** Compare ads running against the number the budget supports. Classify as too few, about right, or too many, using per-ad daily spend. Flag any ad below the delivery floor.
3. **Format mix.** Spend, share of spend, and ad count per format.
4. **Grade each format.** Compare CTR, CPC, and CPM with the benchmark for that format. For link-driving formats, grade effective cost per landing-page click, not raw CPC, because raw CPC includes costs that never reach the site. Formats with no link show "n/a (no link)". Do not score them as failures. Lead generation forms are judged on cost per lead.
5. **Deal influence (if CRM).** Attribute influenced pipeline to formats. Remove test or sandbox deals before counting. Report formats whose pipeline share exceeds their spend share.
6. **Reallocation.** Recommend moves in dollars from weak formats to strong ones, citing the metric behind each move.
7. **Trends.** Period-over-period change in spend, impressions, clicks, CPC, CPM, and CTR. Label the efficiency verdict: improving (more output for flat or less spend) or declining.
8. **Decay.** Flag ads whose CTR fell for three consecutive weeks, or that fell below their format's pause threshold after 1,000 or more impressions. Requires weekly data.
9. **Red and green flags.** Each item names the campaign, ad set, or ad, the metric, and the fix.
10. **Accounts.** Top engaged accounts, accounts surging, accounts reached for the first time, and any account taking a disproportionate share of impressions. Suggest a cap only when one account's share is clearly out of line with the rest.

## Enterprise and ABM checks (when a named account list exists)

Run these in addition to the steps above. All thresholds are author defaults to calibrate against the account's own history.

- **Account linkage comes first.** If ad engagement cannot be linked to CRM opportunities at account level, do not issue reallocation, bid, or creative-pause recommendations. Say that the linkage is missing, and recommend it.
- **Reach by target account.** Share of the target account list with at least one impression in the window. Healthy at about 60% or more. Critical when under about 30% are reached while frequency rises.
- **Frequency per persona.** Sum frequency across all active campaigns for each buyer persona. Campaign averages hide decision-makers exposed across several ad sets. A persona above about 10 impressions in 30 days, with engagement down more than about 25%, is fatigued. The fix is persona-level caps, not a lower total budget.
- **Spend outside the list.** If more than about 20% of spend reaches accounts outside the ICP or target list, label it audience dilution, and recommend switching off broad delivery expansion options.
- **Form quality.** If more than about 25% of form submissions come from non-buyer job titles or non-business email domains, the creative attracts curiosity, not purchase intent.
- **Form against site request.** Lead-to-opportunity conversion on in-platform forms against website demo requests, on matching segments. Healthy at about 40% of the site rate or more. Critical below about 20%.
- **Unit economics.** Media cost per acquired customer against gross-margin-adjusted contract value. Under about 20% with payback inside 12 months is healthy. Over about 35%, or payback beyond 18 months, fails.
- **High cost per opportunity alone is not failure.** Compare exposed and unexposed accounts within the same deal stage and firmographic tier. If intent bias cannot be ruled out, mark the finding as an unproven hypothesis and escalate it for human review.

## Output

A self-contained HTML audit, titled "[Company] LinkedIn Ads Audit", with a PDF export. Sections in order:

1. Scorecard: spend, ads live, CPC, CPM, CTR, cost per landing-page click, each with benchmark and pass or fail.
2. Ad count verdict.
3. Budget by format.
4. Deal influence, or the note on what a CRM connection would add.
5. Benchmark grades by format.
6. Reallocation with dollar moves.
7. Trends and efficiency verdict.
8. Ad insights, including decaying ads.
9. Red and green flags.
10. Accounts to act on.
11. Top three to five fixes, ranked.
12. Footer: figures are directional, not guarantees.

Chat summary: two or three plain-English takeaways. The detail lives in the report.

## Quality bar

- Ads are classified by their real format field, not by campaign name.
- Test or sandbox deals are removed before influence is counted.
- Decay checks use weekly series, not one window.
- Missing data is reported as missing, not as zero.
- Small accounts get a proportionate audit. Do not run an impression-hog analysis on two ads.
- Pass and fail marks are plain text, not emoji.

## Rules

- Diagnostic only. For a monthly recap, use `linkedin-ads-monthly-report`. For a new plan, use `abm-strategy-planner`.
- Benchmarks are reference points that vary by source. Show their source and date on the report.
- Do not change ads or spend from this skill. Recommendations only.
