---
name: linkedin-signal-triage
version: 1.0.0
status: draft-for-review
description: Use to turn LinkedIn activity around a team member into routed, scored signals, covering profile views, inbound connection requests, direct-message conversations, post comments and reactions, and engagement with a product-focused influencer post. Resolves each actor, applies dedup, internal, relationship, and fit gates, scores active signals more strongly than passive ones, writes to the CRM only for fully resolved and fit-matched actors, and proposes a next move for a human to approve. Never sends outreach. Not for writing the outreach itself (see linkedin-outreach) or for general buying-signal tracking (see signal-detection-and-timing).
sources:
  - "LinkedIn signal handling (MIT, Ariel Cohen, covering the profile-view, connection-request, DM-classifier, post-engagement, and influencer-engager handlers): the rule that an inbound connection request is an active first-party signal and scores differently from a passive profile view, the gate sequence (dedup, internal, relationship, fit), the rule that the CRM is written only for fully resolved, fit-matched actors, the repeat-engager escalation, the lone-reaction light touch, the verification that an influencer post is about the product before capture, and the rule that replies and sends stay with a human"
  - "Removed: the named webhook providers, enrichment and scraping services, chat channels, CRM names, the template placeholders, and the sub-skill references. Each handler is restated as a step in one sequence"
  - "Adapted for GTM-360: the active-versus-passive weighting, the repeat-engagement threshold, and the lone-reaction treatment are author defaults. Calibrate against the team's conversion data"
---

# LinkedIn signal triage

## Purpose

LinkedIn produces many small signals around one person: who viewed the profile, who asked to connect, who messaged, who reacted, and who engaged with an influencer's post about the product. Each is a weak alone. Handled ad hoc, they flood the CRM with unresolved names or get ignored. This skill applies one gate sequence to every actor and one scoring rule, so that a request from a decision-maker at a fit company is acted on, and a profile view from a student is not.

## When to use

- A profile-view, connection-request, or engagement notification fires for a tracked team member.
- A daily review of direct-message conversations is due.
- A product-focused influencer post has gone out and its engagers need capturing.
- A team is deciding whether LinkedIn activity is worth a process at all.

Route elsewhere when:

- The question is writing outreach. Use `linkedin-outreach`.
- The question is which buying signals to track in general. Use `signal-detection-and-timing`.
- The question is an inbound demo request from the website. Use `inbound-demo-request-triage`.

## Inputs

- The signal and the actor: name, title, employer and company domain.
- The team's own CRM record of the actor, and any earlier processing in the same window.
- The list of team members and company domains, to exclude internal activity.
- The fit rules the team uses for decision-makers and companies.

## Signal strength

Rank the signals before routing:

- **Active, first-party:** an inbound connection request, a direct message the person sent, a comment on the team member's post. The person chose to act. These can qualify on their own when the person is a decision-maker at a strong-fit company.
- **Passive:** a profile view, a lone reaction. These are logged as light signals. They become qualifying only when repeated or when the actor is already known to be in fit.
- **Campaign-driven:** engagement with a product-focused influencer post. Treat as a list to review, not as a set of individual leads.

## Procedure

1. **Resolve the actor.** Establish name, title, employer, and company domain. If the actor cannot be resolved, log the signal without a CRM write, and stop.
2. **Gate in order:**
   - **Dedup.** Has this actor already been processed in this window? If so, update the existing record and stop.
   - **Internal.** Is the actor on the team or from the company's own domains? If so, ignore silently. Team engagement is noise, not demand.
   - **Relationship.** Is the company already a customer, an open deal, or a closed-lost account? Route to the matching path: account team for a customer or open deal, a reactivation review for a closed-lost account. Do not treat it as net-new.
   - **Fit.** Does the company match the ICP, and is the title a buying role? Only fit-matched actors reach a CRM write as prospects.
3. **Score the signal.** Apply the signal strength above. An active signal from a decision-maker at a fit company is qualifying on its own. A passive signal needs repetition or a stronger fit before it qualifies. A weak persona caps the score at the awareness tier, however strong the company.
4. **Write to the CRM** only for fully resolved, fit-matched actors. Record the signal type, the date, and the source. Unresolved or unfit actors are logged to a separate record, not the prospect table.
5. **Escalate repeat engagers.** An actor who engages more than once within the window moves to a higher intent level, after a check that they are an active buyer and not a recurring fan. Only then is a personalised, multi-channel next move drafted.
6. **Handle direct messages in a daily pass.** Classify each conversation into a bucket: customer support, commercial, pipeline, re-engagement, prospect, partner, investor, community, or other. Update the account record and CRM. Score only the qualified buckets. Route partner and investor messages to their owners rather than the sales queue.
7. **Propose the next move, do not send it.** For each scored signal, draft one of two things: a reply for the thread owner, or a sequence queued for approval for the rest of the buying group. Nothing is sent without a human approving it.
8. **Post the outcome to one visibility channel** for each processed ICP-relevant signal, so the team can see what was acted on.

## Influencer post engagers

Before capture, check that the post is genuinely about the product. A broad topic filter is not enough. Then collect engagers, filter to fit companies and buying roles, score each company, and post one digest. Team members are removed from the list. The digest is a review list, not a set of sends.

## Output

- Per signal: the actor, the signal type and strength, the gates passed or failed, and the score.
- The CRM writes made, if any.
- The proposed next move, marked for approval.
- A daily summary of direct-message buckets and routed signals.

## Quality bar

No outreach is sent by the skill. Team and internal actors are dropped. The CRM holds only resolved, fit-matched actors. Passive signals do not qualify alone. A weak persona does not reach a qualified tier. Watch for profile views treated as demand, unresolved names in the prospect table, and repeat fans scored as active buyers.
