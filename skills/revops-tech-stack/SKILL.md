---
name: revops-tech-stack
version: 1.1.0
description: "Use to decide what the revenue technology stack should contain, to audit a stack that has grown without a plan, to evaluate a tool or decide build versus buy, and to decide where AI tools fit given the company's process and data maturity. Works capability by capability, not tool by tool, and sizes the stack to the company's stage. Use when the team says there are too many tools, the tools do not talk to each other, or someone wants to buy an AI tool. Not for strategy framing (see revops-strategy) or CRM data governance (see revops-data-governance)."
---

# Revenue tech stack architecture

## Purpose

Most stack problems are capability problems wearing tool names. A company buys a tool for a job it does not yet define, then buys another tool to fix the integration gap, then finds reps working around both. The fix is to start from capabilities, decide which tool owns each one, and size the whole stack to the stage the company is actually at.

The core rule: every capability the business needs has exactly one owner, the CRM holds the canonical record, and no tool is bought before its process is defined.

## When to use

- The team reports too many tools, overlapping features, or unclear ownership of data.
- A new tool is proposed, and nobody has said which capability it closes.
- Integrations break, or reps re-enter data by hand.
- Someone wants to buy an AI tool or build one.
- The stack has to be sized for the next growth stage.

Route elsewhere when:

- The question is the overall GTM strategy or pipeline design. Use `revops-strategy`.
- The question is data definitions and quality inside the CRM. Use `revops-data-governance`.
- The question is the warehouse, transformation, and reverse-ETL design. Use `gtm-data-architecture`.
- The question is the CRM implementation itself. Use `revops-salesforce`.

## Inputs

- Inventory of every tool: owner, annual cost including admin time, users, and stated purpose.
- Usage data by user and by month, pulled from the tools, not from license counts.
- The list of integrations and data flows, and the last time each one failed.
- The GTM process map, or at least the stages and handoffs.
- Company stage: ARR, number of GTM staff, number of segments, and the plan for the next year.
- The request or problem that triggered the review.

## Procedure

### Step 1: Think in capabilities, not tools

Replace "we need a sales engagement tool" with the capabilities behind it: automated prospect outreach, call recording and review, buyer intent signals, and so on. Then ask which tool, or which feature of a tool already owned, delivers each one.

Three reasons this matters:

1. Tools overlap. The CRM's built-in sequencing may cover most of what a dedicated engagement tool does. The dedicated tool then adds cost and complexity for a modest gain. Check before buying.
2. Capabilities depend on each other. Call intelligence is only valuable if its insights reach the CRM, coaching, and the process. The capability is changed rep behavior, not recording calls.
3. Stage changes the answer. A small team with a handful of reps does not need an enterprise account-based platform. A larger team across several segments may. Tools should follow the stage.

### Step 2: Map the core and intelligence layers

**Core layer (every revenue team needs these):**
- **CRM, the system of record.** Accounts, contacts, deals, activity, reporting, and workflow. Every other tool syncs to it. A satellite tool should never become the system of record.
- **Marketing automation, the demand engine.** Capture, nurture, score, and route leads, with real-time sync to the CRM. Lag between the two means leads fall through.
- **Engagement, the outreach layer.** Email, calling, meeting scheduling, and templates, with all activity logged to the CRM automatically. If reps must log by hand, they will not.

**Intelligence layer (add as data volume and maturity justify it):**
- Conversation intelligence, buyer intent and enrichment, customer success platform, and revenue intelligence or forecasting.

**Automation layer:**
- Integration platform (iPaaS), document and quoting tools, and data operations.

Each capability has one rule: it must integrate with the CRM, or it becomes shelfware. Set an entry threshold for each intelligence capability, expressed as ARR, headcount, or data volume, and do not buy until the threshold is met.

### Step 3: Apply the golden rules

1. **One owner per capability.** Two tools doing the same job create a dispute about which holds the canonical data.
2. **The CRM is the hub.** Data flows into the CRM. Reporting, forecasting, and pipeline management happen there. Satellite dashboards may exist, but the CRM is canonical.
3. **Process before platform.** Define the process, then select the tool that supports it. Buying a tool to discover the process produces a process shaped like the tool.
4. **Integration cost is real.** Every new tool adds maintenance. Budget for integration work each year as a share of tool spend (a default to calibrate). If the tool cannot integrate with the CRM, do not buy it.
5. **Stage-appropriate complexity.** Do not build a stack for a company three times the size. Do not run a large company's stack on a small company's setup.
6. **Automate the data, not the judgment.** Automate capture, sync, enrichment, and routing. Automate a decision only after the decision logic has been run by hand and proven.
7. **Composable beats suite only when integration is affordable.** An 80% suite solution often beats a 100% best-of-breed tool once integration effort is counted.

### Step 4: Size to stage

Stack composition grows with the company. As a planning frame, not a budget:

- **Early stage (under about $5M ARR, fewer than ten GTM staff).** A small core with a few satellite tools, usually three to five. The CRM's built-in features cover most needs.
- **Scale-up (about $5M to $25M ARR, ten to fifty GTM staff).** A larger set, typically six to twelve tools, with a formal integration owner and a documented data model.
- **Growth (about $25M to $100M ARR, fifty to two hundred GTM staff).** Twelve or more tools, dedicated integration and data ownership, and an annual stack review.

Pricing for each tool changes often and varies by seat count and usage. Replace these frames with the client's current quotes and invoices before any budget decision. Do not build a growth-stage stack at early-stage scale, and do not run a growth-stage company on an early-stage setup.

### Step 5: Value engineering, from lifecycle value to stack spend

The most useful use of the stack is insight. Find out which customers are worth the most across their full life, then point the stack at winning more of them.

1. **Score customers on lifecycle value, not deal size.** Include acquisition cost, sales cycle length, onboarding effort, retention, expansion, support cost, and advocacy. The best customers are the ones with the best ratio of lifetime value to cost to serve, which are not always the largest.
2. **Find the common attributes of the top segment.** Company size, industry, technology in use, entry use case, acquisition channel, and sales motion. This is the data-backed ICP, which may differ from the one written on a slide.
3. **Map each tool to the top segment.** Which tools help win and retain these customers? Which mainly serve segments with weak economics? Which capabilities are missing for the top segment?
4. **Reallocate.** Invest in the capabilities that serve the top segment. Reduce the ones that serve segments where full-lifecycle economics do not work.

### Step 6: Run the capability-value matrix

Place each tool on two axes: how well it delivers a capability the business needs, and how much value that capability creates.

- **Core platform (high fit, high value).** Keep. Maximize usage. Invest in training and integration.
- **Optimize (high fit, low use).** The tool works but people do not use it. Fix adoption through training, process, or configuration.
- **Question (needed capability, poor delivery).** Decide whether the tool or the process is failing. Fix the configuration first, then evaluate alternatives.
- **Cut (low fit, low value).** Remove it. Count the full cost: license, admin time, context switching, and data fragmentation. Redirect the budget.

Shelfware is the most common finding. A tool with under half of its licensed users active each month is underused, as a default to calibrate.

### Step 7: Evaluate a new tool

Score four dimensions. The weights are defaults.

- **Capability fit (40%).** Does it close a named gap? Does it replace a tool or add one?
- **Integration quality (25%).** How deep and reliable is the native CRM integration, and what does it cost to maintain?
- **Total cost of ownership (20%).** License, implementation, integration, training, admin, and switching cost, divided by the users who get value from it.
- **Vendor viability (15%).** Funding, customer base, roadmap, and market position. A strong tool from a vendor that may not last is a liability.

Do not decide on a demo. Ask the vendor who will make the tool work in the first ninety days. Green signs: a named implementation person, a hands-on onboarding of thirty to sixty days, a first workflow built with the client and handed over. Red signs: documentation and a ticket queue as the whole implementation plan, self-serve onboarding with no human support, and claims that setup takes an afternoon. AI tools need configuration, data, and iteration. A vendor that will not commit people to the first quarter does not believe its own product works without them.

### Step 8: Decide build or buy

Buy by default for GTM tools. RevOps is not a software development function, and the maintenance of custom tools usually costs more than the license.

Build only when all three hold:
- No vendor can do the capability well enough.
- The capability is a top priority for the business.
- It needs internal data or control that a vendor cannot provide.

Build where the company's method differs from what vendors assume, or where the signal is internal and proprietary. Buy the commodity layers: outbound automation, call recording, enrichment, meeting scheduling, and native CRM scoring.

### AI in the stack

### Maturity model

| Stage | Name | What it looks like | Human role |
|---|---|---|---|
| 1 | Ad hoc | One or two isolated tools, no integration, inconsistent use | Reviews all output |
| 2 | Programmatic | Three to five integrated tools with native CRM sync; standard use | Reviews before action |
| 3 | AI-assisted | Copilots and scoring inside the core workflow; deep two-way sync; high adoption | Acts on recommendations, audits weekly |
| 4 | AI-orchestrated | Agents acting across tools with defined lanes | Handles exceptions and sets policy |

To move between stages, document the process, clean the data, train the team, baseline the metrics, define the human review, and build a weekly audit into the cadence.

### Readiness check

Before recommending any AI tool in an area, check:

- Is the process documented? If not, fix the process first. AI amplifies whatever exists.
- Is the CRM data clean enough to act on? If not, run a data governance sprint first.
- Will the team use the output? Plan adoption before purchase.
- Are the metrics baselined? Without a baseline, ROI cannot be shown.
- Is the review protocol written? Name who reviews and who may override.
- Is a weekly audit planned? Outputs drift.
- Is the lawful basis for processing personal data documented, and does the vendor agreement cover AI processing and data location? These are checks for counsel, not a legal opinion.

Rule: if three or more prerequisites are missing, the company is not ready for AI in that area. Start with the foundation.

### Where AI fits in the bowtie

- **Awareness and education.** ICP scoring, intent aggregation, enrichment, chat qualification, email personalization, and lead routing. Typically needs stage 2 or above.
- **Selection and mutual commit.** Conversation intelligence, pipeline scoring, qualification copilots, and AI-assisted forecasting. Typically stage 2 to 3.
- **Onboarding and retention.** Success plans, early health signals, renewal risk, and sentiment analysis. Stage 2 to 3.
- **Expansion.** Upsell scoring, usage signals, and reference mining. Stage 3 or above.

### Core AI principles

1. Fix the process before automating it.
2. A recommendation the team cannot explain will not be trusted.
3. AI assists the decision. A person makes it, especially for forecasts.
4. Review outputs weekly, because they drift.
5. Start where the constraint is, not where the tool is easiest to deploy.

### Vendor and platform changes

AI features are moving into the CRM and the revenue intelligence tools themselves. When evaluating a platform, compare the AI capability across vendors, not only forecast accuracy, and check whether the vendor's native models reduce the custom work you would otherwise build. Check current vendor documentation for any feature, pricing, or deprecation date. These change faster than this library is updated.

### Multi-agent reality

Running many agents together is hard. Integration overhead is usually larger than expected: webhooks, middleware, and custom calls between agents. Start with one or two agents, get them reliable, then add more. Pick one system of record before deploying any agent. Agent-to-agent coordination is the hardest problem, so do not solve it first.

Recommended architecture:
1. The CRM is the hub. All agents read from and write to it.
2. A middleware layer handles triggers and routing.
3. Each agent operates in one defined lane, with one motion.
4. A person reviews decisions that cross lanes. Agents do not override each other.

### Knowledge retrieval for AI

When a rep or an agent needs institutional knowledge (playbooks, call recordings, past deals, documented processes), the answer should come from the company's material, not from a general model's training. The stack needs four parts: ingestion from the sources, chunking and indexing, semantic retrieval, and delivery at the moment of use.

Chunking quality limits retrieval accuracy more than the choice of embedding model. Design the chunking strategy first, then choose tools. In regulated or EU-based operations, the choice between managed and self-hosted options is a compliance decision, and it belongs with counsel and the security team, not with the sales team.

### Composability

Assess the stack against four tests for every vendor or build decision:

1. **Openness.** Open formats and APIs, or lock-in?
2. **Adjacency.** Can it work close to the data, or does it need copies?
3. **Replaceability.** What does it cost to swap this in three years?
4. **Optionality.** Does this choice widen or narrow future options?

The architecture has three ages. In the first, every pair of systems is connected directly, which becomes unmanageable quickly. In the second, a hub such as a CRM or integration platform sits in the middle, which is where most mid-sized companies are. In the third, applications share one data foundation instead of holding their own copies. Moving toward the third reduces integration work, but it needs data maturity first.

Capability audit across five layers:
- **Data core.** Is data unified, or spread across stores with conflicting versions?
- **Semantic layer.** Are metric definitions shared? If marketing and sales disagree on what a qualified lead is, this layer is missing.
- **Context service.** Do downstream systems get customer context from one source, or does each query the data with its own logic?
- **Decisioning.** When several systems act on one signal, is there an owner? If email, advertising, and outreach all fire on the same trigger, there is not.
- **Applications and agents.** Is custom software and automation governed, with an audit trail? Shadow automation is a risk.

Custom software can be a differentiator. Competitors can buy the same products, but internal tools built on the company's method are harder to copy. Treat custom development as an investment with an owner and a maintenance budget, not as a free shortcut.

### Stack audit: the annual review

1. **Inventory.** Every tool, owner, cost, user count, and purpose, including hidden costs: admin time, integration upkeep, and training.
2. **Usage.** Actual active use from the tools' own data.
3. **Capability map.** Each tool against the capability it serves. List overlaps and gaps.
4. **Value.** For each tool, what breaks if it is removed tomorrow? If the answer is nothing, it is a cut candidate.
5. **Integration health.** Check every data sync. Failures are invisible until they cause a visible problem.
6. **Roadmap.** Does the stack support next year's plan? What capability will be needed that does not exist yet? Which tools are being outgrown?

Present the full cost of the current stack, including hidden costs, next to a rationalised version.

## Output

- The capability map: each capability, its owner, and the gaps.
- The capability-value matrix with an action for each tool.
- A stack sized to the company's stage, with an entry threshold for each intelligence capability.
- The evaluation scorecard for any tool under consideration, with the ninety-day implementation question answered.
- The build-or-buy decision and its reasons.
- For AI: the stage assessment, the readiness check, and the first use case.

## Diagnostic questions

1. For each tool, which capability does it own, and what would stop working without it?
2. Which tools are below half of their licensed users each month?
3. How many data syncs failed last quarter, and who was told?
4. Which proposed tool has a process written down that it will support?
5. Which AI prerequisites are missing, and is the team ready for the first use case?

## Quality bar

Every capability has one owner, the CRM is the hub, and no tool was bought before its process existed. The stack matches the stage. AI is deployed where the prerequisites are met. Watch for tools bought to find out what the process should be, more than one owner for the same data, integrations no one monitors, and vendor claims accepted without a ninety-day plan.
