# Library decisions

Team-wide defaults for this library. Each one is a default. A client's copy of the library may override it, and the override must be recorded in that copy of this file, with a date and the reason.

| Decision | Default | Decided | Where it applies |
|---|---|---|---|
| Deal health score | Weighted 0 to 100 across six dimensions (engagement recency, multi-threading, stage velocity, methodology adherence, next-step quality, economic buyer access). Bands: 80 to 100 healthy, 60 to 79 watch, 40 to 59 at risk, below 40 critical. | 2026-10-12 | `deal-velocity` |
| Evidence gates | 1 to 5 per dimension, with stage minimum totals. Used for stage entry and forecast truth. A separate job from the health score. | Unchanged | `deal-qualification-gates` |
| Blocker scoring | -1 to +1 per dimension, with stage bands. Used for blocker maneuvers. A separate job from the health score. | Unchanged | `deal-blocker-maneuvers` |
| Account scoring | Signal weights for accounts, not deals. | Unchanged | `account-tier-scoring` |
| Discovery score | SPICED total, 0 to 15 (five elements at 0 to 3). One discovery framework per team. Recorded in its own field and never added to the health score or the evidence gates. | 2026-10-12 | `sales-methodology` |
| Superseded | The 0 to 3 six-dimension score (0 to 18 total) in `revenue-metrics` is no longer the health score. Do not report it alongside the 0 to 100 score. | 2026-10-12 | `revenue-metrics` |
| ICP list tiering | 100-point ICP score: A 90 to 100, B 70 to 89, C 50 to 69, D under 50. | 2026-10-12 | `prospect-list-building` |
| Alternative list tiering | Pass-and-signal (A, B, C, D). Use only if a client chooses it, and never in the same list as the point score. | 2026-10-12 | `prospect-list-building` |
| CRM platform | Salesforce. The HubSpot platform skill is not written, since no client uses HubSpot. | 2026-10-12 | `revops-salesforce` |

## Rules that apply to every decision

- Thresholds, weights, and bands are defaults. Calibrate them against the client's won and lost deals before relying on them.
- Do not average scores from different scales. Keep each in its own labelled field.
- A change to a default is made here first, then applied to the skills that cite it.

## Skill format

The canonical format and house voice live in `STYLE.md`. In short: every skill has Purpose, When to use (with a "Route elsewhere when:" list), Inputs, Procedure, Output, Quality bar, and an optional Rules section, in that order. Only `Principles`, `Diagnostic questions`, and `Anti-patterns` are allowed as extra top-level sections; everything else is a subsection. A skill has exactly one `Rules` section. Skills are written in American English.
