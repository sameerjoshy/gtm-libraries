---
name: email-subject-and-copy-review
version: 1.0.0
status: draft-for-review
description: "Use to write or improve the subject line and body of a B2B marketing or newsletter email. Generates subject lines from named psychological triggers (curiosity, urgency, pain, authority, results, contrarian, value, action, empowerment, story, trend, and quick win), reviews the body against a checklist of copy rules (direct address, a hook that gets to the point, skimmable structure, a single contextual call to action, a closing line for the reader who skips to the end), and rewrites vague pain statements into specific ones. Not for the whole sequence (see saas-lifecycle-programs) or for detecting machine-sounding prose (see content-authenticity-review)."
sources:
  - "Email subject line generator (MIT, Daniel Bustamante): the principle that subject lines are high-leverage, the psychological trigger categories for matching a subject to an email's intent, and the output of several variations with preview text"
  - "Email copy optimiser (MIT, Daniel Bustamante): the copy checks on intro hook, direct address, mobile formatting, skimmability, a closing line, contextual calls to action, and paragraph structure"
  - "Pain is the pitch rewriter (MIT, Daniel Bustamante): the step that finds generic sections and rewrites them with specific pain, given three alternatives per section"
  - "Removed: the library of one hundred named frameworks, the named marketers and their quotations, and the example rewrites, none of which are reproduced"
  - "Adapted for GTM-360: the rule not to invent statistics or customer details in any rewrite, and the rule that a rewrite must still be true of the product, are author additions"
---

# Email subject and copy review

## Purpose

A subject line decides whether an email is opened, and the body decides whether it is read. Both are often written generically. This skill improves each in turn: it generates subject lines matched to the email's intent, reviews the body for copy problems, and rewrites vague statements into specific, true ones.

## When to use

- An email is drafted and the subject line is unclear or weak.
- Open rates are low, and the team wants alternatives to test.
- A draft reads as generic and does not convert.
- A sales or promotional email needs more specificity.

Route elsewhere when:

- The question is the whole email sequence. Use `saas-lifecycle-programs`.
- The question is whether the text reads as machine-written. Use `content-authenticity-review`.
- The question is the reader's pain in depth. Use `ad-copy-voice-of-customer` for customer language.

## Inputs

- The email's intent, and its audience.
- The draft subject line and body.
- Open rates and reply rates for earlier emails, where they exist, to judge the alternatives.
- Any real deadline the email can state. Without one, no urgency is written.

## Subject lines

Match the subject to the email's intent. Write five to ten options, each using a different trigger:

- **Curiosity:** an open question the email answers.
- **Urgency:** a real deadline. Never invent one.
- **Pain:** the problem in the reader's own words.
- **Authority:** a specific expert view or source.
- **Results:** a specific outcome the company can show.
- **Contrarian:** a view that challenges a common belief.
- **Value:** what the reader gets from opening.
- **Action:** a clear next step.
- **Empowerment:** what the reader can do.
- **Story:** a short narrative hook.
- **Trend:** a shift the reader will recognise.
- **Quick win:** a result in a short time.

Write a preview line for each recommended subject. For A/B tests, change one element at a time.

## Copy review checklist

Review the body against these checks:
1. **Hook.** The first line gets to the point, with no warm-up.
2. **Direct address.** The reader is addressed as "you" where that fits.
3. **Mobile formatting.** Short paragraphs and no wide tables.
4. **Skimmability.** Each paragraph carries one idea a reader can see at a glance.
5. **Specificity.** Generic claims are replaced with specific, true ones.
6. **One call to action,** placed where it fits the content, not repeated.
7. **Closing line.** A short final line for the reader who skips to the end.
8. **Paragraph structure.** No paragraph does two jobs.

## Pain specificity rewrite

Find sections that are generic, such as "we help you save time". For each, write three specific rewrites that describe the reader's situation in concrete terms. Keep only rewrites that are true of the product and that the company can support. Do not add statistics, customer names, or results that are not supplied.

## Procedure

1. **Read the email's intent** and the reader.
2. **Write subject lines** across the triggers, and select the strongest three.
3. **Review the body** against the eight checks.
4. **Rewrite generic sections** using the pain specificity method.
5. **Check every claim** against supplied facts. Remove any that cannot be supported.
6. **Recommend** one subject, its preview line, and a test plan for the next version.

## Output

- Five to ten subject lines, labelled by trigger, with three recommended and their preview lines.
- The copy review, with each check's result and the fix.
- The rewritten sections, with the reason for each.

## Quality bar

Subject lines match the email's intent. No urgency, statistic, or customer detail is invented. Every rewrite is true of the product. A test changes one element at a time. Watch for false deadlines, invented numbers, and subject lines that promise what the body does not deliver.
