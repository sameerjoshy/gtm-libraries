---
name: cold-email-preflight
version: 1.0.0
description: "Use in the hour before a cold email campaign goes live. Runs a checklist covering domain authentication, list verification, copy risk, day-one volume, and written kill-switch thresholds, then produces a launch or hold decision and the monitoring rules for the first week. Not for writing the copy or the sequence (see outbound-cold-email)."
---

# Cold email pre-flight check

## Purpose

Most cold campaigns that fail were set up to fail in the hour before launch: unverified addresses, a domain without authentication, links in the first message, and no agreed rule for stopping. This check takes about an hour and decides whether the campaign goes live. It also sets the stopping rules in advance, when the team is not yet under pressure to ignore them.

## When to use

- Immediately before any cold email campaign is launched.
- Before a new sending domain or mailbox is used.
- After a list has been changed, merged, or re-imported.

Route elsewhere when:

- The copy and sequence need writing. Use `outbound-cold-email`.
- A campaign has already failed and needs diagnosis. Use `outbound-performance-diagnosis`.
- Deliverability has broken down and needs recovery. Use `email-deliverability`.

## Inputs

- The sending domains and mailboxes, with their warm-up history.
- The list to be sent, and the verification results.
- The sequence copy, including every variable and its fallback.
- The planned daily volume and the day-one schedule.
- The named person who receives alerts.

## Procedure

1. **Check authentication.** Confirm the sending domain passes SPF, DKIM, and DMARC, and that link tracking uses a domain the team controls. Any failure is a hold.
2. **Verify the list.** Verify every address in the batch. Remove anything the verifier cannot confirm. The launch list should carry no known-bad addresses. The bounce budget is for the addresses that could not be checked in advance.
3. **Run the copy risk pass.**
   - The first message has no links and no attachments.
   - It reads as one person writing to one person.
   - Every variable has a fallback, so no prospect sees a raw placeholder.
   - Phrasing varies across the sequence, since identical text sent at volume is easy to filter.
4. **Check volume.** The day-one schedule stays within each mailbox's proven capacity. Volume ramps across the first week rather than starting at full size.
5. **Set the kill-switches in writing,** before the first send:
   - The bounce rate at which the campaign pauses automatically.
   - The placement or complaint signal that pauses it.
   - The person alerted when either fires.
6. **Decide.** Launch only if every check passes. Otherwise hold, and record the item that blocked the launch.
7. **Set the first-week watch.** Check bounce and reply rates daily, per mailbox. A spike in bounces means the list is weaker than it looked. Flat replies with healthy opens mean the copy is missing. Both healthy means the next step up in volume can be taken.

## Output

- The launch or hold decision, with each check's result.
- If held: the blocking item, its owner, and what would clear it.
- The kill-switch thresholds and the alert recipient.
- The first-week watch schedule.

## Quality bar

Authentication and list verification are recorded as passed, not assumed. The kill-switches are written before the first send. No first message contains a link or attachment. The campaign ramps through its first week. Watch for full-volume launches on day one, unverified lists, and thresholds decided after the numbers arrive.
