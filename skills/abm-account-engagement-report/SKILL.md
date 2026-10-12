---
name: abm-account-engagement-report
version: 1.1.0
description: "Use when the user has account-level ad data (for example a platform rate accounts CSV) plus pipeline data and wants a client-facing ABM account engagement dashboard showing funnel progression, a scored account leaderboard, segment analysis, and an action plan. Not for a single-account brief (see account-research-brief) or a monthly report (see linkedin-ads-monthly-report)."
---

# ABM account engagement report

Turns account-level ad data and pipeline data into one self-contained HTML dashboard for a client.

## Purpose

Answer three questions for a VP Marketing or CRO audience:
1. Which accounts are progressing through the funnel?
2. Where do buying signals appear in more than one channel?
3. Which segments are engaging, and which are spending without response?

## When to use

- A client needs an account-level dashboard that shows which accounts are progressing, where signals appear in more than one channel, and which segments engage.

Route elsewhere when:
- The question is planning the program. Use `abm-strategy-planner`.
- The question is the measurement method. Use `abm-measurement-framework`.

## Inputs

- **Rate accounts CSV (required, or pipeline data required).** Expected columns: Company Name, Website, Industry, Company Size, Headquarters, Clicks, Impressions, Cost, CPC, Engagement Level, Conversions, Leads, Influenced Revenue. Any signal tool export that matches these fields works.
- **Pipeline data (strongly recommended).** One row per contact: company, contact, title, source channel, funnel stage (Lead, MQL, Opportunity), search keyword, campaign.
- **Client context (ask first).** Ask: "Which client is this for? A company name or URL helps me set the ICP." If context exists in `context/client-*.md`, use it. If the user declines, run without ICP framing and say so on the dashboard.
- **Optional:** search-term reports, CRM deal exports.

## Procedure

1. **Validate.** Require a Company Name column. Blank numeric cells become 0. Strip currency symbols and whitespace. Read the file with BOM handling. Map "N/A" industry or size to "Unknown". Log every row that fails and its reason.
2. **Engagement flag.** Ignore the export's Engagement Level column when it is uniform (often every row says "Low"). Use actual behavior instead: clicks at or above 1 counts as Engaged. Note this on the dashboard.
3. **Match pipeline to accounts.** Exact case-insensitive match first, then partial match. List every unmatched pipeline company. Do not drop it silently.
4. **Multi-channel.** An account present in two or more pipeline sources is multi-channel. These are the strongest signals and lead the dashboard.
5. **Funnel.** Count unique accounts at each stage: Reached (every account in the export), Engaged (1+ clicks), Lead, MQL, Opportunity. An account at several stages counts once, at its highest stage. The stage counts must be non-increasing from top to bottom. If they are not, stop and report the error.
6. **Score.** `Score = (clicks x 10) + (impressions / 100) + stage bonus`, with bonuses Lead 25, MQL 50, Opportunity 100. These weights are the default. They are not benchmarks. Record the weights used at the top of the dashboard. Sort descending.
7. **Segments.** By industry: accounts, impressions, clicks, cost, CTR, pipeline accounts. By size band: same measures. Always show the number of accounts behind each figure. A segment with one or two accounts is not a pattern and must be labelled as such.
8. **ICP alignment (only with client context).** Classify each industry as ICP or non-ICP. Report CTR for each group, the CTR multiple, and the share of impressions going to non-ICP.
9. **Heatmap.** Clicks by industry and size, for accounts with at least one click.
10. **Revenue, if present.** Keep three measures separate and never sum them into one number:
    - *Exposure:* impressions on the account.
    - *Influence:* exposure that came before pipeline creation, within a stated window.
    - *Attribution:* a click or conversion linked to the pipeline event.
    Remove renewals before claiming influence.

## Output

One self-contained HTML file named `[Client]_ABM_Account_Engagement_Dashboard.html`, with sections in this order:

1. Header: client, channels, account count, pipeline account count, date, and the scoring weights.
2. Funnel: six stat cards (Reached, Engaged, Leads, MQLs, Opportunities, Multi-Channel) and a log-scale funnel chart.
3. Active pipeline: multi-channel callout first, then pipeline cards grouped Opportunity, MQL, Lead, each with company, contact, source, keyword, and campaign.
4. Leaderboard: tabs for All, Pipeline Only, and Ad Engaged Only.
5. Segments: clicks by industry and size, impressions against clicks, CTR by size, with a one-line insight.
6. Heatmap, with a note on where engagement is thin.
7. Action plan: one card per stage (Opportunity, MQL, Lead, Ad Engaged), targeting optimization, and signal-tool levers. Name real accounts and keywords from the data. Do not write generic advice.

Chat summary, three to four sentences: funnel progression (accounts reached, in pipeline, at opportunity), the multi-channel finding, the most useful segment finding with its sample size, and one account-level insight.

## Quality bar

- Funnel stages are non-increasing.
- Every unmatched pipeline company is listed.
- No unfilled template tokens remain.
- No em dashes or emoji in the output.
- Segment figures show account counts.
- Revenue is not summed across exposure, influence, and attribution.

## Rules

- Covers one dashboard for one client. For monthly recap reporting use `linkedin-ads-monthly-report`. For a diagnostic fix list use `linkedin-ads-audit`.
- Do not present scoring weights as industry benchmarks.
- Do not use a single client's results to set a benchmark for others.
