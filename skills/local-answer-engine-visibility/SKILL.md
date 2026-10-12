---
name: local-answer-engine-visibility
version: 1.0.0
status: draft-for-review
description: "Use when a business serves specific towns, suburbs or service areas and needs to know where AI answer engines recommend it. Tests each served area separately in buyer phrasing, records map-pack presence and written-answer presence as separate signals, and produces a ranked gap map of the areas where rivals are named instead. Not for overall brand visibility (see answer-engine-visibility-tracking) or for the citation sources behind answers (see citation-source-outreach)."
sources:
  - "Local AI visibility (MIT, Huxley Peckham): the town-by-town matrix in buyer phrasing, the warning that head-city results predict nothing about nearby areas, recording map-pack and written-answer presence separately because they move for different reasons, the gap map ranked by demand with rivals named, and the visibility cliff where one competitor dominates a few areas"
  - "Removed: the named engines and the named local listing platform. Demand is ranked by any measure the team has, with population as a proxy, and the source's named data tools are not restated"
  - "Adapted for GTM-360: the rule that area results are never averaged into one score is kept as a hard rule. The ranking by demand is the source's method, applied with the team's own data"
---

# Local answer engine visibility

## Purpose

A business that serves several towns can be recommended in one and invisible in the next. A single head-city check hides exactly the gaps that cost work. This skill tests each served area on its own, separates the two ways a local brand can appear, and ranks the gaps so the first fix is the most valuable one.

## When to use

- A business serves specific towns, suburbs or areas, and wants to know where AI recommends it.
- A local competitor appears to win areas the business also serves.

Route elsewhere when:

- The question is overall brand visibility. Use `answer-engine-visibility-tracking`.
- The question is the sources behind the answers. Use `citation-source-outreach`.

## Inputs

- Every area the business genuinely serves, not only the head city.
- The services offered, so each test question names a service and a place.
- The engines to test, and which of them draw on map results.
- Any demand data the team has for each area, such as search volume or customer counts. Population is the fallback.

## Procedure

1. **Build the area matrix.** List every served area. Phrase each test question the way a local buyer would type it: the service and the place, in plain words. Ask each question per area and per engine.
2. **Do not generalise from one area.** Results in the head city say little about the suburb next door. Answer engines build local answers from thin, local evidence, so presence can change from one postcode to the next.
3. **Record map-pack presence and written-answer presence separately.** The map pack follows profile completeness, reviews and proximity. The written answer follows mentions, citations and content. A business can hold one and not the other, and each needs different work.
4. **Build the gap map.** For each area and engine where the business is absent, record which rivals are named, in the engine's own words, with the answer quoted.
5. **Rank the gaps by demand.** Use the team's demand data where it exists, and population where it does not. Say which measure was used.
6. **Read the pattern.** A visibility cliff is one competitor dominating a few areas on every engine. Those areas are usually the priority, and the quoted answers show why.

## Output

- The area-by-engine grid, with map-pack and written-answer presence in separate columns.
- The ranked gap list: area, question, rivals named, and the quoted answer.
- The demand measure used for ranking.

## Quality bar

Each served area is tested on its own. Map-pack and written-answer presence are never merged. Areas are never averaged into a single score. Watch for one head-city check standing in for the whole service area, traditional local rankings read as proof of AI presence, and a gap list that cannot be traced to quoted answers.

## Rules

- Test each served area separately, in buyer phrasing.
- Record map-pack presence and written-answer presence as separate signals.
- Never average areas into one score.
- Never assume traditional local rankings mean the business appears in AI answers.
