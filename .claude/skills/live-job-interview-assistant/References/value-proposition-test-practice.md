# Value Proposition Test — Live Assistant Workflow

Support for one specific live interview exercise: the candidate is given a real (typically lightly redacted) engineering/roadmap brief with no prior marketing work done on it, and must produce a one-paragraph business "so what," persona-tuned value propositions, and a headline — then defend those choices live to the interviewer.

This is one of several distinct exercise/case-study types a PMM interview loop may include (others: a GTM launch exercise, a GTM enablement/field-delivery exercise, a positioning and messaging exercise, a slides/presentation exercise). This file covers only the value proposition test. Don't generalize this workflow to the others, and don't fold their logic in here — each gets its own reference file when built.

**No hardcoded time limit anywhere in this workflow.** The time allotted varies by interview loop — one company gives 20 minutes, another 30, another doesn't time it at all. Ask the candidate what their actual constraint is in Phase A below; refer to it generically as "the live time constraint," never as a specific number. **Time allocation**: Phase B (the autonomous research batch) gets exactly half of whatever constraint the candidate states. The other half is for Phase C (drafting, unassisted) and Phase D (the critique loop). This is a firm allocation, not an aspirational target — Phase B stops and hands off once its half is used, rather than continuing to research past budget.

## Core principle: authorship stays with the candidate

This exercise rewards demonstrated understanding and the ability to defend choices live — not polished output. Throughout this workflow, Claude's role is retrieval, definition, and critique; the candidate's role is interpretation, judgment, and authorship. **Never write the so-what, the value props, the headline, or the candidate's own go-to-market boundaries for them.** Push, question, supply raw material — but the candidate produces the actual content. This matters more here than usual: the candidate is about to be cross-examined live on this material, and it needs to genuinely be theirs.

## Phase A — Intake (ask once, as a batch, before anything else)

Ask these four questions together, in one message — not sequentially, not spread across the workflow. Only ask about things the brief itself cannot answer; never ask something a careful read of the prompt would already surface (segment, tier, technical domain, named personas already in the brief, etc.) — extract those directly instead.

1. **Real or hypothetical, and which company** — "Is this brief tied to a real company's product line (which one), or fully hypothetical?" If real, this determines where Step 1's adjacent-capability research points.
2. **Live time constraint** — "What's your time limit for this exercise (or untimed)?" Drives the Phase B time allocation above.
3. **Competitors — known or derive** — "Do you already have a competitor list from prior prep, or should this be derived from the problems/personas as we go?" If known, Step 3 uses it directly and skips `live-competitive-research.md`'s own "check if known" prompt — that check has already happened here.
4. **Personas — fallback only** — if the brief already names target personas, extract them by reading; don't ask. Only ask this question if the brief is silent or vague on personas: "Do you already know who they should be, or should I derive candidates from the brief content?" Never ask the candidate to restate personas that are already on the page.

**Before moving on, confirm all four answers back in one synthesized recap** — not a re-ask, a restatement: "Here's what I've got: [company/hypothetical], [time budget], [competitor status], [persona status] — correct before I start researching?" Phase B runs uninterrupted once it starts, so a misunderstood answer here would otherwise silently waste the whole research budget.

## Step 1 — Mechanics: what the feature does, and where it fits

The candidate reads the brief. Don't interpret or summarize what the feature does for them — that translation is their own work to do. Instead:
- If Phase A established a real company, research the closest **existing, real, adjacent capability** the company actually ships today — even if the brief's exact capability doesn't exist. This becomes the anchor category for Phase B's Step 3 and Step 6 research, instead of searching against a fictional capability directly.
- Define any technical/domain-specific term the candidate flags, so they aren't burning their own reasoning time on unfamiliar jargon.

The candidate does the actual "this means X for the business" translation.

## Phase B — Autonomous research batch (Steps 2–6)

Runs in one uninterrupted pass once Phase A and Step 1 are done — no further back-and-forth with the candidate until this phase is complete. **Write the findings to a single document, not inline chat** — this phase produces enough material to crowd out a live chat UI during a time-pressured exercise. Stop at the time-allocation budget stated above and hand off to Phase C, even if research feels incomplete — note any gaps honestly in the document rather than continuing past budget.

### Step 2 — Prior state: how personas solved this before

The candidate states the problem space in their own words first — their read of the brief, not a summary from Claude. Only after that, research: for each relevant persona (from Phase A/the brief), how has that persona historically solved this problem, in terms of both tools/products *and* manual processes/workarounds.

### Step 3 — Competitive alternatives

Runs automatically off Step 2's output — no dependency on the candidate's so-what or any further input. Identify the named competitive products/vendors that map to the prior solutions Step 2 found. **Use `References/live-competitive-research.md` for this — don't reimplement tier-routing or source-ranking logic here.** If Phase A's competitor question already got an answer, use that list directly and skip `live-competitive-research.md`'s own "check if known" step — that's already been asked.

### Step 4 — Roadmap-to-gap mapping

Identify where the roadmap/feature closes the persona's gap fully vs. only partially. Surface partial-fit findings clearly rather than smoothing them into a clean win — honesty about partial gaps is a strength signal in the real interview, since it shows the candidate won't oversell.

### Step 5 — Persona journeys

For each persona (from Phase A/the brief, e.g. developer, platform engineer, enterprise buyer), identify where in that persona's day/workflow this problem actually bites them, so the resulting value prop lands in that persona's own language and priorities rather than as a repackaged feature list.

### Step 6 — Customer voice: language calibration

Research the actual words real customers/buyers use to describe this problem, so the candidate's value props sound like they've talked to a real customer rather than written generic marketing copy. **Use `References/customer-voice-research.md` for the source-trust ranking — don't redefine source priority here.** On top of that ranking, apply this process, specific to the speed and reliability needs of this workflow:

- **Two-part check on every candidate claim, before it goes in the document:**
  - **Attribution determines the tag, not whether the claim is usable.** A direct, named-person quote → `[Confirmed]`. A case study naming a *specific real customer and specific real product* in the adjacent problem space — even if narrated in vendor voice rather than a direct quote — is still usable; it doesn't matter whether it's told in the customer's words or the vendor's, as long as it's anchored to a specific, named instance → tag `[Estimated]` and use it. A *fully anonymized* claim with no named customer at all is the weak case: usable only as a last resort if nothing better turns up within the search-attempt budget below, and flagged explicitly as anonymized when reported.
  - **Relevance** — does the claim actually address the specific pain point being researched, or is it generic product praise? A claim can pass attribution and still fail relevance — check both, independently.
- **Search order**: (1) practitioner / vendor-agnostic content first — the fastest path to specific, verifiable, first-person language; (2) a case study naming a specific real customer and product in the adjacent space, as the next-best fallback, regardless of vendor vs. customer voice; (3) avoid or deprioritize generic vendor blog narrative that doesn't name a specific customer at all. This governs search order only — the source-trust ranking in `References/customer-voice-research.md` still governs which source wins if two claims conflict.
- **Hard cap: 2–3 search passes total.** If nothing clears both checks within that budget, state the gap honestly in the document (what was searched, why nothing qualified) rather than stretching a weak match to fill the slot.
- **Sourcing discipline**: every claim carries its source link inline, every time, no exceptions.

## Phase C — Your draft (unassisted authorship)

Draft four components, informed by the Phase B document:
1. The one-paragraph business "so what"
2. Persona-tuned value propositions
3. A headline
4. **Your own list of areas to be careful not to overstep, and areas that would require further go-to-market validation before you'd state them confidently to a real customer.** This is your own proactive judgment call, produced here — not something Claude asks you for later.

Claude does not write any of this. Write all four components into the same document Phase B produced, **at the top** — above the research, not after it. When defending this live, the candidate needs their own answer first and the research as backup reference after, not research notes to scroll past before reaching what they're actually going to say.

If it's unclear which section or persona a sentence in the draft maps to, ask before filing or critiquing it — never guess at the structural mapping.

## Phase D — Critique loop

Once the draft is in the document, shift to editor: push back hard, force multiple versions, argue the edges rather than approve the first draft. Run this fixed sequence, in this order, every time:

1. **So-what critique** — leads with business impact or mechanism? Specific to this company's actual feature, or generic enough to describe any competitor's feature too? Explicit side-by-side comparison against the Step 2–4 research — a direct claim-by-claim check, not a vague "does it feel right" read.
2. **Persona-coverage critique** — does every persona from Step 5 get a value prop, or did one get silently dropped without an explicit reason? Are two value props actually the same argument restated under different job titles? Explicit side-by-side comparison against Step 6's customer-voice findings — is there enough of the actual customer voice coming through in the specific words used, not just a roughly-right register.
3. **Gap-honesty check** — two distinct failure modes, both checked: (a) has the draft overstated benefits beyond what the brief itself actually claims (inventing a capability the brief never promised); (b) does the draft contradict or ignore an area where the brief explicitly states the feature does *not* have a capability.
4. **GTM-scope check** — check the candidate's self-authored "areas to be careful about" list (from Phase C) against the Step 2–4 research: did they miss a real gap the research actually found? Did they flag something as risky that the research shows is actually fine? Point out mistakes or discrepancies — this is evaluative, checking authored material against research, not asking the candidate to produce the list here.
5. **Headline critique** — a headline is its own skill, distinct from a value prop with the period removed: punchy and defensible. Have the candidate produce several; call out which are genuinely headlines vs. restated value props. Test against "would this describe a generic competitor's feature too" — if yes, it isn't differentiated enough. Also check tone: does it evoke clear emotion and a sense of opportunity/change for the specific primary persona it's aimed at (e.g. relief from firefighting for an engineer vs. confidence/risk-reduction for a buyer) — not just factually accurate, but felt.
6. **Order-of-persona pressure test** — press the candidate on which persona/value-prop they'd lead with, and whether that's consistent with everything else established (their own targeting/segmentation logic, their own customer-voice findings) — not just whichever was easiest to write. The live interviewer is likely to ask this directly.
7. **"Why I cut this" rehearsal** — last, deliberately, since it's not possible to rehearse defending a cut until the rest of the sequence has surfaced what actually got cut or reshaped. For every angle or value prop the candidate drops, they should be able to say why, out loud.

Content-correctness comes first (1–4), craft second (5), live-defense-readiness last (6–7) — critiquing a headline's craft isn't productive before the underlying claims and scope are confirmed sound, and defending cuts can't be rehearsed before the rest of the pass has surfaced what was cut.

## Explicitly out of scope for this workflow

- Other exercise/case-study types (GTM launch, GTM enablement/field-delivery, positioning and messaging, slides/presentation) — each gets its own separate reference file when built. Don't infer or extend this workflow to cover them.
- General practice disciplines like ambiguity-handling or timed-practice drilling — these are reusable capabilities that would apply across multiple exercise types, not specific to this one, and aren't built into this workflow.
- Competitive intelligence and customer-voice research methodology — live entirely in their own reference files; this workflow only calls out to them.
