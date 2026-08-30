# Product-to-Value Translation Test — Live Assistant Workflow

Support for one specific live interview exercise: the candidate is given a real (typically lightly redacted) engineering/roadmap brief with no prior marketing work done on it, and must produce a one-paragraph business "so what," persona-tuned value propositions, and a headline — then defend those choices live to the interviewer.

This is one of several distinct exercise/case-study types a PMM interview loop may include (others: a GTM launch exercise, a GTM enablement/field-delivery exercise, a positioning and messaging exercise, a slides/presentation exercise). This file covers only the translation test. Don't generalize this workflow to the others, and don't fold their logic in here — each gets its own reference file when built.

**No hardcoded time limit anywhere in this workflow.** The time allotted varies by interview loop — one company gives 20 minutes, another 30, another doesn't time it at all. If it's relevant to ask, ask the candidate what their actual constraint is; refer to it generically as "the live time constraint," never as a specific number.

## Core principle: authorship stays with the candidate

This exercise rewards demonstrated understanding and the ability to defend choices live — not polished output. Throughout this workflow, Claude's role is retrieval, definition, and critique; the candidate's role is interpretation, judgment, and authorship. **Never write the so-what, the value props, or the headline for the candidate.** Push, question, supply raw material — but the candidate produces the actual content. This matters more here than usual: the candidate is about to be cross-examined live on this material, and it needs to genuinely be theirs.

## The workflow

### Step 1 — Mechanics: what the feature does, and where it fits

The candidate reads the brief. Don't interpret or summarize what the feature does for them — that translation is their own work to do. Instead:
- Research where this fits in the company's current documentation and existing product surface — is this an existing capability being extended? A genuinely new primitive? Part of a known product line/tier?
- Define any technical/domain-specific term the candidate flags, so they aren't burning their own reasoning time on unfamiliar jargon.

The candidate does the actual "this means X for the business" translation.

### Step 2 — Prior state: how personas solved this before

The candidate states the problem space in their own words first — their read of the brief, not a summary from Claude. Only after that, research: for each relevant persona, how has that persona historically solved this problem, in terms of both tools/products *and* manual processes/workarounds.

### Step 3 — Competitive alternatives (live)

Building off what Step 2 surfaces, identify the named competitive products/vendors that map to the prior solutions found. **Use `References/live-competitive-research.md` for this — don't reimplement tier-routing or source-ranking logic here.** This runs live, in real time, as part of working through the exercise, the same way it would for any other live competitive question — there's no separate pre-built research corpus this depends on.

### Step 4 — Roadmap-to-gap mapping

Identify where the roadmap/feature closes the persona's gap fully vs. only partially. Surface partial-fit findings clearly rather than smoothing them into a clean win — honesty about partial gaps is a strength signal in the real interview, since it shows the candidate won't oversell.

### Step 5 — Persona journeys

For each persona in the brief (e.g. developer, platform engineer, enterprise buyer), identify where in that persona's day/workflow this problem actually bites them, so the resulting value prop lands in that persona's own language and priorities rather than as a repackaged feature list.

### Step 6 — Customer voice: language calibration (live)

Research the actual words real customers/buyers use to describe this problem, so the candidate's value props sound like they've talked to a real customer rather than written generic marketing copy. **Use `References/customer-voice-research.md` for this — don't redefine source priority here.** Runs live, same as Step 3.

### Step 7 — Critique loop

Once the candidate has drafted a so-what, value props, and headline, shift to editor: push back hard, force multiple versions, argue the edges rather than approve the first draft.

- **Headline-specific critique pass** — a headline is its own skill, distinct from a value prop with the period removed: punchy and defensible. Have the candidate produce several; call out which are genuinely headlines vs. restated value props.
- **Order-of-persona reasoning** — press the candidate on which persona they'd lead with and why. The live interviewer is likely to ask this directly; it shouldn't default to whichever persona was easiest to write for.
- **"Why I cut this" rehearsal** — for every angle or value prop the candidate drops, they should be able to say why, out loud. The live conversation half of this exercise is as much about defending discards as picks.

## Explicitly out of scope for this workflow

- Other exercise/case-study types (GTM launch, GTM enablement/field-delivery, positioning and messaging, slides/presentation) — each gets its own separate reference file when built. Don't infer or extend this workflow to cover them.
- General practice disciplines like ambiguity-handling or timed-practice drilling — these are reusable capabilities that would apply across multiple exercise types, not specific to this one, and aren't built into this workflow.
- Competitive intelligence and customer-voice research methodology — live entirely in their own reference files; this workflow only calls out to them.
