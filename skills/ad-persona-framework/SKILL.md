---
name: ad-persona-framework
version: 1.0.0
status: draft-for-review
description: "Use to turn an ICP segment into an ad persona: the description of the buyer in the terms an ad platform can actually target, covering demographic, firmographic, intent, consumption, and psychographic fields. Use when building targeting for a campaign, when audiences are generic and waste budget, or when user personas exist but have never been mapped to what the platform can target. Not for the copy written for the persona (see ad-copy-voice-of-customer)."
sources:
  - "Ad persona framework (MIT, Ivan Falco): the distinction between an ad persona and a user persona, the template components (demographic, firmographic, intent, consumption, and psychographic fields with goals, challenges, thinking, hearing, and seeing), and the rule that an ad persona must map to targeting the platform can use"
  - "Removed: the named listing sites and review platforms used as examples, and the named keyword research tool. These are replaced by categories"
  - "Adapted for GTM-360: the rule that an ad persona lists only fields the platform can target, and that the rest is for copy, is an author addition"
---

# Ad persona framework

## Purpose

A user persona describes who the buyer is. An ad persona describes how the buyer can actually be reached. Most companies have the first and not the second, so their targeting is generic and their budget reaches people who will never buy. This skill translates the ICP into a persona that a campaign can be built against.

## When to use

- A campaign is being built and the audience is undefined or generic.
- Targeting is wasting budget on the wrong roles or companies.
- A user persona exists, and no one has mapped it to what the platform can target.

Route elsewhere when:

- The question is the ICP itself. Use `icp-builder`.
- The question is the message for the persona. Use `ad-copy-voice-of-customer`.
- The question is the campaign structure. Use `paid-campaign-plan`.

## Inputs

- The ICP segments, with their firmographic definitions.
- Any user persona already written for the segment.
- A list of the platforms the campaign will run on, and what each can target.
- Customer and sales conversation notes that show how the buyer thinks.

## The template

**Demographic:** name, age range, location, and any other demographic field the platform actually supports. Keep it short. Demographic targeting is often weak for B2B.

**Firmographic:** the fields that matter most for B2B targeting:
- industry,
- company size,
- job titles and job functions,
- seniority,
- years of experience,
- skills listed on a professional profile.

**Intent:**
- Keywords the buyer searches for, researched with a keyword tool.
- Review or listing sites the buyer uses to compare options.

**Consumption:**
- groups the buyer belongs to,
- events they attend,
- publications and podcasts they follow.
Think about every place the buyer's attention already goes.

**Psychographic:**
- goals: what the buyer is trying to achieve,
- challenges: what stands in the way,
- thinking: what they are considering,
- hearing: what they keep hearing in the market,
- seeing: what trends and solutions they notice.

## Procedure

1. **Start from the ICP segment**, not from a blank page.
2. **Fill the firmographic fields** first. These are what most platforms can target.
3. **Mark which fields the chosen platforms can actually target.** Any field that cannot be targeted goes to the copy brief, not the targeting setup.
4. **Fill the intent and consumption fields** from research and from customer conversations.
5. **Fill the psychographic fields** from the words customers use, not from marketing language.
6. **Check the persona against the platform.** For each targeting field, confirm the platform offers it. Remove or flag any that do not.
7. **Name the persona** so the campaign plan can reference it.

## Output

- One ad persona per ICP segment, with each field marked as targetable or copy-only.
- The targeting settings for each platform, derived from the persona.
- A list of the psychographic points the copy should address.

## Quality bar

Every targeting field maps to something the platform can use. Psychographic fields come from customer language. The persona is named, so campaigns can reference it. Watch for personas that list fields no platform can target, demographic targeting presented as B2B targeting, and a persona with no source in customer conversations.
