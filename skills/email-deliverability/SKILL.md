---
name: email-deliverability
version: 1.0.0
description: "Use when emails land in spam, open rates drop, a domain or IP is blocklisted, a new sender needs to warm up, or a deliverability audit is wanted before volume is scaled. Produces either a severity-ranked audit of the sending setup or a root-cause diagnosis with a recovery plan and the thresholds to monitor. Covers infrastructure, data quality, content, and traffic shape. Not for the first cold campaign's launch checks (see cold-email-preflight)."
---

# Email deliverability

## Purpose

When email stops arriving, the cause is usually the sending setup or the way volume is applied, not the copy. This skill checks the setup in a fixed order, so the cheap and high-impact fixes come first. It also sets the monitoring thresholds that will pause sending before the damage spreads.

## When to use

- Emails are going to spam, or open rates have fallen.
- A domain or IP has been blocklisted.
- A new domain or mailbox needs a warm-up.
- A deliverability audit is wanted before volume increases.

Route elsewhere when:

- The campaign is about to launch. Use `cold-email-preflight`.
- The campaign is underperforming on replies or meetings. Use `outbound-performance-diagnosis`.

## Inputs

- Send volume by day and by mailbox provider.
- Open and reply rates by provider.
- Whether IPs are shared or dedicated, and the authentication records.
- Bounce data, with hard and soft bounces separated.
- What changed just before the problem appeared, such as a migration, a new list, or a volume increase.

## Procedure

1. **Choose the mode.** Proactive review audits the whole setup. An active problem is diagnosed from the change that preceded it.
2. **Scope the problem.** An open rate below about 10 percent at any provider is a deliverability signal, whatever is thought of open-tracking accuracy.
3. **Check the four pillars in order:**
   - **Infrastructure.** SPF, DKIM, and DMARC are present and verified. Check after any DNS or provider migration, since records can disappear. The server's announced name must match the IP's reverse DNS, because a mismatch is a common cause of blocklisting.
   - **Data.** Hard bounces above about 0.5 percent mean stop and clean the list. Soft bounces are often rate-related or temporary, so retry them over about 72 hours before treating them as hard. Check that bounces from an old platform were not re-imported after a migration.
   - **Content.** Ask whether the message looks like a scam to a filter: missing branding, HTML-only sending, bloated code, and a sender identity that does not match the domain.
   - **Traffic shape.** Often the largest factor. Throttle each provider separately. Do not raise volume by more than about 50 percent week over week. Spread large sends over three to four days.
4. **Classify the problem and prescribe:**
   - Blocklisted: remove the listing, but fix the cause first or it returns.
   - Content filtered at one provider: pause that provider for 24 to 48 hours, fix, and retest on an engaged segment.
   - Broken authentication: fix the records and wait for propagation before resuming.
   - New or damaged sender: warm up over about two to four weeks, starting with the most engaged recipients and increasing volume slowly.
     - Set a daily cap for each mailbox that rises with that mailbox's own age, not the campaign's. As a default: a handful of sends in week one, roughly doubling each week, full volume at about four weeks. A mailbox added to a mature team starts at week one.
     - Add volume through more mailboxes. Never push one mailbox past its cap.
     - Keep cold volume off the domain the business depends on. Use a separate sending domain for it.
     - Send within the recipient's working hours and on working days, and keep the first touch plain: no links, images, tracking or attachments until a human has replied.
     - A warm-up network's score is not evidence that a real list can be mailed. Judge readiness on real replies and on the bounce and complaint figures.
5. **Set the monitoring thresholds** that pause sending: bounce spikes, a complaint rate above about 0.3 percent, or one provider falling while the others hold. Show the current daily cap and the reason for it wherever the team sees sending. Do not raise a cap without stating what a cold mailbox at full volume risks.

## Output

- For an audit: findings ranked by severity, each with its evidence and fix.
- For a diagnosis: the cause, the evidence, and a dated recovery plan.
- The monitoring thresholds, and who is alerted when each fires.

## Quality bar

Each pillar is checked in order. Every figure cites its source data. Soft and hard bounces are reported separately. Traffic shape is reviewed per provider. Thresholds are written down before recovery begins. Watch for list cleaning before the infrastructure is checked, volume increases during a recovery, and provider tactics applied without evidence.
