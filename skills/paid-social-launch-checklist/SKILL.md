---
name: paid-social-launch-checklist
version: 1.0.0
status: draft-for-review
description: "Use before the first live paid social campaign for a high-value B2B offer, to confirm measurement and audiences are ready. Covers conversion events that fire on completion rather than on click, the priority order when several events fire on one page, domain verification, a server-side events route where the browser misses conversions, remarketing and exclusion audiences built before any prospecting, and a test lead traced from the ad to the CRM. Not for the optimisation of a live campaign (see paid-social-optimisation-playbook) or for the choice of audience strategy (see paid-social-audience-strategy)."
sources:
  - "Paid social setup and tracking (MIT, Ivan Falco): the conversion events for lead generation, firing on completion rather than on click, the priority setting when several events fire on one page, domain verification before scaling, the server-side events route to recover conversions the browser misses, the remarketing audiences of thirty, ninety and one hundred and eighty days, the exclusion audience of employees, the first-campaign sequence, and the pre-launch checklist"
  - "Removed: the named platform's menu paths, the named tag manager and its configuration steps, the named form type and its settings, and the step-by-step interface instructions. The checklist is kept in general terms"
  - "Adapted for GTM-360: the remarketing windows are the source's defaults, kept as defaults. The rule that a test lead must be traced to the CRM before spend is an author addition"
---

# Paid social launch checklist

## Purpose

A paid social campaign that launches without working measurement spends budget and then cannot show what it bought. The platform optimises on whatever conversion it is told about, so a wrong event at launch teaches it the wrong thing for weeks. This checklist confirms the measurement base and the audiences before the first pound or dollar is spent.

## When to use

- A paid social campaign for a high-value B2B offer is about to launch for the first time.
- A new domain, landing page or conversion path is being added to an existing account.

Route elsewhere when:

- The campaign is live and underperforming. Use `paid-social-optimisation-playbook`.
- The question is which audience strategy to use. Use `paid-social-audience-strategy`.
- The question is server-side conversion feedback from the CRM stages. Use `conversion-feedback-to-ad-platforms`.

## Inputs

- The landing page or form the campaign will drive to, and the thank-you page.
- The conversion event the business values most, and which other events occur on the same page.
- The root domains used in any ad or landing page.
- The customer list, the site traffic available for audiences, and the employee list for exclusions.
- The destination for leads, such as the CRM, and who checks it.

## Procedure

1. **Set the conversion events.** For lead generation, use a lead event, and a sign-up event where sign-up is a key conversion. Fire each event when the action completes, on the thank-you page or after successful form validation. Never fire on the button click.
2. **Set the priority order** when more than one event fires on the same page, so the event the campaign optimises for ranks above page views and lower-funnel events.
3. **Install the measurement base on every relevant page,** and confirm it fires, using the platform's own event diagnostics or a browser check. Check the thank-you page specifically.
4. **Verify each root domain** used in the campaign, before scaling spend. Verification can take minutes or up to about seventy-two hours, so start early.
5. **Add a server-side route** for the conversion events, once the browser events are firing. It recovers conversions that browser blockers and privacy settings remove. Send the same event identifier from browser and server, so the platform counts each conversion once. This step is recommended for B2B, not mandatory at launch. If it is skipped, record that decision.
6. **Build the audiences before any prospecting:**
   - remarketing audiences from site visitors, at roughly thirty, ninety and one hundred and eighty days;
   - an exclusion audience of the company's own employees, and of known competitors where that applies;
   - the customer list, excluded from prospecting unless the campaign is for expansion.
   Prospecting audiences come after remarketing is running.
7. **Start with remarketing.** Launch the first campaign to site visitors, with a small daily budget. Use four to six distinct concepts, not small variations of one. Make the copy state who the ad is for.
8. **Check placements and creative format.** Use the default placements only if the creative fits each placement's shape. Otherwise limit the placements.
9. **Name campaigns with a fixed convention,** for example product, objective, audience and window.
10. **Trace one test lead end to end.** Submit a test lead, confirm it appears in the platform's event diagnostics, and confirm it reaches the CRM with the right owner and fields. Do not spend before this passes.

## Output

- A checklist with each item marked done, with the evidence for it.
- The list of audiences built, with their windows and exclusions.
- The test lead trace: the ad, the event, and the CRM record.
- Any step skipped, such as the server-side route, with the reason.

## Quality bar

Events fire on completion, not on click. The priority order is set where several events share a page. Each root domain is verified. Remarketing and exclusions exist before prospecting. A test lead has reached the CRM. Watch for a button-click event, an unverified domain on a scaled campaign, and a test lead that never reached the CRM.

## Rules

- Do not spend before the test lead has reached the CRM.
- Fire conversion events on completion only.
- Exclude employees from every prospecting audience.
- Build remarketing before prospecting.
