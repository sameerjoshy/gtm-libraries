---
name: signal-detection-and-timing
version: 1.2.0
description: "Use to decide which buying signals to track for a business, to interpret a fired signal (relevance, meaning, strength, confidence, why-now), and to decide when and how to act on it (window, cadence, channel). Covers website-based signal plans, fixed watchlists, and website or content engagement. Hiring and champion job-change signals have their own skills. Not for choosing a ready play (see `signal-outbound-plays`)."
---

# Signal detection and timing

## Purpose

Keep effort on the few signals that change a buying decision, and act on them inside the window they stay useful. Most signals are noise. A signal that is not interpreted, dated, and checked for fit is an alert, not a lead.

## When to use

- A team needs to choose which public or first-party signals to track for outreach.
- A signal has fired and needs interpreting, dating and checking for fit before anyone acts.

Route elsewhere when:
- The question is which ready play to run for a specific event. Use `signal-outbound-plays`.
- The question is a champion who has changed employer. Use `champion-job-change-tracking`.
- The question is hiring patterns in particular. Use `hiring-signal-tracking`.
- The task is writing the outreach itself. Use the outbound skills.
- The task is scoring accounts into tiers. Use `account-tier-scoring` (targeting family).

## Inputs

- Business context: what is sold, to whom, sales motion (product-led, sales-led, hybrid), and ICP constraints.
- A signal to interpret: type, what happened, date it occurred, company, and any corroborating signals.
- For a fixed watchlist: the account list, with canonical domains.
- For engagement signals: the engagement event, the content, and time on page or repeat-visit count where available.

## Procedure

### A. Choose signals for a business

1. Extract from the company's site: what it sells, who buys, and what has to change in an account for it to be needed now.
2. Turn each why-now into a signal you can observe. Group by family: people moves, company moves, competitive engagement, social or behavioral activity, and technology changes (a tool added or dropped).
3. Rank by fit, intent strength, and volume. Keep three to five. Drop anything that is undetectable, low-volume, or really inbound.

### B. Interpret a fired signal

1. **Relevance gate.** Ask whether the event creates or reveals a problem the offer solves. If clearly not, stop and return "not relevant" with a one-line reason. Nothing downstream should see it.
2. **Classify the signal:** business event or intent data.
3. **Strength** (high, medium, low): how explicitly the event describes the relevant activity. Score the current event only. Do not add points for earlier signals.
4. **Confidence** (high, medium, low): how sure we are of the reading. Intent data alone rarely reaches high confidence, because it shows topic interest, not a purchase decision.
5. **Category:** growth, urgency, intent, risk, or noise. Pick one, the one that most directly explains why to act now versus later.
6. **Why now:** one sentence that cites something concrete from the event. If none exists, write null. Do not invent one.
7. **What not to assume:** the most important inferential risk. What the signal does not prove.
8. **Open questions:** at most five, in order of what blocks outreach first. A signal with more than five real uncertainties is too uncertain to act on.
9. Return interpretation fields only. This step never assigns a tier, chooses an action, sends an alert, or writes to memory. Those belong to other stages.

### C. Strength and confidence guide

| Signal combination | Typical strength | Typical confidence |
|---|---|---|
| Intent data plus a high-intent first-party visit (pricing, demo, integrations) | High | Medium |
| Intent data plus a relevant business event | Medium to high | Medium |
| Intent data plus a relevant hiring cluster | Medium | Medium |
| Intent data alone | Low | Low |
| Relevant funding with a stated use of funds | Medium to high | Medium |
| Funding with no use of funds stated | Low | Low |
| Generic executive hire, no link to the problem | Low | Low |

Treat these as starting points to calibrate against your own reply and conversion data, not as fixed rules.

### D. Decide the window and cadence

1. Classify the decay profile:
   - **Act-now:** short, sharp intent, such as a visit to a pricing or demo page.
   - **Ramp:** a window that opens over weeks, such as a new leader settling in.
2. Set the window from the event date:
   - High-intent behavioral signals: reach out within about 24 to 48 hours. Cold within days.
   - New leadership or role change: the useful window tends to open two to four weeks in and run into the second month.
   - Hiring, funding, or expansion: days to weeks. Anchor to a real deadline if the event names one.
3. Match cadence and channel order: tight and multi-touch for act-now; patient and value-first for ramp.
4. Frame one angle that ties the outreach to the trigger's why-now.

Output: `{ reach_out_by, cold_after, cadence, channel_order, angle }`.

### E. Watchlists over a fixed account list

1. Resolve each target to a canonical domain, operating entity, and parent. Search existing and archived CRM records before proposing a new record.
2. Route ambiguous domains, subsidiaries, and namesakes for review. Do not monitor an unresolved company name, because matching will blend unrelated entities.
3. Classify each account: **watch** (stable identity and fit), **research** (fit or identity incomplete), or **exclude** (with a recorded reason).
4. Write the signal specification before collecting events: observable event, primary evidence, freshness window, expected implication, known false positives, likely buying roles.
5. On each cadence: collect events, resolve each to one watched account, suppress duplicates and anything already acted on, re-check fit, active opportunities, recent touches, and exclusions, then rank the account, event, and contact combination together.
6. Return engage, research, nurture, or skip, with the reason and the strongest counterargument. Engage needs a verified contact. Strong event with no contact is research, not a blind send.

### F. Engagement signals (website and content)

| Engagement | Strength |
|---|---|
| Pricing page read for more than about 60 seconds, repeat visits | High |
| Demo or sales page read for more than about 60 seconds | High |
| Gated asset download with name and company | High |
| Webinar attended live | High |
| Case study or comparison page | Medium |
| Webinar registered, not attended | Medium |
| Single blog post, nothing else | Low |
| Anonymous company visit, no contact | Low (act at account level) |

Before any outreach:
- Check for an active sequence. Do not message someone a sequence is already reaching.
- Reference the specific content engaged with. A generic "thanks for visiting" does worse than no message.
- Respond within the window for the engagement type. A pricing visit answered in week two has missed.
- For an anonymous visit, create an account-level task for the owner, not an individual message.

## Principles

- **Start from the buyer's why-now, not a menu of signal types.** Ask what has to become true in an account for this offer to matter now. Then find the public, observable proxy for that change.
- **Detectability is the gate.** A signal is usable only if it can be seen in public or first-party data, at useful volume, today.
- **Freshness is load-bearing.** Date every event from the event itself, not from when an aggregator published it. A stale signal is a cold lead.
- **Strength and confidence are separate.** Strength is how big the event is. Confidence is how sure the reading is. Never let one stand in for the other.
- **Never manufacture urgency.** If the event has no real deadline, the window is soft and must be labeled so.
- **Never creepy.** Reference the public change ("saw the funding news"), never how the person was found ("saw you visited our pricing page").

## Output

Depending on the step:
- A signal plan: three to five signals, each with the observable event, why it fits this business, where to detect it, the target persona and firmographic filter, and a rank.
- An interpretation record: relevance verdict, signal type, clean summary, likely meaning, business implication, strength with rationale, confidence with rationale, category, why-now or null, what not to assume, open questions.
- A timing plan: window, cold-after date, cadence, channel order, angle.
- A watchlist: resolved accounts with classification, signal specification, stakeholder coverage plan, ranked queue with decisions.

## Quality bar

- Every signal has an event date taken from the event, not the article.
- Irrelevant signals stop at the relevance gate with a reason.
- Strength and confidence are scored separately, each with a rationale.
- Why-now is either cited from the event or null.
- Every interpretation states what it does not prove.
- Open questions are specific and answerable, and capped at five.
- Benchmark figures found in source material (reply rates, conversion multiples) come from vendor claims and are not used as targets until tested against your own data.
- No message refers to how the person was found.
