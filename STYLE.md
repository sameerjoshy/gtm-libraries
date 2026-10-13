# STYLE

The house standard for every skill in this library. Every skill is written to
this file. When a skill and this file disagree, this file wins.

## What a skill is

A skill is an executable procedure an operator can run cold and get a defined
outcome. It is not an essay, a deck, or a sales pitch. If it cannot be run, it
is not a skill.

Three things every skill must do:

1. **Be simple.** One idea per section. Short sentences. No jargon without a
   definition. A new operator should be able to read it once and run it.
2. **Be easy to use.** Inputs are named and obtainable. The procedure is
   ordered. The output is a named artifact. Nothing is left implied.
3. **Produce the best outcome.** Every step exists to move a real number or a
   real decision. No step is there to look thorough.

## Language

- **American English** everywhere: *optimize, prioritize, personalize,
  organize, monetize, behavior, center, analyze, program, favor, color*. This
  includes folder names and slugs.
- **Second person, active voice.** "Measure the fill rate," not "the fill rate
  should be measured."
- **Imperative procedure.** Steps start with a verb.
- **Plain words.** Prefer the short word. Define a term the first time it is
  used if it is not in `definitions/glossary.md`.
- **No emoji. No decorative banners. No ALL-CAPS for emphasis.**
- **No hype.** No "revolutionary", "game-changing", "seamless", "world-class".
  A claim is a fact with a source or it is not written.
- **No mixed spelling, no mixed pronouns.** Say "you" or "the operator", never
  flip between "one", "we", and "you" in the same skill.

## Evidence and honesty

- Every fact about a prospect, market, or number carries a **source** and a
  **confidence** (high / medium / low). An inference is labelled as an
  inference.
- **No invented specifics.** Statistics, customer names, quotes, prices, and
  case studies come only from approved material or a cited source. Where a
  figure is missing, use a placeholder in brackets and say what fills it.
- Defaults, benchmarks, and thresholds are **labelled as defaults** and are
  replaceable by the client's own numbers.

## Approval and safety

- **Nothing leaves the building without human approval.** No send, no CRM
  write, no price, no contract, no payment happens without a named approver.
  Skills stage work; a human releases it.
- **Business contact data only.** No personal emails, phone numbers, or private
  account details.
- State the approval gate explicitly in the skill, and end with the approval
  question where an external action is proposed.

## Structure

Every skill has these sections, in this order:

| Section | Required | What it holds |
|---|---|---|
| `Purpose` | yes | One short paragraph: the outcome the skill produces. |
| `When to use` | yes | The triggers. Then a `Route elsewhere when:` list that sends adjacent cases to the right skill. |
| `Inputs` | yes | What is needed, each with where it comes from. |
| `Procedure` | yes | Numbered, executable steps. Ordered cheapest-first where gates apply. |
| `Output` | yes | The named artifact(s) the skill produces. |
| `Quality bar` | yes | Checkable statements. If it cannot be checked, it is not a quality bar. |
| `Rules` | optional | Only hard MUST / NEVER rules the Quality bar does not already state. One `Rules` section, never two. |

Optional supplementary sections, allowed only from this closed list, placed
after `Procedure` and before `Output`, or at the end after `Rules`:

- `Principles` — the reasoning that anchors judgment calls.
- `Diagnostic questions` — questions used to reach a decision.
- `Anti-patterns` — what failure looks like.

Anything else (benchmarks, frameworks, deliverability limits, cadence tables,
messaging frameworks) is a **subsection** (`###`) inside the relevant section,
not a new top-level `##` heading.

- **One `##` per canonical section.** Steps and sub-parts are `###` or
  numbered lists, never new `##` headings.
- **Frontmatter:** `name` equals the folder slug; `version` is semver;
  `description` opens with "Use when", "Use to", or "Use for" and lists routing
  in the form "Not for X (see `skill-name`)."

## Length

- Aim for **600 to 1,600 words**. A skill over about 2,000 words is flagged and
  must justify the length or be tightened.
- Cut anything a competent operator would infer. Keep the parts that change
  behavior.

## Voice at a glance

- Bad: "It is important to note that organizations should consider optimizing
  their outreach in order to maximize efficiency."
- Good: "Optimize the first line. It drives the reply."
