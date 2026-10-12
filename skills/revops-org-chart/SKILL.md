---
name: revops-org-chart
version: 1.0.0
description: "Use to design or change the structure of a RevOps team: which roles to hire first and in what order by ARR stage, when to bring in a systems architect and in what mode, centralised versus embedded versus hub-and-spoke, where RevOps should report, what its charter must say, how to move a business automation or CRM team into RevOps, and how to structure a multi-business-unit company. Not for the GTM org redesign across functions (see gtm-planning-org-design)."
---

# RevOps org chart and team design

## Purpose

Where RevOps sits and who is in it determines what it can actually do. A team reporting to one executive with no charter becomes a ticket queue with a better title. A team with authority over definitions and data, and enough people to hold them, becomes the steward of how revenue runs.

This skill helps decide the structure, the order of hiring, and the mandate. Frame every recommendation around outcomes and role identity: what the leader gains (forecast trust, steerability, fewer fire drills), what the RevOps person becomes (system owner, not spreadsheet operator), and what changes in their week.

The core rule: the team's authority must match its responsibility. If RevOps owns the data model but cannot say no to a senior request that breaks it, the structure is wrong, whatever the chart says.

## When to use

- A company is hiring its first RevOps person, or the second or third.
- The CRM or automation team needs to become a RevOps function.
- Leadership is debating whether RevOps reports to sales, finance, or the executive team.
- A systems architect is being considered, and the mode (advisory, fractional, or full-time) is unclear.
- A multi-business-unit company needs a structure that gives comparable numbers without merging systems.

Route elsewhere when:

- The question is the GTM structure across sales, marketing, and customer success. Use `gtm-planning-org-design`.
- The question is compensation for the roles. Use `gtm-compensation`.
- The question is the change programme for moving the team. Use `revops-change-management`.

## Inputs

- Company ARR and GTM headcount by function.
- Number of business units, segments, and CRM instances.
- Current reporting lines for every operations person.
- The list of systems and integrations the team maintains.
- The decisions that currently go unmade or are contested, such as definitions, field changes, and tool purchases.
- Current pain: forecast trust, data quality, tool sprawl, or speed of change.

## Procedure

### Step 1: Size the team to the stage

As a planning frame, not a quota:

| ARR stage | Team size | First hire | Next additions |
|---|---|---|---|
| Under about $5M, pre-scale | 0 to 1 | Generalist consultant or fractional help | None |
| About $5M to $15M, early | 1 | RevOps manager (generalist) | CRM administrator |
| About $15M to $30M, growth | 2 to 3 | Analyst | Second manager or senior operator |
| About $30M to $75M, scale | 4 to 6 | Operations leads for each function | Business intelligence manager |
| About $75M to $150M, mature | 7 to 10 | Full-time systems architect | Marketing ops and customer success ops leads |
| Above $150M, enterprise | 10 or more | Hub-and-spoke structure | VP of RevOps, full functional split |

Use these bands to decide the next hire, then check against the team's actual workload. Two people can be overloaded at $10M, and six can be underused at $60M.

The architect is not a late-stage hire by default. An advisory or fractional architect can add value much earlier, especially during a platform launch or a change to the revenue architecture.

### Step 2: Define the four archetypes

These roles are different, and they should not be confused in job descriptions or hiring decisions.

1. **Generalist manager.** The first hire and the connective tissue between strategy and execution. Owns the cadence, the priorities, and the link to leadership. Does not make routine field changes in the CRM. A reasonable ratio is one generalist for about five specialists.
2. **Business partner.** The operations lead aligned to one GTM function: sales, marketing, or customer success. Owns that function's workflows, reports, and process design. Not the first hire.
3. **Systems architect.** Designs the revenue technology for scale: data model, integration architecture, CRM design, automation framework, and tool selection. Explicitly not an administrator. Needs enough coding or data architecture to judge a design, and enough communication skill to explain it to executives.
4. **Analyst.** Data, reporting, and analysis. A subject expert in the numbers. Scales in clusters once a generalist is in place. Not the first hire.

### Step 3: Choose the architect's mode

| Mode | When | What the architect does |
|---|---|---|
| Advisory | Any stage, especially at a platform launch or a structural decision | Reviews decisions, catches structural mistakes before they compound |
| Fractional | The team is junior, or complexity is high but full-time is not yet justified | Owns named deliverables, handles escalations, transfers knowledge on purpose |
| Full-time | Three to six or more RevOps people, ten or more tools with active integrations, and architecture decisions are a weekly bottleneck | Embedded, owns the whole systems layer |

Engage at least in advisory mode when any of these holds: a new CRM or revenue architecture is being launched, three or more systems have two-way data flows, the internal team configures well but does not design for scale, several business units' changes break each other's processes, or a platform change alters the cost model or the automation path.

The architect owns end-to-end architecture, not day-to-day administration. Their work: integration design, the data model and single source of truth, translation of business process into technology (process drives technology, never the reverse), workflow automation, and architecture documentation.

Platform changes are frequent and their pricing and deprecation dates move. Check current vendor documentation before designing around any feature. A rule that holds across platforms: new automation should be built on the platform's current supported path, and old automation should have a dated migration plan.

### Step 4: Separate the architect from the admin

An administrator configures the platform within an existing framework. An architect designs the system for growth. An administrator who becomes an architect needs a mandate, new skill investment, and separation from ticket work. The change rarely happens without outside support.

Screen candidates on these signals:

| Signal | Architect | Administrator |
|---|---|---|
| Starting point | Asks how to structure it for growth before choosing a tool | Asks which field to add |
| Systems thinking | Can trace how a change in one area breaks another | Strong in one tool, fixes the immediate problem |
| Technical base | Can write scripts and reason about data pipelines | Strong platform certification and builder skill |
| Communication | Explains architecture to executives who do not know the platform | Speaks the platform fluently, struggles to generalise |
| Scale question | "How do we ingest from five sources consistently?" | "How do we report on this metric?" |
| After failure | Analyses why the approach failed and changes the design | Fixes the error and ships |

Interview prompts for an architect: describe an integration across three or more systems you designed, and where it broke. Describe a time you said no to a request because it would break the data model. Show a script you wrote to move or check data. Explain your current CRM to someone who has never seen it.

### Step 5: Add AI governance roles when the automation demands them

Once the company runs AI-driven steps in its revenue process, three accountabilities usually appear. Assign them before they become a problem, not after an incident.

1. **Agent designer.** Owns the prompts and rules for customer-facing automated steps such as scoring, routing, and forecast adjustment: when they change, and how they fail. Tactical RevOps work, not data science. Often fractional at first, and sits with the architect.
2. **Oversight lead.** Owns data readiness for agents, monitoring of their performance, impact tracking, and compliance with data protection and AI rules. Bridges RevOps and legal or compliance. Becomes necessary when several agents run in production, or when enrichment and automated contact raise compliance questions.
3. **Process owner.** Decides which processes qualify for automation, runs the pilots, and manages the change when automation replaces manual work. Usually a business partner or analyst with added responsibility. Needs process discipline, not coding.

Hiring sequence as a default: a fractional agent designer within the architect role first; a dedicated oversight person, often promoted from analyst, when automation is substantial; a formal governance lead reporting to the head of RevOps when many agents run. The architect owns orchestration. The oversight lead owns monitoring and compliance.

When the number of production agents passes about ten, orchestration needs to be designed deliberately: which agent owns which decision, what data each agent may rely on, and where conflicts surface for a person to resolve.

### Step 6: Choose the structure

Three models. Each is right in some context.

**Departmental.** Sales ops, marketing ops, and customer success ops as separate teams under a head of RevOps. Suits a company around $15M to $50M. Risk: re-siloing.

**Centralised (centre of excellence).** One RevOps team serving every GTM function. Owns definitions, data, and systems. Business partners may exist as relationship managers but report into RevOps. Suits a single-motion company with a strong RevOps leader, up to about $100M with one product line. Risk: other functions feel under-served, and RevOps becomes a queue.

**Embedded.** Ops people sit in and report to their functions. Faster and closer to the work. Suits fast-moving organisations where context matters more than consistency. Risk: re-siloing within a year, data model drift, and no one able to say no across functions.

**Hub-and-spoke.** A central hub owns data model, governance, architecture, shared definitions, and cadence standards. Embedded spokes own execution within those standards. Recommended from roughly $50M or in multi-business-unit companies.

The reporting line for spokes matters. A dotted line to the function head keeps the spoke credible with RevOps and close to the work. A direct report to the function gives speed and risks drift.

The test for any model: can the central team make a binding decision that affects sales without the sales leader's approval? If yes, a centralised model works. If no, embedded spokes need enough central governance to hold the shared layer together.

### Step 7: Choose the reporting line

Where RevOps sits determines what it can do, and no option is neutral.

- **Reporting to the CRO.** Fast alignment with sales, and natural authority over pipeline and forecast. Marketing and customer success can feel under-served, and sales data becomes hard to challenge.
- **Reporting to the CEO or COO.** Real neutrality across functions, and authority over definitions without political cost. Can feel distant from the commercial engine, and getting traction on sales priorities takes effort.
- **Reporting to the CFO.** Credibility with finance, and strong metric discipline. Risk of over-weighting reporting against execution, with customer success and marketing de-prioritised.
- **Reporting to the VP of sales.** Maximum sales alignment in the early stage, and it becomes sales operations rather than RevOps. Marketing and customer success lose trust quickly.

Default for a scale-up of about $15M to $75M: report to the CRO or the CEO or COO. The CFO works where there is no CRO and the company runs forecast-first. The VP of sales arrangement works only as a short transition, and it tells marketing and customer success the function is not theirs.

The political test: can RevOps say no to a request from the VP of sales that would break a shared process? If not, the reporting line does not matter, because the authority is not real.

### Step 8: Write the charter

RevOps without a mandate is a ticketing function. The charter sets four things in writing:

1. **Decision rights.** What RevOps owns outright: definitions, the data model, stage names, metric definitions, and the cadence structure. What needs RevOps sign-off: tool purchases, new fields, workflow changes. What RevOps advises on without blocking.
2. **Change control.** No definition, field, or process changes without an owner, an effective date, and a logged reason. RevOps is a gatekeeper with a published process and a turnaround time, not a bottleneck. The difference is that a gatekeeper has an SLA.
3. **Backlog authority.** A visible, prioritised backlog of system changes. Stakeholders request, RevOps triages and sequences. Requests outside the roadmap are declined with a reason, not left to fade.
4. **Governance sponsorship.** Signed by the executive RevOps reports to. Without that cover, the mandate is theoretical.

For a business automation team moving to RevOps, the charter is the most important document. The technical capabilities often exist already. The mandate does not. The constraint is usually governance, not technology.

Charter sections to include beyond the four: the scope of systems owned, the escalation path when a function disagrees, the review cadence for the charter itself, and the metrics RevOps is judged on.

### Step 9: Move from automation or CRM admin to RevOps

A business automation team is the natural predecessor to RevOps. The transition needs four changes:

1. **Mandate.** From "configure what is asked" to "steward how revenue runs on the platform."
2. **Charter.** Explicit authority over definitions, the right to decline requests, and change control.
3. **Role growth.** Admins can grow into analyst or architect roles. Leads can grow into business partner roles.
4. **Gap.** Process authority and partnership skills. The technical base is usually already there.

The organisational evolution has four stages. Siloed: operations people report to department heads and lose priority to quota work. Departmental: all operations under one manager, organised by the function served, with no authority to say no. Functional: reorganised by capability, with a systems team (architects and administrators) and an insights team (analysts). The manager of the systems team should be an architect, and this is the critical transition. Evolved: enablement joins RevOps, with cross-functional product-style ownership and regular sessions where operations staff sit with end users.

### Step 10: Structure multiple business units

When one company runs several business units with separate CRM instances and different maturity, a standard chart breaks. The core tension: units need room to run their own motion, and the company needs comparable numbers to allocate investment.

Design principles:

1. **One shared dictionary, local implementations.** Stage names, metric definitions, and data model standards are set centrally. Each unit defines its own triggers, bands, and local workflows within that schema. Do not merge instances. Share the dictionary.
2. **One architect across all units**, fractional or full-time. The architect owns the interface between instances: how data reaches cross-unit reporting without a merge. This role should not be split by unit.
3. **One business partner per unit.** Each works within the shared schema and owns the local implementation. A monthly sync across business partners is the minimum governance.
4. **Maturity-adjusted expectations.** Scan each unit's maturity and plot them on one model. Show leadership the spread. A uniform target holds back the most mature unit and overwhelms the least mature.
5. **Governance before automation.** A central warehouse on top of inconsistent definitions combines four languages into one table. Fix the dictionary first, then centralise reporting.

Example structure for a company of about $250M ARR with four units: a head of RevOps and business automation over a fractional or full-time architect, one business partner for each unit covering its motion (direct sales, mid-market, channel, and services), and a shared analyst team for cross-unit reporting.

## Output

- The stage-appropriate team size and the next hire, with the reason.
- The archetype for each role, and the architect's mode with its trigger.
- The structure model and the reporting-line decision, with the political test applied.
- The charter, with the four required sections and any additions.
- The transition plan for an existing team, if one applies.
- The multi-unit design, if relevant.

## Diagnostic questions

1. Who owns the definition of a qualified opportunity, and can they say no to a sales leader?
2. Which operations people report to a function rather than to RevOps, and what conflicts does that create?
3. Is the architect a designer or an administrator in practice, and does their week show it?
4. What is the last request RevOps declined, and was it declined with a reason?
5. Which decisions go unmade for more than a month because no one has the authority to make them?

## Quality bar

The team's authority matches its responsibility, written in a charter with an executive sponsor. The architect is hired or engaged at the mode the complexity needs. The reporting line gives the team authority across functions, not only within one. Watch for RevOps reporting to one function, no written decision rights, an architect doing ticket work, and a multi-unit company that tries to merge systems before agreeing on definitions.
