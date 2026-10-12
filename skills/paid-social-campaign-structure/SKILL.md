---
name: paid-social-campaign-structure
version: 1.2.0
description: "Use when structuring paid social campaigns for B2B high-value offers in three phases. Phase one validates which audiences produce qualified leads, using separate budgets per audience with the same ads in every audience. Phase two tests creative concepts inside the winning audience with a shared budget. Phase three moves to automation once the inputs are proven. Covers the validation criteria (judged in the CRM, not the ad platform), the consolidation rules, and the minimum test length. Not for the audiences themselves (see `paid-social-audience-strategy`) or for the automation settings (see `paid-automation-controls`)."
---

# Paid social campaign structure

## Purpose

Paid social campaigns for B2B often fail because the budget is spread and judged in the wrong place. Creative is tested before the audience is proven, and results are judged on cheap clicks rather than qualified leads. This skill sets a three-phase structure that tests one variable at a time and judges each audience on the CRM outcome.

## When to use

- A team is launching paid social for a high-value B2B offer for the first time.
- A new offer or a new market segment is being tested on paid social.
- Campaigns are running, but the team cannot say which audience is worth scaling.

Route elsewhere when:

- The question is how to build the audiences. Use `paid-social-audience-strategy`.
- The question is the automated delivery settings. Use `paid-automation-controls`.
- The question is the creative angles. Use `ad-creative-as-filter`.
- The question is how the platform receives qualified outcomes. Use `conversion-feedback-to-ad-platforms`.

## Inputs

- The audience candidates: customer lookalikes, third-party segments, interest and title targeting, and broad targeting.
- The offer and the creative set, with at least three to four ads for each audience.
- The CRM fields for title match, firmographic match, and lead-to-qualified conversion.
- The total budget for the test.

## Procedure

### Phase 1: Audience validation

**Purpose:** find which audience sources produce qualified leads, before spending on creative testing.

**Structure:**
- One campaign for the test.
- One ad set per audience candidate, each with its own fixed daily budget.
- The same three to four ads in every ad set, so the only variable is the audience.

**Rules:**
- Use separate fixed budgets for each audience, not a single shared budget. A shared budget lets the platform move money toward the cheapest audience and starve the others.
- Turn off any automatic expansion of the audience, so each ad set reaches only the audience defined for it.
- Run for at least two to four weeks.
- Judge each audience in the CRM, not in the ad platform, on: title match to the ICP, firmographic match, lead-to-qualified conversion, cost per qualified lead, and the quality score from sales calls.

**Exit:** stop audiences producing low-quality leads. Take the strongest one or two into Phase 2.

**Simpler alternative:** test only two ad sets, broad against interest-based, for two to four weeks, and keep the better one.

### Phase 2: Creative scaling

**Purpose:** scale the proven audience by testing creative concepts inside it.

**Structure:** one campaign for the winning audience, with one ad set per creative concept. Each concept has three to four variations. The budget is shared across the concepts, so the platform can favor the strongest.

**Rules:**
- Test concepts, not single ads, so the result reflects an angle rather than one execution.
- Keep the audience fixed while the concepts are tested.

### Phase 3: Automation

Move to automated delivery only after both the audience and the creative are proven. See `paid-automation-controls` for the rules.

### Sequence

1. **Name the audience candidates** and set each one's fixed budget.
2. **Load the same ads** into every audience for Phase 1.
3. **Turn off automatic audience expansion.**
4. **Run for two to four weeks,** then score each audience in the CRM.
5. **Take the winners into Phase 2** and test creative concepts inside them.
6. **Consolidate** the winning ad sets into a single campaign only after the results are stable.

## Output

- The phase, the structure, and the budget for each ad set.
- The CRM scorecard for each audience, with a keep, cut, or test-further decision.
- The creative concepts under test in Phase 2.

## Quality bar

Each phase changes one variable. Audiences have separate budgets in Phase 1. Audience quality is judged in the CRM, not on click cost. Tests run for at least two weeks. Watch for a shared budget that hides the weak audiences, creative tested before the audience is proven, and a Phase 1 winner judged on cost per click.
