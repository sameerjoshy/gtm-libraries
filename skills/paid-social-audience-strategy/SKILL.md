---
name: paid-social-audience-strategy
version: 1.1.0
description: "Use to build audiences for B2B paid social campaigns, where the platform's own professional targeting is weak and the audience quality depends on the data the company feeds it. Sets out the customer research to do before any audience is built (why customers bought, what triggered the search, who else was involved), the seed data to use (CRM contacts, customer lists, and third-party segments), how to build lookalikes from the best customers rather than all customers, and the exclusions. Not for the campaign structure (see paid-social-campaign-structure) or the creative (see ad-creative-as-filter)."
---

# Paid social audience strategy

## Purpose

Professional targeting on consumer social platforms is limited, so B2B paid social depends on the data the company supplies. The platform can find more people like the ones supplied, but only if the supplied data describes the right buyers. This skill sets the research to do first and the data to supply, so the platform's matching works in the company's favor.

## When to use

- A B2B paid social campaign needs an audience and the team is tempted to rely on native targeting alone.
- Campaigns reach many people who never become qualified leads.
- A list of customers or contacts is available and the team wants to use it for matching.

Route elsewhere when:

- The question is how to structure the campaign around the audiences. Use `paid-social-campaign-structure`.
- The question is which ads to show. Use `ad-creative-as-filter`.
- The question is how the platform receives qualified outcomes. Use `conversion-feedback-to-ad-platforms`.

## Inputs

- The CRM contacts, with their titles, firms, and stage.
- The customer list, and each customer's value and fit.
- Third-party data segments available for the platform, if any.
- Customer interviews or call notes that show why people bought.

### Step one: research before building

Before any audience is built, answer these from customer interviews and call notes:
- Why did they buy, and what problem were they trying to solve?
- What triggered the search? Was it a change in role, a new mandate, a failure of the existing tool, or a deadline?
- Who else was involved in the decision?
- What did they look at before choosing?

The answers decide which job titles, company sizes, and situations go into the audience.

### Step two: choose the seed data

- **CRM contacts that match the ICP** are the most direct seed. Match them by title and firm, then remove any that do not fit.
- **Customers at the top of the value range** are better seeds than the full customer list, because a lookalike built from every customer copies the weakest ones too.
- **Third-party segments** can supplement the seed, but check their fit against the ICP before using them.

### Step three: build the audiences

1. **Matched audience** from the CRM contacts, after the fit filter.
2. **Lookalike audiences** from the top-value customers, at a narrow match level first. Widen only after the narrow audience is tested.
3. **Interest and title audiences** from the research in step one, as a comparison group.
4. **Broad audience** as a control, to show whether the defined audiences add anything.

### Step four: set the exclusions

- Remove existing customers from prospecting audiences, unless the campaign is for expansion.
- Remove the company's own employees and known competitors.
- Remove contacts who have already been through a closed-lost cycle within the period set by the team, unless the campaign is for re-engagement.

### Sizing the audience and reaching situations

- **Cold audience size.** As author defaults: an ideal of about 150,000 people. Under about 10,000, the audience stalls. Over about 500,000, it dilutes. Calibrate these to the account's own delivery.
- **Persona too small.** If the primary persona builds to under about 25,000, move it into account-based targeting rather than broadening the audience to fill it.
- **Situation-based buyers are reached by message.** A recent loss, a contract ending, a new mandate or a funding round cannot usually be filtered for. Reach them with a message that names the situation, and let people self-select. Use a third-party signal only as a proxy, and check its fit.
- **Broad expansion options stay off** by default, so the platform does not spend on people outside the defined audience.

## Procedure

1. **Complete the research** and write the answers down.
2. **Clean the seed data** and apply the fit filter.
3. **Build the four audience types** in step three.
4. **Apply the exclusions** in step four.
5. **Test the audiences** in the structure set out in `paid-social-campaign-structure`.
6. **Refresh the seed** on a regular schedule, so the lookalikes reflect the current buyer.

## Output

- The research answers, in brief.
- The seed data, the fit filter used, and the number of matched contacts.
- The audience list, with each audience's type and its exclusions.

## Quality bar

Research comes before the audience is built. Seeds are filtered for fit. Lookalikes come from the best customers. Exclusions are applied to every prospecting audience. Watch for audiences built from the whole customer list, lookalikes that copy weak customers, and a campaign with no broad control.
