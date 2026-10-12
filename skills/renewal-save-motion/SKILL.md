---
name: renewal-save-motion
version: 1.0.0
description: "Use when a customer renewal is at risk, or when a renewal falls inside 120 days. Runs a renewal clock from T-120 with a CLEAN, WATCH, or AT-RISK verdict at each checkpoint, names the failure mode before acting (value gap, adoption gap, champion loss, sponsor shift, or competitive displacement), applies commercial levers in a fixed order with the discount last, decides save or release explicitly, and reports save rate by failure mode. Starts from a risk flag raised by upstream detection. Not for expansion on healthy accounts, or for the full customer success organisation design."
---

# Renewal save motion

## Purpose

Defending revenue is a system. Losing a dollar to churn cancels a dollar of expansion. Save windows close quietly: by the time a customer says they are leaving, they have usually been evaluating alternatives for weeks. The motion here is a fixed renewal clock that starts 120 days out, a diagnosis of the failure mode before any action, and a save-or-release decision that is made deliberately.

## When to use

- A risk flag already exists on an account, from a health scan, a drop in usage, a champion leaving, or an expansion attempt blocked by inactivity.
- A renewal falls within 120 days.
- A customer has gone quiet, asked for a downgrade, or sent a cancellation notice.

Entry condition: this skill runs on an account that is already flagged. Detection comes first. If nothing is flagged and no renewal is within 120 days, the company needs better detection, not this skill.

Route elsewhere when:

- The account is healthy and the question is expansion. Use `expansion-revenue-architect`, if it is in use, or the expansion process. The two motions do not run on the same account at the same time.
- The question is how the whole customer success team is organised. Use `cs-operations`.
- The question is which accounts are at risk across the base. Use the health scanning process. This skill starts where that process ends.

## Inputs

- The renewal date, the contract value, and the owner.
- Usage trend over the last 90 days, support history, and sponsor and champion status.
- Who the economic buyer is, and whether they have engaged in the last 60 days.
- Any downgrade or cancellation request, with the wording the customer used.
- The value the customer was promised at signature, and the evidence of value delivered since.
- Any competitor known to be in the account.

## Procedure

### Step 1: Run the renewal clock

Every renewal runs the same clock, whatever its health. Healthy accounts pass each checkpoint quickly. Flagged accounts go into the save motion.

| Checkpoint | Action |
|---|---|
| T-120 | Name the renewal owner. Pull the health verdict: usage trend, support pattern, champion status, sponsor status. Give a verdict: CLEAN, WATCH, or AT-RISK. |
| T-90 | AT-RISK accounts enter the save motion (Steps 2 to 4). WATCH accounts get a value recap, and a new verdict at T-60. CLEAN accounts get the renewal packet drafted. |
| T-60 | Commercial terms on the table for CLEAN and recovered accounts. No surprises after T-60. If the price is changing, the customer should have heard it by now. |
| T-30 | Signature logistics only. If substantive objections first appear here, the motion failed earlier. Record that as the lesson, not as a late save. |

Renewal risk shows up in behaviour, such as declining logins, abandoned features, and a silent sponsor, well before it is spoken. If the company first learns of the risk within 60 days of renewal, the detection layer is the real problem. That rule of thumb is practice-based.

### Step 2: Name the failure mode before acting

A save play aimed at the wrong failure mode speeds up the churn. Classify the account first.

1. **Value gap.** The customer uses the product but cannot show that it is worth the money. The missing piece is an impact story in their own numbers. Save play: build a value recap from their system data, and walk the economic buyer through it, not only the daily users.
2. **Adoption gap.** They have stopped using it, or never fully started. The question is whether the problem still exists for them. Save play: narrow to the one workflow that hurt when they bought, relaunch that workflow only. Re-onboarding everything convinces no one.
3. **Champion loss.** The person who championed the product has left, and contact has gone quiet. Treat this as a new sale into the same account. Save play: find out who inherited the problem, and brief them as a stranger inheriting a paid solution. They do not owe the company continuity. Also refer the departed champion to the revival process (`closed-lost-revival`). One event, two plays.
4. **Sponsor shift.** A reorganisation, a new executive, or a change of strategy has moved the decision elsewhere. Save play: an executive-level re-anchor on the new agenda. A feature demo cannot fix a political change.
5. **Competitive displacement.** An alternative is being actively considered. Save play: a case for switching costs, plus a roadmap commitment with a date, delivered by someone senior. If the company discovers this at T-30, assume it is negotiating an exit, and aim for a dignified exit that keeps the door open.

### Step 3: Apply the commercial levers in order

The discount is the last lever. It buys silence, not adoption. It also reprices every future renewal at that account, and every account that hears about it.

1. **Scope right-sizing.** Fewer seats or modules that are truly used. A smaller contract that stays retains more revenue over two years than a larger one the customer resents.
2. **Term restructure.** A shorter renewal with success criteria written in, or a multi-year deal with protection, depending on which side is uncertain.
3. **Service injection.** Implementation help, training, or an owned success plan. It costs margin once. A discount costs margin every year.
4. **Pause instead of cancel,** where the platform allows it. This keeps the data, the relationship, and the route back.
5. **Price concession, last.** Always exchanged for something real: a case study, a longer term, an expansion option, or a reference. Never given for free.

### Step 4: Decide save or release

Some accounts should churn. Buyers who were wrongly fitted in an over-eager quarter, and companies that have moved away from the problem, are examples. Fighting every churn teaches the team that retention means begging.

Decide explicitly at triage, by checking three things:

- Is the fit still right?
- Is the problem still real?
- Do the economics still make sense?

If two of the three hold, fight. Otherwise, release well. This rule is practice-based.

A released account gets a clean exit, a data handover, and a standing re-entry premise: "If the trigger that broke this changes, here is the route back." A well-released account can be a revival candidate later. A badly released one becomes a bad review that prospects read.

### Step 5: Record an autopsy for every outcome

Every loss, saved or released, gets an autopsy in the same loss-pattern library used by `closed-lost-revival`. Record the failure mode, the first detectable signal, and the number of days between that signal and the first action. The library is how the next quarter's saves start earlier.

## Scorekeeping

- **Save rate by failure mode,** never blended. A 60% save rate on value gaps and a 10% rate on competitive displacement are two different businesses, and a blended figure hides both.
- **Signal-to-action lag:** the days from the first risk signal to the first human action. This is the number the motion exists to shrink.
- **Concession cost per saved dollar,** so the team can see whether service injection beats discounting on evidence.
- **Gross revenue retention each quarter,** against the reference points in the source: a median near 90% and top-quartile above 95% for private SaaS, from industry surveys. Segment it the way the board does.

## Output

- The renewal calendar for the next 120 days, with each renewal's owner and verdict.
- For each AT-RISK account: the failure mode, the save play, the lever sequence, and the save-or-release decision with its reasoning.
- The signal-to-action lag for the period, and the save rate by failure mode.
- Any account released, with its exit and re-entry premise.
- Autopsy entries for the closed outcomes.

## Quality bar

Every renewal within 120 days has a named owner and a written verdict. There are no commercial surprises inside 60 days. Each save names its failure mode before a play is chosen, and the play matches the mode. The discount is the last lever, and each one is exchanged for something. Save rate is reported by failure mode. Watch for generic save plays, discounts offered first, renewals discovered in the last month, and a blended save rate that hides a weak segment.

## Diagnostic questions

1. List the renewals due in the next 120 days. Who owns each one, by name, today?
2. For your last five churns, on what date was the risk first visible in system data, and on what date did a person first act? The gap is the motion's real latency.
3. In the last year, what share of saves led with a discount, and what did those accounts do at the following renewal?
4. When a champion leaves a customer account, what happens automatically today? Is anything triggered?
5. Can the team produce a value recap in the customer's own numbers for the top ten accounts within one day? If not, the value-gap play has nothing to work with.
