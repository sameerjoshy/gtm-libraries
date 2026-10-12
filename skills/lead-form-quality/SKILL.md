---
name: lead-form-quality
version: 1.0.0
status: draft-for-review
description: "Use when a paid campaign collects leads through an in-platform lead form, to stop cheap leads that sales cannot use. Explains the social-amnesia problem (people who submit without remembering why, then deny knowing the company), sets form-type and friction choices, requires a work email, and adds one to three qualification questions. Use alongside the decision on whether a landing page would perform better. Not for the landing page itself or for the offer (see paid-offer-strategy)."
sources:
  - "Lead form optimisation for B2B paid campaigns (MIT, Ivan Falco): the trade-off between lead forms and landing pages, the social-amnesia problem and its fix through intentional friction, the choice between a volume form and a higher-intent form, the work-email requirement with its reason, and the rule on custom qualification questions (one to three, multiple choice)"
  - "Removed: the platform's field names and screen paths, and the named personal-email providers, which are replaced by a general description"
  - "Adapted for GTM-360: the claim that lead forms out-convert landing pages is restated as a tendency to test, not a rule. The custom questions are shown as examples, not required fields"
---

# Lead form quality

## Purpose

In-platform lead forms are easy to submit, so they produce volume. For B2B that volume often arrives with personal email addresses, people who do not remember submitting, and no buying role. Sales cannot follow up on them. This skill adds deliberate friction and qualification so the forms return leads a salesperson can use.

## When to use

- A paid campaign uses an in-platform lead form and sales reports low-quality leads.
- Leads are arriving with personal email addresses.
- Sales reports prospects who do not remember filling in the form.
- A team is deciding between a lead form and a landing page.

Route elsewhere when:

- The question is whether the offer is right. Use `paid-offer-strategy`.
- The question is measurement of lead quality over time. Use `paid-measurement-scorecard`.
- The question is the follow-up after a lead arrives. Use `inbound-demo-request-triage` for demo requests or `reply-handling` for replies.

## Inputs

- The platform and form type in use, and the fields it collects.
- Lead records with their email type, job title and company, and any sales feedback on them.
- The offer the form promises.
- The landing-page conversion rate for the same audience, if a landing page exists.

## The social-amnesia problem

Lead forms fill in automatically from the person's profile and submit in a couple of seconds. The person may not register what they signed up for. When sales calls, the prospect says they do not remember giving their details and asks where the company found them. This is the main quality problem with B2B lead forms.

The fix is intentional friction. More friction means more awareness, and more awareness means a higher quality lead.

## Lead form or landing page

- Lead forms tend to convert more people, but produce lower-quality leads unless they are qualified.
- Landing pages tend to produce higher-quality leads when they convert well.

Start with a lead form to validate the audience quickly. If a landing page can convert at an acceptable rate for a solution-aware audience, use it for higher quality. Keep investing in the landing page so the lead form is not the only route.

## Form type

| Form type | Behaviour | When to use |
|---|---|---|
| Volume | Easy to submit, auto-fills aggressively | Early audience validation, when raw volume matters most |
| Higher intent | Adds a review step before submission | Default for B2B, except fast validation tests |

## Work email

Require a work email. By default, the platform fills in the person's personal login email, which is rarely useful for B2B follow-up. Set the form to require the person to type a work email.

Why it matters:
- Personal email addresses are poor for sales follow-up.
- Requiring a work email filters out people who are not buyers.
- Typing an address is a friction point, and the people who type a work address tend to have more intent.
- Sales gets an address it can use.

## Qualification questions

Add one to three custom questions. They are the most effective lever on lead quality. Use multiple choice, with options the sales team can act on. Examples:

| Question | Purpose | Options |
|---|---|---|
| Current monthly spend on the problem | Budget | Bands that match the price list |
| Company size | Firmographic fit | Bands that match the ICP |
| Biggest challenge with the problem | Pain | Specific options drawn from customer language |
| Role | Buying role | Executive, senior leader, manager, individual contributor |
| Timing | Urgency | Now, within three months, within six months, exploring |

Keep the questions short. Each extra question reduces completion, so add only what sales will use to qualify.

## Procedure

1. **Decide form versus landing page** using the test above.
2. **Choose the form type.** Use higher intent by default.
3. **Require a work email.**
4. **Add one to three qualification questions,** each tied to a decision sales makes.
5. **Check completion and quality together.** A form that completes well but produces leads sales cannot use has failed.
6. **Track the share of leads that sales accepts** as the quality measure, alongside cost per lead.

## Output

- The form or landing-page decision, with the reason.
- The form settings: type, work email, and the qualification questions with their options.
- The quality measure to track.

## Quality bar

Every form requires a work email. Qualification questions map to sales decisions. Quality is measured by the share of leads sales accepts, not only the cost per lead. Watch for personal-email leads accepted into the CRM, questions no one will use, and forms judged only on volume.
