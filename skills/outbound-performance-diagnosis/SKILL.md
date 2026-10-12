---
name: outbound-performance-diagnosis
version: 1.0.0
status: draft-for-review
description: "Use when an outbound campaign is underperforming and the cause is not obvious: replies have dropped, meetings have dried up, a sequence that worked has stopped, or the numbers look fine but nothing closes. Works through the funnel layers in a fixed order (delivery, engagement, replies, quality), stops at the first broken layer, and produces one diagnosis with its evidence and one next change. Not for writing the copy itself (see outbound-cold-email)."
sources:
  - "Outbound performance diagnosis (MIT, Tanyo Gochev): layered funnel review in fixed order, stop at the first broken layer, opens treated as diagnostic rather than as result, reply rate read against opens, positive versus total replies, one change at a time, sample-size discipline"
  - "Adapted for GTM-360: layer thresholds (for example, a drop of more than about a fifth per step as sequence fatigue) are author defaults to calibrate per sending domain and list. Open-tracking caveats are kept as a rule of thumb, not a benchmark"
---

# Outbound performance diagnosis

## Purpose

Campaign reports tend to show the most visible number and the most visible fix. Copy gets rewritten because it is the easiest lever to see, and the leak is usually one layer up, in delivery, targeting, or the offer. This skill checks the layers in a fixed order and stops at the first one that is broken, because nothing below a broken layer can be read reliably.

## When to use

- Reply rate has dropped, or a sequence that worked has stopped working.
- Opens look fine, but nothing replies.
- Replies arrive, but meetings do not follow.
- Someone proposes changing the copy, and the cause has not been checked.

Route elsewhere when:

- The question is the offer's design. Use `cold-offer-architect`.
- The question is the list's quality. Use `prospect-list-building`.

## Inputs

- Campaign data by step: sends, bounces, complaints, opens, replies, positive replies, negative replies, and meetings.
- Sample size for each variant tested.
- Sending domain and list source, so deliverability can be judged.

## Procedure

1. **Layer 1, delivery.** Check bounce rate, spam complaints, and inbox placement. If delivery is out of range, stop. Change nothing else, because tests run on undelivered messages teach the wrong lesson.
2. **Layer 2, engagement.** Read opens and how they decay across steps. Treat opens as diagnostic only, since tracking pixels and privacy settings make them unreliable. A steep decline across steps points to sequence fatigue or deliverability, not the subject line.
3. **Layer 3, replies.** Read total reply rate and reply rate by step against opens:
   - Opens healthy, replies near zero: the copy or the offer is not moving readers.
   - Opens weak, replies weak: fix delivery and subject lines first. Reply data is not yet readable.
   - Replies healthy, mostly negative: segment. The message may suit a different group.
4. **Layer 4, quality.** Separate positive replies, referrals, "not now", and negative replies. A high reply rate that is mostly negative is worse than a lower rate that is mostly positive, because it damages the domain and the list.
5. **Check meetings after replies.** If replies are positive but meetings are missing, check response time first. Interest decays within hours. Then check whether the ask was too soft or came before any value.
6. **Prescribe one change.** Hold all other variables constant. Name the result that would confirm the diagnosis. Below a few hundred sends per variant, the difference is usually noise, so do not call it.

## Output

- The layer where the campaign breaks, with the numbers and sample sizes that locate it.
- The evidence for ruling out the layers above it.
- One change, the reason for it, and the result that would prove the diagnosis right or wrong.

## Quality bar

Delivery is verified before any downstream finding. Every rate has its sample size. Positive and negative replies are never combined into one count. Only one change is recommended. Watch for copy rewrites while a delivery metric is out of range, and diagnoses that list five improvements.
