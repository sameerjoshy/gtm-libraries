# QA Report — Skills Library

Date: 2026-10-12 · Branch: `skills-library-qa` · Baseline: `eb30ddc`

## Scope
All **192 skills** in `skills/` were reviewed and brought to one house standard
(`STYLE.md`): canonical structure, American English, consistent house voice
(simple, easy to use, best outcome), unambiguous routing.

## Method
1. **Mechanical pass (deterministic).** Applied by script across all 192 files.
2. **Uniform rewrite.** Every skill rewritten to the `STYLE.md` template and
   voice, preserving substance and inventing nothing.
3. **Deterministic validation.** Every file re-checked for structure, headings,
   frontmatter, routing, spelling, and line endings.

## What changed

### Structure
- Canonical sections enforced on every skill, exact order and names:
  `Purpose`, `When to use`, `Inputs`, `Procedure`, `Output`, `Quality bar`,
  optional `Rules`.
- **1,489** non-canonical top-level headings demoted to `###` subsections
  (steps, tables, frameworks, benchmarks, anti-patterns) so every skill reads
  the same way.
- **8** skills had a duplicate `## Rules` heading (a merge artifact from
  "Rename Boundaries to Rules"). All collapsed to a single `Rules`.
- `## Inputs (…)` variants normalized to `## Inputs`.
- Every skill ends `When to use` with a `Route elsewhere when:` list. **3**
  skills that were missing it (`multi-threading-coach`,
  `mutual-action-plan-builder`, `reply-handling`) now route explicitly.

### Language
- **564** British spellings converted to American English
  (e.g. `optimisation→optimization`, `prioritisation→prioritization`,
  `programme→program`, `centre→center`, `labelled→labeled`,
  `behaviour→behavior`, `judgement→judgment`).
- `version` bumped on every skill; frontmatter `name` still equals the folder.

### Slugs (URLs) renamed to American English
| Old | New |
|---|---|
| affiliate-programme-playbook | affiliate-program-playbook |
| creator-programme-measurement | creator-program-measurement |
| creator-programme-strategy | creator-program-strategy |
| paid-optimisation-signals | paid-optimization-signals |
| paid-social-optimisation-playbook | paid-social-optimization-playbook |
| pricing-monetisation-ops | pricing-monetization-ops |
| seo-topic-prioritisation | seo-topic-prioritization |
| personalised-first-touch | personalized-first-touch |

All cross-references (in-file backticks and `README.md` links) were updated.

## Validation result
- Canonical sections present and ordered: **192/192**
- Single `Rules` where present: **192/192**
- `Route elsewhere when:` present: **192/192**
- British spellings remaining: **0**
- `name` = slug, `version` set: **192/192**
- LF line endings: **192/192**

## Known, accepted soft flags
- **30 skills exceed 2,200 words** (largest: `crm-migration-consolidation`
  3,940; `deal-blocker-maneuvers` 3,752; `pricing-monetization-ops` 3,502).
  Each carries reference tables or a multi-mode procedure; length is justified
  and substance was preserved over trimming.

## Files added
- `STYLE.md` — the house standard (format, voice, evidence, approval, length).
- `DECISIONS.md` — "Skill format" section now points to `STYLE.md`.

## How to verify
```
# structural + spelling scan (no output = clean)
node <validator> .
```
Regenerate from the repo and diff against this branch. Every skill is
self-consistent and renderable as a flat set of sections.
