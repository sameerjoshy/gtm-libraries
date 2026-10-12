---
name: saas-lifecycle-programs
version: 1.0.0
status: draft-for-review
description: Use to design, audit, or rebuild the messaging a subscription product sends across the customer journey, from activation and onboarding to adoption, retention, expansion, failed-payment recovery, and win-back. Starts by checking whether the events and attributes the messaging needs are tracked and reach the messaging platform, then ranks findings by leverage, or produces a staged build roadmap with the trigger, touches, and data prerequisites for each programme. Not for the customer success motion itself (see cs-operations).
sources:
  - "SaaS lifecycle programs (MIT, Tanyo Gochev): audit the data layer before any campaign, the eight-stage journey map from acquisition to resurrection, a minimum viable set of programmes, the principle that retention is the foundation, and a findings report ranked by leverage"
  - "Removed: the example sequences and the figures attached to the source's examples. The stage map is restated as this library's own list"
  - "Adapted for GTM-360: the minimum viable programme set and the order of build are author defaults. A broken data pipe is raised as the first deliverable, even when the request was for a campaign"
---

# SaaS lifecycle programmes

## Purpose

Lifecycle messaging is only as good as the events behind it. Most lifecycle problems are not missing campaigns. The events are not tracked, they are tracked inconsistently, or they never reach the messaging platform, so the programme quietly sends the wrong message to the wrong people. This skill checks the data first, then designs or audits the programmes against the customer journey.

## When to use

- Trial conversion or activation is low.
- Churn is rising, and the team wants messaging to help.
- Onboarding or failed-payment messages need review or a rebuild.
- A win-back flow is needed.

Route elsewhere when:

- The question is the customer success motion. Use `cs-operations`.
- The question is the product's own onboarding. Use `onboarding-activation`.
- The question is the price or plan design. Use `pricing-monetisation-ops`.

## Inputs

- The list of events and user attributes that exist, and how many records each has.
- The cohort retention curve, by signup month.
- Current lifecycle messages, with their triggers.
- The plans, trial length, and billing system used for failed payments.

## Procedure

1. **Audit the data layer first.** For each message the programme would need, confirm the trigger event exists, is populated, is consistent, and reaches the messaging platform. Name every gap. If the pipes are broken, the first deliverable is fixing them, stated plainly, even when the request was for a campaign.
2. **Read the retention curve before prescribing anything.** A curve that flattens means retained users are a stable base to build on. A curve that keeps falling means the first priority is retention, not acquisition messaging.
3. **Place the user journey on the eight stages:**
   1. Acquisition: signup, setting expectations, first login.
   2. Activation: reaching the first moment of value.
   3. Onboarding: completing the setup steps that predict retention.
   4. Adoption: building the habit and widening feature use.
   5. Retention: reinforcing value and preventing decay.
   6. Expansion: hitting limits, upgrading, adding seats.
   7. Advocacy: referrals and reviews from happy users.
   8. Resurrection: reactivating dormant users, saving cancellations, and recovering failed payments.
4. **Start with the minimum viable set:** activation, onboarding, trial conversion if there is a trial, failed-payment recovery, and win-back. Add expansion and advocacy once these work.
5. **For an audit,** rank findings by leverage: the revenue or retention at stake, against the effort to fix. Show the evidence for each.
6. **For a build,** produce a roadmap in stages. For each programme, give the trigger, the number and timing of touches, the data it depends on, and the check that shows it is working.
7. **Define the success measure** for each programme before it runs, such as activation rate, trial conversion, or recovered payments.

## Output

- The data-layer findings, first, with each gap and its fix.
- The retention reading and what it implies.
- The journey map, with the stage of each programme marked.
- An audit ranked by leverage, or a staged roadmap with triggers, touches, data prerequisites, and success measures.

## Quality bar

The data layer is checked before any programme is designed. Each programme names its trigger and its data source. The retention curve is read before prescriptions. Success is measured before launch. Watch for campaigns built on untracked events, win-back flows with no data behind them, and lifecycle programmes designed for an acquisition problem that is really a retention problem.
