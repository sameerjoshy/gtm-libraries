---
name: brand-mention-monitor
version: 1.0.0
status: draft-for-review
description: Use when a team needs to know what people are saying about its brand across social, news, forums, and review sites, for a routine weekly sweep, a launch watch, or a "something feels off" check. Resolves brand variants, picks a source profile for the audience, scores each mention on reach, velocity, sentiment, and risk-topic match, dedupes against earlier runs, and buckets each mention into Crisis, Watch, Engage, or Log with an owner and a response window. Not for a discourse read on a topic (see recent-discourse-sweep) or for one company's profile (see account-research-brief).
sources:
  - "Brand mention monitor (MIT, Uri Knorovich): the four-part scoring (reach, velocity, sentiment, risk-topic match) with weights, the velocity honesty gate that labels first-pass velocity as estimated, the source profile chosen before any query, the three query families (broad, risk, opportunity), the dedup split against stored fingerprints, the four-tier triage with owners and windows, and the rules to link exact URLs and never fabricate counts"
  - "Removed: the named platforms, the market profiles, the reference files on the scoring rubric, rerun memory, and output format, and the named wire and review services. Source groups are restated as categories"
  - "Adapted for GTM-360: the weights, the Crisis threshold of 65, the Watch threshold of 45, and the response windows are author defaults. Calibrate them against the brand's own incident history"
---

# Brand mention monitor

## Purpose

Brand problems usually show up in public before they reach the team. This skill sweeps the places the brand's audience talks, scores each mention on how far and how fast it is spreading and how much risk it carries, and turns the result into a short triage list with an owner for each item. The team responds to the tier, not to a raw feed.

## When to use

- A weekly routine sweep.
- A launch week, when the team wants eyes on the conversation.
- A "something feels off" check after a complaint or a press item.
- A comparison of how the brand is discussed against a named competitor.

Route elsewhere when:

- The question is what the market says about a topic over a window. Use `recent-discourse-sweep`.
- The question is one company's profile. Use `account-research-brief`.

## Inputs

- The brand, as the team understands it, plus any competitors to track alongside it.
- The date window (default: the last seven days).
- Depth: a quick scan or a deep sweep (default: deep).
- The crisis owner: the person or role who receives Crisis-tier items.
- The team channel for Crisis and Watch alerts, if one is used.

## Procedure

1. **Resolve brand variants before sweeping.** Find alternate spellings, hashtags, handles, product names, and sub-brands that are mentioned on their own. For a brand name that is also a common word, add disambiguating terms such as the industry or domain, so the sweep does not pull unrelated noise. Confirm the entity if the name is still ambiguous.
2. **Profile the brand.** Establish whether the audience is business or consumer, the industry, the main geography and language, and a rough audience size. This sets the source profile and calibrates the scoring: a high reach for a niche business tool is not the same as high reach for a consumer app.
3. **Pick the source profile before writing queries.** Weight the venues where this brand's audience actually talks. Business audiences tend to be on professional networks, review platforms, technical forums, and trade press. Consumer audiences tend to be on short-form video, photo and social platforms, and consumer review sites. Regulated sectors add regulators and wire services. Do not scan every venue equally.
4. **Sweep in parallel streams**, one per source group: social, news and press, review platforms, and community forums. Bound every query to the confirmed window. Run a shallow discovery pass first, then pull full content only for mentions that look high-impact. Scoring evidence (engagement, reply tone, author profile) comes from that second pass.
5. **Run three query families in every pass:**
   - broad brand queries,
   - risk queries, tuned to the industry (for example legal action, outage, scam, recall),
   - opportunity queries (praise, purchase intent, comparisons won).
   If a stream fails, continue with the rest and name the gap in the report. Never present a partial sweep as complete.
6. **Score every mention** on four dimensions, each from 0 to 100:
   - reach: how many people can see it,
   - velocity: how fast it is gaining ground, which separates a forming story from a stale one,
   - sentiment: scored separately for risk and for opportunity,
   - risk-topic match: legal, safety, outage, executive conduct, or misinformation.
   Composite (default weights): reach × 0.30 + velocity × 0.30 + the higher of risk sentiment and risk-topic match × 0.25 + opportunity × 0.15.
7. **Apply the velocity gate.** Hourly growth needs two measurements. On a first pass with no baseline, score only observable proxies (pickup across platforms, press pickup of a social post, absolute engagement at crisis scale) and label velocity "estimated". Upgrade it on a second pass.
8. **Dedupe against the previous run.** Keep a running record per brand. Fingerprint each mention by its normalised URL, platform, and published date. Split the feed into net-new, returning with a changed score, and already known and unchanged. Lead the report with that split. Persist the new fingerprints after the run, and carry Crisis and Watch items forward until someone marks them handled.
9. **Assign one tier per mention:**

| Tier | Composite score | Action | Suggested owner | Response window |
|---|---|---|---|---|
| Crisis | 65 and above | Route immediately | Crisis owner, legal, and leadership | Within 2 hours |
| Watch | 45 up to 65 | Assign an owner and monitor velocity | Marketing or communications | Within 24 hours |
| Engage | Any score, positive, high reach | Amplify, thank, share | Marketing or social team | Within 48 hours |
| Log | Below 45, no risk signals | None; searchable record only | None | None |

10. **Write the report.** Open with a summary and the dedup split. List Crisis items first, each as a decision card: the excerpt, the four scores, why it was flagged, who responds, by when, and a suggested action. Close with one to three recommended actions, each tied to a tier and an owner. On a first run, note that a second pass in a few days establishes the velocity baseline.
11. **Push only Crisis and Watch items** to the team channel, if one is set. Never post the full feed.

## Output

- A summary with the time window, the sources covered, the gaps, and the dedup split.
- Crisis decision cards, then Watch, Engage, and a count of Log items.
- Recommended actions, each with a tier and an owner.

## Quality bar

Every mention links to its exact URL, never a platform home page. First-pass velocity is labelled estimated. Every query is bounded to the stated window. Each Crisis card can be acted on from its own content. Watch for a flat list sorted by follower count, velocity claimed from a single snapshot, and a re-run that reports last week's items again. Never invent engagement counts or follower numbers.
