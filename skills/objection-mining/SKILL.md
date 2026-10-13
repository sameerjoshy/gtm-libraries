---
name: objection-mining
version: 1.2.0
description: "Use when the same pushback keeps arriving and nobody has recorded it. Mines call recordings, reply threads, and lost-deal notes for recurring objections, classifies each one (timing, budget, authority, trust, fit, competition), ranks them by observed frequency with real quotes, and names the upstream place each should be answered so it stops arriving. Not for handling one live objection on a call (see `call-scoring`) or a written reply (see `reply-handling`)."
---

# Objection mining

## Purpose

People who are not interested rarely object. They ignore you. An objection means a buyer engaged enough to state their criteria. Every objection that arrives repeatedly is a gap in the outreach, paid for again on every call. This skill finds the recurring objections, classifies them, and moves each answer to the place it should have been given: the offer, the first touch, the site, or qualification.

## When to use

- The same pushback comes up across reps or campaigns.
- Reps are stuck on objections that could have been answered earlier.
- A battlecard is wanted, and the team has no evidence of which objections matter.
- A campaign's losses need an explanation.

Route elsewhere when:

- The question is one live exchange on a call. Use `call-scoring` to review it, or `reply-handling` for a written reply.
- The question is the offer itself. Use `cold-offer-architect`.

## Inputs

- Call recordings or transcripts, reply threads, and lost-deal notes for a defined period.
- Win, loss, and no-decision reasons where recorded.
- The current outreach and offer, so each objection can be matched to where it should have been handled.

## Procedure

1. **Collect the raw objections.** Pull the buyer's own words. Paraphrases are logged separately and not counted as quotes.
2. **Classify each objection** into one of six categories before any response is written:
   - Timing: "not this quarter". Real interest that is not urgent enough.
   - Budget: "too expensive". Often a priority or a comparison problem.
   - Authority: "I need to check with". The speaker is the champion, not the buyer. Equip them.
   - Trust: "how do I know this works". Needs proof of fit, not more features.
   - Fit: "we are different", "too small for this". The buyer cannot see themselves in the message.
   - Competition: "we are looking at X too". Active comparison.
3. **Read the category, not just the words.** The same phrase can belong to different categories. "Too expensive" from a buyer who has not seen value is a fit objection, and a discount answers it wrongly.
4. **Rank by observed frequency** per category and overall. Count only quoted occurrences, and state the sample size.
5. **Name the pre-handle point** for each objection: which message, which page, which qualification question should have answered it. Propose one change at that point.
6. **Record timing objections** with the stated reason and date, for return at that date. Timing is a deferral, not a rejection.
7. **Apply the opt-out rule.** A direct "stop", "unsubscribe", or "remove me" is a suppression: the contact leaves every sequence and is not contacted again. Do not slow the cadence or send a closing message. A soft "not interested" keeps the contact in follow-up at a slower pace.

## Output

- A ranked catalog: category, frequency and sample size, a verbatim quote, what the objection usually means, and the pre-handle point with its proposed change.
- Timing objections with dates, for scheduled return.
- Opt-outs recorded for suppression, listed separately.
- The one or two objections that appear most often and would move the most deals if fixed upstream.

## Quality bar

Every objection is classified before a response is proposed. Frequencies come with sample sizes. Each objection names where it should have been handled. Opt-outs are suppressed, not nurtured. Watch for battlecards of rebuttals with no frequency data, discounts offered for fit or trust objections, and "not interested" treated as a reason to stop.
