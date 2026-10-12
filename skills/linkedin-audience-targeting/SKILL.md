---
name: linkedin-audience-targeting
version: 1.0.0
description: "Use to size, target and maintain a LinkedIn audience for B2B campaigns. Covers audience size by funnel stage, the job title or job function choice, seniority and company size splits, company and contact list targeting, the exclusions to apply, and the rules that keep audience expansion and the network placements off. Not for the campaign structure or budget (see abm-strategy-planner) or for retargeting segments across channels (see abm-retargeting-segments)."
---

# LinkedIn audience targeting

## Purpose

On a professional network, the audience decides results more than the creative does. A cold audience that is too tight drives up costs, and one that is too broad spreads the budget too thin to be remembered. This skill sizes the audience for its stage, sets the targeting method, applies the exclusions, and keeps the settings that waste budget switched off.

## When to use

- A new LinkedIn audience is being built for a cold, nurture or conversion stage.
- An existing audience is getting high cost, low reach or off-target impressions.
- A team is choosing between job titles and job functions.

Route elsewhere when:
- The question is the campaign structure or the budget. Use `abm-strategy-planner`.
- The question is retargeting across channels. Use `abm-retargeting-segments`.
- The question is the campaign level. Use `abm-campaign-level-choice`.

## Inputs

- The funnel stage the audience serves: cold, nurture or conversion.
- The buyer's job titles and functions, and their seniority.
- The target company sizes, and the companies in the ICP.
- The monthly budget for the audience.
- Customer, competitor and existing-contact lists, for exclusions.
- The platform's current audience rules, checked before each build.

## Procedure

1. **Size the audience for its stage.** As defaults: a cold audience around 50,000 members, up to 100,000 only with budget to reach frequency, and 10,000 to 20,000 on a small budget. A nurture audience of 1,000 to 30,000. A conversion audience of 1,000 to 5,000. An audience over about 100,000 rarely makes sense on a normal budget, and one over about 300,000 almost never does. Below about 10,000 for a cold audience, costs rise sharply.
2. **Fix the audience when the size is wrong.** Too tight: broaden by adding a related job function or an adjacent industry. Too broad: narrow by seniority, company size or industry. A retargeting audience below about 500 needs a larger top-of-funnel budget to fill it, or a longer lookback window.
3. **Choose job title or job function, not both.** Job titles give precision at higher cost and suit a small, known list of titles. Job function with seniority reaches more people at lower cost but needs weekly exclusion of irrelevant titles. On the platform, job titles and seniority cannot be combined in the same campaign, so choose one approach.
4. **Protect the business development function.** On the platform, the business development function includes C-suite roles. Do not exclude it wholesale if the ICP includes executives. Use seniority exclusions instead.
5. **Set seniority and size splits.** Exclude unpaid, training and entry seniority from B2B campaigns, since those roles lack purchasing authority. Where the product is used by one group and bought by another, split the campaigns: directors and above for the business case, managers and seniors for daily use. Use employee count rather than revenue, since revenue for private companies is an estimate. Start with two size splits, not three. The 500-employee boundary is the default enterprise cut-off.
6. **Use company lists for account targeting.** Upload the account list and layer persona filters on top. Each filter reduces the matched audience, so check that the final audience still clears the platform's minimum. Contact lists match poorly where people use personal emails, so pair them with a company list.
7. **Apply the exclusions in priority order.** Converted users first, then competitors, existing customers, website visitors in cold campaigns, unpaid and entry seniority, the company's own employees, and agency staff. Keep cold, nurture and conversion audiences non-overlapping, so the same accounts are not bidding against themselves.
8. **Keep three settings off.** Audience expansion, which the platform switches on by default, is off. The audience network placements are off, because their quality is low for B2B. Lookalikes are a last resort, tested on a small budget first, and rebuilt quarterly from the current customer list.
9. **Build retargeting before the first campaign.** Create the website visitor, video viewer, form opener and page audiences with their lookback windows before launch. Thirty days suits high-intent pages, 90 days standard nurture, and 180 days a low-cost sustainer.
10. **Split the audience for scale.** Split by region or size only when each split can be funded to its own minimum, and review each split on its own results.

## Output

- The audience size for the stage, with the size check against the budget.
- The targeting method chosen, with the reason.
- The seniority and size splits, with the reason for each.
- The exclusion list in priority order, with the lookback windows.
- The settings confirmed off, and the retargeting audiences to build before launch.
- The platform rules checked, with the date of the check.

## Quality bar

The audience size matches its stage and budget. Job title and job function are not mixed in one campaign. Expansion and the network placements are off. Exclusions are applied in order, and the warmer stages are excluded from the colder ones. The platform minimums are checked on the day of the build. Watch for a cold audience under 10,000 on a small budget, a business development function excluded when executives are in the ICP, and retargeting audiences created after the campaign has started.

## Rules

- Confirm the platform's current audience rules before each build.
- Keep audience expansion and the network placements off unless tested and shown to help.
- Exclude unpaid, training and entry seniority from B2B campaigns.
- Set up retargeting audiences before launch. They are not retroactive.
- Label stage sizes and splits as defaults unless they come from the team's own results.
