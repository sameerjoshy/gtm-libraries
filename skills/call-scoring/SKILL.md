---
name: call-scoring
version: 1.0.0
description: "Use to score a sales call and turn the score into coaching. Covers two complementary views: nine conversation KPIs computed from the transcript (talk ratio, question rate, longest monologue, next steps, and similar), and a behaviour scorecard per conversation type (prospecting, discovery, demo, pricing, close) scored 1 to 5 with cited evidence. Use when coaching is vague, reps and managers grade calls differently, or a transcript needs grading. Not for qualification of the deal itself (see meddpicc-gap-audit)."
---

# Call scoring

## Purpose

Coaching fails when nobody agrees what a good call looks like. This skill makes the standard visible in two layers. The first layer measures how the conversation was run, from the transcript. The second layer grades whether the behaviours that win deals happened, using a card per conversation type. Both layers point at the same practice plan.

## When to use

- Coaching feedback is vague ("felt good", "more energy").
- Reps and managers disagree on whether a call went well.
- A rep needs a specific drill, not general advice.
- A transcript needs grading against a standard.

Route elsewhere when:

- The question is whether the deal is qualified. Use `meddpicc-gap-audit`.
- The question is a demo's structure. Use `demo-builder`.

## Inputs

- A transcript with speaker labels, ideally with timestamps. Without timing, the timing-based KPIs are marked unavailable, not estimated.
- The call's conversation type: prospecting, discovery, demo, pricing, or close. Classify from content if the label is missing.
- The team's current playbook, so the scorecard matches how the company sells.

## Procedure

### Part A: Call KPIs from the transcript

1. **Attribute speakers.** Resolve who is on each side from calendar or CRM metadata. If unsure, propose the attribution and confirm before scoring.
2. **Classify the call.** Use content first, then any label as a hint. If a call spans two types, score it under its dominant type and say so.
3. **Compute nine KPIs from the raw transcript, never from a connected tool's summary numbers:**
   - Talk-to-listen ratio (seller share of talk time).
   - Question rate (questions per call, and share asked by the seller).
   - Longest monologue (one side holding the floor without interruption, pooled across that side's speakers).
   - Talking speed.
   - Engagement level (buyer turns, turn frequency, and length).
   - Sentiment, from buyer language.
   - Agenda set at the start.
   - Next steps agreed with dates.
   - Next meeting scheduled before the call ended.
4. **Score against target bands.** Bands are defaults and must be calibrated per client against their own won calls. Timing-based KPIs are marked unavailable when the transcript has no timestamps.
5. **Separate two groups.** Conversation quality (questions, talk ratio, engagement) and forward motion (agenda, next steps, next meeting). Report them separately. A call that scores well on quality and poorly on motion is a finding: the rep ran a good conversation that went nowhere.

### Part B: Behaviour scorecard

1. **List the key conversations** where deals are won and lost. Each gets a card.
2. **Build 10 to 15 items per card.** Each item is an observable behaviour, not a judgement ("got the buyer to state the problem in their own words", not "good discovery"). Group items into the call's natural chunks: opener, body, close, for example.
3. **Score each item 1 to 5** with the quoted moment that earned it, or the absence that cost it. Mark an item unobserved if the transcript does not show it. Never invent a moment.
4. **Find the lowest chunk** and write one drill for it.

### Part C: Coaching loop

- Practise the lowest-scoring chunk only, not the whole call.
- One role play per rep per week, minimum.
- Re-score a sample of calls after a month. Track the trend per chunk, so the team sees where it improves.
- Grow the card only after the scoring habit is steady. A 40-item card nobody uses grades nothing.

## Output

- Nine KPI values with their bands, each marked computed or unavailable.
- Quality and forward-motion scores, reported separately, with any mismatch named.
- Scorecard result for the call type: each item scored with evidence, the lowest chunk, and one drill.
- A cumulative trend when several calls are scored.

## Quality bar

Every score cites the transcript. Every band is marked as a default or as calibrated. Quality and motion are never averaged into one number. Watch for scores given on impression, bands treated as industry benchmarks, and drills that practise the whole call instead of the weakest section.
