---
name: inbound-demo-request-triage
version: 1.0.0
description: "Use when a demo request arrives through a website form or webhook and the question is what happens in the next few minutes. Gates out requests with no usable work email, resolves the person and company, decides buyer persona before scoring, and routes the request on fit and persona, never on a tier number alone. Three outcomes: book a meeting for a qualified buyer, send a fit company's non-buyer a route to the buyer, or send a self-serve or out-of-fit account to a free trial. Not for scoring the account in general (see account-tier-scoring) or for an outbound reply thread (see reply-handling)."
---

# Inbound demo request triage

## Purpose

A demo request is a hand raised, and the default response, which books a meeting for everyone, has two failure modes. It sends the team into meetings with companies that were never going to buy, and it treats a junior analyst at a strong-fit company as if they were the economic buyer. This skill decides in the first few minutes which door a request goes through, and it records why.

## When to use

- A demo request form or webhook fires and the record needs routing.
- A backlog of requests needs triage.
- The team is debating whether every request should get a meeting.

Route elsewhere when:

- The question is the account's overall score. Use `account-tier-scoring`.
- The question is a reply in an existing thread. Use `reply-handling`.
- The question is a meeting that has already happened. Use `post-meeting-follow-through`.

## Inputs

- The submitted record: work email, and any name, title, or company the form captured.
- The company's self-serve floor, funding override, and top tiers.
- The decision-maker titles for the market.
- The booking link and free-trial link the team uses.

## Procedure

1. **Gate the email.** Extract the work email. Stop when there is none, or when it is a consumer domain (for example a general webmail provider). Post a low-priority note saying a request could not be processed, with the raw address if there was one. Do not enrich, write to the CRM, or send anything. Enrichment costs money and a personal address on a demo form is often a student, a competitor, or a bot.
2. **Resolve and write.** Resolve the person (name, title, profile) and the company from the email domain (size, funding, industry, target market). Create or update the contact and company, linked to each other, with a note recording the source, the date, and the address submitted. CRM writes are reversible and form the audit trail, so they need no approval.
3. **If no real company resolves,** that is a non-fit answer. Route to the non-fit path and say the domain could not be resolved.
4. **Decide persona before scoring.** Classify the submitter as decision-maker or not from title, against the market's list. Individual contributors, junior titles, non-go-to-market functions, and any unresolved title are not decision-makers. Persona is an input to scoring. Scoring first blends company and person into one tier, and the two can no longer be separated.
5. **Score the account with three directives:**
   - **Suppress the qualified alert for non-decision-makers.** Scoring still runs in full and tags and CRM state still update. Only the announcement is withheld. This keeps the qualified channel free of accounts where no buyer has raised a hand.
   - **Self-serve is not a full stop.** Apply the self-serve tags as normal, then still send the free-trial route. A small company asking for a demo is a strong trial audience.
   - **Funding override.** Before scoring, take the lower of the enriched and profiled employee counts and the total funding. If the company clears the override, keep it on the sales-assisted path, do not suppress the alert even for a non-decision-maker, and route it to the booking branch.
6. **Route on fit and persona, never on tier alone:**

| Outcome | Path |
|---|---|
| Competitor | Post nothing and send nothing. End silently. |
| Investor, partner or vendor, or government | One low-priority note naming the reason. No email. End. |
| Self-serve, or out of ICP | Free-trial route. |
| Fit, decision-maker | Booking route: a short email from the owner with the booking link. Post to the qualified channel. |
| Fit, not a decision-maker | Right-company route: a short email asking who owns the problem, with the booking link, and a note to the team. Do not post as qualified. |

7. **Send at most one outbound email.** The booking and right-company emails are the only sends. Do not send anything else from the form.
8. **Post one alert** to the team channel, whatever the outcome, so every request is visible.

## Output

- The CRM record, with source and date.
- The fit and persona verdict, with the reason for each.
- The route taken and the one email sent, if any.
- The team alert.

## Quality bar

Persona is classified before scoring. No request is routed on tier alone. Consumer-domain and competitor requests produce no outbound email. A funded company is not pushed to self-serve by default. Watch for every request booked regardless of fit, a junior title announced as qualified, and a self-serve company turned away with silence.
