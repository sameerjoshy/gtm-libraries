---
name: linkedin-ads-audit
version: 1.0.0
status: draft-for-review
description: Use when someone wants to review, grade, or improve their own LinkedIn ad results, ABM programme, or spend over the last 30 days, for example "audit my LinkedIn ads", "why is my CPC high", "which format is working", "are my ads decaying". Produces a graded report with a prioritised fix list. Not for planning a new campaign.
sources:
  - "LinkedIn ads and ABM audit (MIT, Emilia Korczynska, ZenABM), audit structure and benchmark grading"
  - "LinkedIn ads 35-point audit (MIT, Justin Rowe), checklist coverage"
  - "LinkedIn ads CTR signal (MIT, Brianne Thomas), CTR decay signal"
  - "Google and Meta ads audits (MIT, Aditya Sriram), write-safety and read-only rule"
---

# LinkedIn ads audit

Grades a company's own LinkedIn ad performance over the last 30 days against benchmarks, and returns a short, ranked fix list.

## Purpose

Find where money is wasted, which formats and accounts deserve more spend, and which ads are decaying. Report what the data shows, and say when it cannot show something.

## Inputs

- **Ad performance export or live connector** covering the last 30 days, and the previous 30 days for trend comparison. Needed fields: spend, impressions, clicks, landing-page clicks, ad format, ad name, campaign name, date.
- **CRM export (optional).** Needed for deal influence by format. Without it, skip that section and say what is missing.
- **Account engagement data (optional).** Needed for the accounts section.

If no data is available, stop and say so. Do not estimate or invent figures.

## Steps

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

## Quality checks

- Ads are classified by their real format field, not by campaign name.
- Test or sandbox deals are removed before influence is counted.
- Decay checks use weekly series, not one window.
- Missing data is reported as missing, not as zero.
- Small accounts get a proportionate audit. Do not run an impression-hog analysis on two ads.
- Pass and fail marks are plain text, not emoji.

## Boundaries

- Diagnostic only. For a monthly recap, use `linkedin-ads-monthly-report`. For a new plan, use `abm-strategy-planner`.
- Benchmarks are reference points that vary by source. Show their source and date on the report.
- Do not change ads or spend from this skill. Recommendations only.
