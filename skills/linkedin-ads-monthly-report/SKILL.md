---
name: linkedin-ads-monthly-report
version: 1.0.0
description: "Use when someone wants a monthly LinkedIn ads and ABM report for the last full calendar month, with a comparison to the month before. For stakeholder or executive audiences. Not a fix list (use linkedin-ads-audit) and not a new plan."
---

# LinkedIn ads monthly report

Produces a stakeholder-ready recap of last month, with the month-over-month comparison and next steps.

## Purpose

Summarise what happened last month, compare it with the month before, say whether the budget was well spent, and list the actions for next month.

## When to use

- A stakeholder needs a recap of last full calendar month, with the month-over-month comparison and next steps.

Route elsewhere when:
- The question is a 30-day grade with a fix list. Use `linkedin-ads-audit`.
- The question is the account-based programme's measurement. Use `abm-measurement-framework`.

## Inputs

- Ad performance for the last full calendar month and the month before. Use explicit start and end dates for both.
- CRM deals for the same months, if available.
- Account engagement data, if available.

The window is the last full calendar month, not the trailing 30 days. Confirm the reporting month with the user, since they may want a past month.

## Procedure

1. **Set dates.** Compute both months from today's date. State them on the report.
2. **Pull totals** for both months: spend, impressions, clicks, CPC, CPM, CTR, pipeline, deals.
3. **Format performance.** Spend and share by format. Grade each format on effective cost per landing-page click.
4. **Campaigns.** Best and worst campaigns by pipeline, then by efficiency. Best campaign type.
5. **Top ads** by clicks and landing-page clicks.
6. **Engaged companies.** Top companies by engagement. Companies with three or more clicks in the month are likely in an interested stage. Route them to sales.
7. **Comparison.** Month-over-month change in each measure, with a verdict: improving, steady, or declining.
8. **Budget verdict.** Was the allocation right? Name the over- and under-funded formats and the recommended split.
9. **Revenue section.** Only if CRM data exists. Remove test deals. If there is no CRM, skip the section and say a CRM connection would add it. Do not estimate pipeline.
10. **Next steps.** Three to five concrete actions for the coming month.

## Output

A self-contained HTML report, titled "[Company] LinkedIn Ads Report, [Month Year]", with a PDF export. Sections in order:

1. Table of contents.
2. Executive summary: headline cards with month-over-month change, top campaigns, top formats, top ads, top engaged companies as bullets, a short narrative with two to four recommendations.
3. Revenue, pipeline and deals (or the note that it needs a CRM).
4. Ad spend by format, with a donut chart drawn as inline SVG so it prints to PDF.
5. Campaign performance.
6. Performance by format against benchmark, including the full benchmark table for every format.
7. Top engaged companies in full, with the likely-interested list.
8. Next steps for next month.
9. Footer: figures are directional.

Chat summary: two or three sentences on the month.

## Quality bar

- The window is the full calendar month. Both months' boundaries are correct.
- Charts render in the PDF. Use inline SVG, not a live charting library.
- No pipeline figure appears without CRM data.
- Every grade has its benchmark next to it.

## Rules

- Reporting only. Use `linkedin-ads-audit` for a fix list of the last 30 days.
- Schedule this on the first of each month only if the user asks.
