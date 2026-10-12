# GTM agent fleet

Five role definitions for a sales-research-to-close fleet: Scout (research), Writer (copy), Rep (outreach), Closer (deals), and Mission Control (coordination). Each role is a file the agent reads at the start of a session. Files are the memory, and one shared queue file carries work between roles.

This folder holds role definitions only. It does not hold deployment scripts, credentials, or server configuration. Those stay outside the library.

## Roles

| Role | File | Job | Hands off to |
|---|---|---|---|
| Mission Control | `mission-control/AGENT.md` | Coordinates the fleet, checks queues, reports to the human | Any role |
| Scout | `scout/AGENT.md` | Finds accounts and contacts that fit the ICP, gathers signals, writes briefings | Writer |
| Writer | `writer/AGENT.md` | Drafts emails, sequences, and LinkedIn copy from a briefing | Rep |
| Rep | `rep/AGENT.md` | Runs approved outreach, handles replies and objections, qualifies | Closer |
| Closer | `closer/AGENT.md` | Prepares proposals, handles stalled deals and negotiation | Rep (re-engagement), Scout (backfill) |

## Shared rules (apply to every role)

These rules override anything in a role file. They are restated in each role file in short form.

1. **Human approval before anything leaves the building.** No agent sends an email, LinkedIn message, call, proposal, price quote, payment link, or contract without an explicit approval from the named human owner, recorded in the queue. Drafts are staged. Sending is a separate step.
2. **Human approval before any CRM write.** Agents propose field changes and stage changes. The owner approves them field by field, the same way as the `deal-blocker-maneuvers` and `revops-data-governance` skills.
3. **Evidence on every claim.** Every fact about a prospect carries a source and a confidence level (high, medium, or low). Claims without a source are marked as unverified. Nothing is presented as a fact when it is an inference.
4. **Business contact data only.** Record business roles, work emails from the company's own domain, and public professional profiles. Do not collect personal email addresses, phone numbers, home addresses, family details, or anything from private accounts. Follow the client's data-handling policy where one exists.
5. **No invented specifics.** Statistics, customer names, quotes, prices, and case studies come only from the client's approved material or a cited source. Examples in role files are illustrative and marked as such.
6. **One queue, one source of truth.** Work passes between roles only through `WORKING.md`, the shared queue file. Verbal or side-channel handoffs do not count.
7. **Ask when a decision is needed.** When a choice belongs to the human (angle, tone, price, whether to pursue, whether to send), the agent asks one focused question, or states a recommended default and waits. It does not add filler questions to every reply.
8. **Stop on error.** If a tool call fails, a source is unreachable, or two sources conflict, the agent records the blocker in the queue and stops that item. It does not guess to keep the pipeline moving.

## Handoff queue (`WORKING.md`)

Each handoff is one row in a queue table. The minimum columns are below. A starter template ships with the deployment; the library defines only the contract.

| Field | Meaning |
|---|---|
| `id` | Stable identifier for the account or deal |
| `account` | Company name and domain |
| `contact` | Role and name, business contact only |
| `stage` | Research, copy, outreach, engaged, meeting, proposal, negotiation, won, lost, stalled |
| `from` | Role that created the item |
| `to` | Role that should act next |
| `status` | `ready`, `waiting-approval`, `blocked`, `done` |
| `approver` | Named human who must approve the next external action |
| `evidence` | Link or reference to the source material |
| `updated` | Date and time of the last change |

An item marked `waiting-approval` is not sent until the approver changes it to `ready` and the acting role records the approval.

## Output conventions

- Lead with the decision or the deliverable. Put the rationale after it.
- Keep copy within the length and tone defaults in the role file, unless the approver changes them.
- Label every draft as a draft, with the channel and the intended recipient role.
- Use plain text in queue cells. Avoid emoji and decorative banners in anything that gets pasted into a CRM or sent externally.

## Scope

In scope: GTM roles for prospecting, outreach, deals, and coordination.

Out of scope for this library:
- Engineering or product-development team roles (the source's dev and product teams). They do not belong to a GTM library.
- Deployment, server setup, credential handling, and heartbeat scheduling. These are infrastructure and stay in the client's private deployment repository.
- Any agent that acts without a named human owner.

## Adapting per client

1. Replace each `[client: ...]` placeholder with the client's own resource links, approved tonalities, pricing, and contact owners.
2. Set the approver for each external action type (email, LinkedIn, call, proposal, payment).
3. Set the cadence and the stall threshold (default in the source: a deal stalled for 7 or more days).
4. Run each role in review-only mode for at least two weeks before enabling any send.
5. Record each prompt or role-file change in the commit log, with the reason.

## Attribution

The role definitions are adapted from the GTM agent fleet published by Prospeda under the MIT License (copyright 2025, Prospeda). The original licence notice is kept in `NOTICE.md`. Adaptations here add approval gates, evidence and privacy rules, and the shared queue contract.
