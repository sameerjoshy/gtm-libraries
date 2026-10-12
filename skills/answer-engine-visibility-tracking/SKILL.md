---
name: answer-engine-visibility-tracking
version: 1.0.0
status: draft-for-review
description: "Use to measure how a brand appears in AI-generated answers over time, and to trust or challenge the score that results. Sets a baseline by seeding the questions buyers actually ask an AI answer engine, in the buyer's words, across the engines and countries that matter, and tracks mentions, ranking against competitors, and the citation sources behind them. Includes an audit that traces any headline visibility score down to the individual answers behind it before the score is explained. Not for choosing which content to build (see answer-engine citation drill-down)."
sources:
  - "AEO visibility tracking (MIT, Yahav Fuchs): the baseline method (defining the brand and its competitors, seeding buyer questions in buyer language, reading the visibility timeline and ranking), the rule to measure per engine and per country, and the mining of cited sources to show where content effort moves the score"
  - "AEO score audit (MIT, Yahav Fuchs): the three-step drill from aggregate score to the scans behind it to the raw answer text, and the rule never to explain a score movement from the aggregate alone"
  - "Sampling before scoring (MIT, Huxley Peckham): asking each question several times per engine, a majority vote for presence, verbatim answers kept as dated evidence, three presence tiers (recommended, mentioned in passing, cited as a source) with the strictest tier reported separately, a grid of questions by engines in place of one aggregate, and the rule that a changed question set is a break in the series, not a trend"
  - "Prompt set research (MIT, Elad Hefetz): harvesting buyer language from several sources with provenance tags, holding the brand back until a final pass so the set reflects category demand, personas mapped to awareness stages, branded prompts kept in their own topic, and a validated hand-off rather than an automatic import. The named monitoring platform and the named assistants are not restated"
  - "Removed: the named engines, the named monitoring tool, the command reference, and the specific scoring formulas, which are not restated. The score is treated as a summary of scans, not as a figure in its own right"
  - "Adapted for GTM-360: the rule to track a fixed set of prompts over time, and to change the set only with a dated note, is an author addition so that trends are not created by changing the questions"
---

# Answer engine visibility tracking

## Purpose

AI answer engines now shape how buyers hear about categories and vendors. A brand that is not mentioned in those answers loses consideration before anyone visits its site. This skill sets up measurement of that visibility, and keeps the resulting score honest: any movement is traced to the answers behind it before anyone explains it.

## When to use

- A team wants to know whether the brand appears in AI answers for its category.
- An AI visibility score has moved, and someone needs to know why.
- A client or leader asks for evidence behind a visibility number.

Route elsewhere when:

- The question is which content to create to earn citations. Use `answer-engine-citation-drill-down`.
- The question is a drop in organic search clicks. Use `organic-decline-diagnosis`.

## Inputs

- The brand and its competitor brands, and the topics the brand wants to be known for.
- The buyer questions, gathered from sales calls, support questions, and customer language.
- The engines and countries that matter to the business.
- The period for the baseline.

## Set the baseline

1. **Define the brand, its competitors, and its topics.** Competitor comparison is the readout that tends to matter most to leaders.
2. **Seed the prompts.** Write questions the way buyers ask them: "best option for this problem", "option A versus option B", "how do I solve this". Use buyer language, not the category's marketing language. Create them per topic, and spread them across the target engines and countries.
   - Harvest the wording from several places: sales calls, support questions, community questions, and comparison content. Tag each prompt with where its wording came from.
   - Hold the brand back until a final pass. Build the category prompts from demand, not from the brand's own copy, which produces questions nobody types.
   - Keep branded prompts, such as comparisons, alternatives and pricing questions, in a separate topic, so they do not inflate the category figures.
   - Map each persona to an awareness stage, and weight the set towards consideration and decision questions.
3. **Fix the prompt set.** Record the date and freeze the set. Change prompts only with a dated note, so trends are not created by changing the questions.
4. **Read the baseline:** which brands are mentioned, for which prompts, on which engines, and where the brand ranks against competitors.

## Track over time

- Run the fixed set on a regular schedule.
- Record, per engine and per country: whether the brand is mentioned, its position against competitors, and the sentiment of the mention.
- Record the sources the answers cite, so the team can see which pages and domains shape the answers.
- Ask each prompt at least three times per engine. Keep every full answer verbatim and dated. Report the vote count for each prompt, not only the verdict: three of three is a different fact from two of three.
- Report presence in three tiers: recommended by name, mentioned in passing, and cited as a source. Report the recommended tier on its own, because it tracks buyers arriving. Never blend the tiers.
- Show the results as a grid of prompts against engines, with the aggregate on top. The grid shows which prompts are won, which are contested, and which engine disagrees with the rest.
- Read movement with care. A change from none of three to three of three is movement. A wobble at the margin is noise. If the prompt set has to change, mark a break in the series and restate the baseline. Never join the old and new sets into one line.

## Audit a score before explaining it

When a visibility score moves, or a number needs proof, decompose it. Never explain a movement from the headline figure alone.

1. **Aggregate.** Pull the headline figures for the period: visibility percentage, mention count, number of scans, and average sentiment.
2. **Decompose.** Break the headline into the individual scans behind it. Find which scans registered a mention and which did not. A drop usually shows up in one engine, one country, or one topic.
3. **Read the raw answers.** For the scans that moved, read the full answer text. Check whether the brand was omitted, mis-described, or replaced by a competitor, and whether the answer itself changed.

Only after these steps is a score movement explained.

## Procedure

1. **Set the baseline** and freeze the prompt set with a date.
2. **Run the tracking** on schedule, recording the per-engine and per-country results.
3. **Report the trend** with the scans behind it, not only the headline.
4. **When a score moves,** run the three-step audit before any explanation.
5. **Record the sources** cited in the answers for the next content review.

## Output

- The baseline and the trend, per engine and country, with the prompt set and its date.
- The competitor ranking for each topic.
- The cited sources, ranked.
- For any score movement, the audit trail from aggregate to scan to raw answer.

## Quality bar

The prompt set is dated and frozen, and changed only with a note. Every reported movement is decomposed to the scans behind it. Explanations cite the raw answers. Watch for a score explained from the headline alone, a prompt set changed silently between periods, and prompts written in marketing language rather than buyer language.
