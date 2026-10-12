---
name: earned-autonomy
version: 1.0.0
description: "Use to decide how much a GTM automation or AI agent may do without a person reviewing each output. Assigns a level per task (draft, spot-check, exception-only, or automatic), states the evidence required to move up and the triggers that move it back down, and treats wordless low-risk actions differently from anything that carries words. Use when a workflow is ready to run on a schedule, when per-item approval should stop, or when an agent has made a mistake. Not for the security or legal review of the agent itself."
---

# Earned autonomy

## Purpose

Automation can save hours or cause damage, and the difference is usually how much it is trusted, not how well it is built. This skill sets the level of trust for each task separately, requires evidence before raising it, and lowers it automatically when something goes wrong. An agent trusted with an easy task does not earn trust for a risky one.

## When to use

- A workflow is ready to run on a schedule without review.
- Per-item approval has become a bottleneck.
- Someone asks how much of the GTM process to automate.
- An agent has made a mistake, and the response needs deciding.

Route elsewhere when:

- The question is whether the agent is secure or compliant. That needs a security or legal review.
- The question is a single draft's quality. Use `reply-pull-gate` or `sdr-outbound-rules`.

## Inputs

- The task, its inputs, and its outputs.
- The outcome measure for the task and its target.
- The guardrails: what counts as a breach, such as a complaint, a bounce spike, or a wrong account.
- The log of past outputs, with the human edits and rejections recorded.

## Levels

| Level | What ships | What reaches a person |
|---|---|---|
| L0 Draft | Nothing containing words | Every item containing words, before it goes |
| L1 Spot-check | Items that pass the quality gate | A random sample, and every low-confidence item |
| L2 Exception-only | Items that pass the gate | Flagged, edge, and high-risk items only |
| L3 Automatic | Runs on schedule and ships when the gate passes | A periodic digest, and any guardrail breach |

**Copy risk versus click risk.** An action that carries no words, such as a profile visit or a connection request without a note, cannot misstate or embarrass, so it can run at L0 inside its rate limits. Anything carrying words starts at L0 and must earn its way up.

## Procedure

1. **Assign a starting level** to each task. New tasks start at L0 or L1, never higher.
2. **Set the promotion criteria** before the task runs:
   - L0 to L1: at least 30 items reviewed, with human edits or rejections under about 10 percent (default).
   - L1 to L2: at least 50 items at L1, with at least 95 percent passing the gate on sampling, and no guardrail breach in the window (default).
   - L2 to L3: the outcome measure at or above target for four consecutive weeks, with no breach (default).
3. **Trust judgement steps separately.** A task with several steps, such as choosing an angle and choosing the person, has a count for each. Clearing one does not clear the other.
4. **Reset on credibility-costing misses.** A miss that would show the sender did no homework resets the count for that step to zero. A harmless stylistic miss does not.
5. **Hold, do not promote, when no refusals occur.** A window with no human reviews is not evidence of quality, because nobody looked.
6. **Set the automatic drops.** Any guardrail breach moves the task back one level without waiting for review. Name the person alerted.
7. **Review the level** each month, and record every change with its evidence.

## Output

- The level for each task, with the evidence behind it.
- The criteria for the next level, with the current count against each.
- The automatic triggers that lower the level, and who is alerted.
- A log of level changes.

## Quality bar

Every level has recorded evidence. Judgement steps are counted separately. Credibility-costing misses reset the count. Automatic drops are set before autonomy is granted. Watch for autonomy granted per agent, promotion on an empty review window, and thresholds changed after the fact.
