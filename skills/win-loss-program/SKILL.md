---
name: win-loss-program
version: 1.1.0
description: "Use when CRM loss reasons are not trusted, competitive losses go unexplained, or positioning and product decisions rest on rep-reported fields. Sets up a standing win-loss program with three evidence lanes: mining the record of every decided deal, interviewing buyers after the decision (both wins and losses), and periodic customer group sessions. Codes the causes against one driver taxonomy and routes the findings to positioning, enablement, and qualification. Rep-reported reasons are treated as opinion; buyer-reported reasons are treated as evidence."
---

# Win-loss program

## Purpose

Most decided deals are never investigated. The CRM loss field is filled by the rep, soon after the outcome, from a dropdown that makes them choose one cause. Those reasons cluster around price and timing. Buyers, interviewed after the decision, often describe trust, a missing capability, a stronger champion on the other side, or a choice that was largely made before the first call. A standing program is the way to find out which account is right, and to feed that into positioning, enablement, and qualification.

## When to use

- CRM loss reasons are not believed by anyone.
- Competitive losses are being explained by guesswork.
- A positioning, pricing, or product decision needs evidence from decided deals.
- Win rates are falling, and nobody knows why.
- Win stories and marketing claims seem to name different strengths.

Route elsewhere when:

- The deal is still open. Use `deal-blocker-maneuvers` or `deal-qualification-gates`.
- The loss is being revived. Use `closed-lost-revival`.

## Inputs

- Decided deals from the last 6 to 12 months, with outcome, value, segment, and competitor where one was named.
- Call recordings and transcripts, and the email threads for those deals, where they exist.
- Access to the buyers who decided, through the account team or a neutral route.
- A list of the people who will consume the findings: product, marketing, sales leadership, and enablement.
- Any existing loss-reason taxonomy, so that history can be mapped to the new one.

## Procedure

### Step 1: Mine every decided deal

Within about a week of each decision, review the full record of the deal.

- Extract what the buyer said about the problem, the alternatives, money, timing, and internal politics. Use verbatim quotes with dates. Do not paraphrase. A paraphrase is where wishful thinking gets back in.
- Work out when the deal actually died or locked. This is rarely the date the CRM records. Find the call where the energy changed, and what came before it.
- Put the rep's stated loss reason next to what the record shows. The gap between them, by rep and by cause, is coaching material in its own right.
- State the limits. Mining only hears what was said to the company. The real reason often sits in a meeting the company was not part of. Lane 2 covers that.

### Step 2: Interview buyers

Interviews are the deeper lane. Run them on a sample, not on every deal.

- **Sample:** interview every large or strategic decision. Add a rotating sample of the rest, and cover both outcomes. Interview wins as well as losses. A program that studies only losses learns half the causal model, and wins are where real differentiators come out, which may differ from the ones on the slides.
- **Timing:** about 2 to 6 weeks after the decision. This window is practice-based. Sooner is raw. Later is revised by memory.
- **Interviewer:** never the rep who ran the deal. A neutral interviewer gets more honest answers. Buyers soften what they say to the person they just turned down. Use a founder for strategic deals, or a product marketing or RevOps lead, or a third party.
- **Protocol:** 30 minutes. No selling, no defending, no correcting the record.
  - Open with: "Walk me through the decision as it actually happened, starting from when you first felt the problem."
  - Follow the story: who was involved, what nearly changed the outcome, what the winning option did that mattered, and what the company did that annoyed or reassured them.
  - Close with: "What would have had to be true for this to go the other way?"
- **Discipline:** when the buyer says something uncomfortable, write it down and ask them to say more. The program is working when a meaningful share of its findings are uncomfortable.

### Step 3: Run customer group sessions

This is a group format with customers. A moderated session brings together five to eight customers to talk about their experience, while cross-functional colleagues from product, marketing, sales, and support listen. The one-to-one interviews reconstruct single decisions. The group session shows the pattern, live, and customers build on each other's answers in a way interviews cannot.

- **Composition:** five to eight customers per session, chosen on purpose. Include happy accounts, accounts that nearly churned, recent wins, and, if possible, a churned customer or a lost evaluator. A skeptic in the room raises the honesty of everyone else. Keep each session within one segment, so that the group shares enough context to be specific.
- **The listening rule:** the company side asks clarifying questions only. No defending, no roadmap promises, no selling. As soon as someone from the company explains why the customer's experience was actually fine, the session stops producing anything useful.
- **The spine:** what they use it for, why they chose it, where it grates, what nearly made them leave, and what they would tell a peer who asked. Walk the customer journey in order: first contact, buying process, onboarding, daily use, and support. This puts friction at a specific stage.
- **Two-sided harvest:** tag each friction point as product or process. "The integration kept breaking" is a product finding. "We did not understand the pricing until the third call" is a sales-process finding. "Nobody contacted us for four months after go-live" is a post-sale finding. A single session can improve both the product and the sales motion.
- **Cadence:** one or two sessions a year per segment is enough. The limit is customers' time, not the calendar. Run one after any strategic surprise in the other two lanes, to test whether an interview theme holds up beyond a few accounts.
- **Keep it a listening session.** It works because it is not a marketing event. Turning it into one destroys the honesty that makes it useful.

### Step 4: Code causes against one taxonomy

Individual stories are anecdotes. The program's output is the pattern across them.

- Code every decided deal against one stable set of driver categories: product capability, trust and proof, price relative to value, champion strength, competitive move, timing and budget reality, and process failure.
- Allow several drivers per deal, and mark one as primary. A single cause per deal recreates the dropdown problem the program exists to escape.
- Code the group-session findings into the same taxonomy, with their product or process tag. That lets one readout inform both the roadmap and the sales motion.

### Step 5: Run the quarterly readout

Make it cross-functional by design.

- Sales sees the process failures.
- Product sees the capability gaps, ranked by revenue at stake.
- Marketing sees the language buyers actually used.
- Leadership sees the trend lines.

One page of findings. Each finding is anchored to a quote.

### Step 6: Route the outputs

- Loss patterns go to the revival process (`closed-lost-revival`).
- Recurring objections go to enablement and proposal preparation.
- Competitive findings go to battlecards.
- A systematic cause goes into qualification. A cause that recurs five times is not a loss reason. It is a missing qualification gate.

## Output

- The coding of each decided deal, with primary and secondary drivers and the supporting quotes.
- The interview summaries, with the interviewer's role noted and the sample explained.
- The group-session findings, tagged product or process.
- The quarterly readout: one page, anchored to quotes, with trends.
- The routing list: which findings go to which owner, and by when.
- The self-audit (see below).

### Self-audit

Put the CRM loss fields and the interview findings for the same deals side by side. The divergence table shows whether the method is finding what the fields miss. If the divergence is small, look first at the interviewing. Do not conclude that the fields were accurate.

## Quality bar

Every decided deal is mined within a week. Interviews run on the planned sample, without a fresh decision each time. The quarterly readout contains at least one finding that contradicts what the company believes about itself. Decisions about positioning or the roadmap cite interview evidence.

Watch for a burst of post-mortems after a bad quarter, run by the reps who lost the deals, producing reasons everyone already accepted. Also watch for win interviews that are never run, so the company never learns what actually wins.

## Diagnostic questions

1. Take the last twenty losses. How many distinct loss reasons does the CRM show, and would anyone stake money on them?
2. When did a buyer last tell the company, after the decision, why it really lost? Who heard it, and where is it recorded?
3. Which of last quarter's losses were interviewed by someone other than the rep who ran the deal?
4. Name one product, positioning, or process change in the last year that cites decided-deal evidence. If there is none, where do those decisions get their facts?
5. Do the win stories and the marketing claims name the same strengths? If wins have never been interviewed, how would you know?
