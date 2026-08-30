# Live Job Interview Assistant

A Claude skill for use *during* an actual live PMM interview — not for prep beforehand. Everything here assumes the candidate is mid-conversation with an interviewer right now and needs a fast, sourced answer, not a slow research process.

## What it does

- **Competitive intel** — fast, sourced competitive facts, fired off mid-interview when the interviewer raises a named competitor. Every claim is tagged `[Confirmed]` / `[Estimated]` / `[Inferred]` with a short source, even under time pressure.
- **Customer voice** — fast, sourced customer/buyer language or claim verification, fired off mid-interview — for the target company, a competitor, or the problem space generally, independent of any specific competitor.
- **Product-to-value translation test** — live support for a specific case-exercise format: a real (often redacted) roadmap/engineering brief, turned into a business "so what," persona-tuned value props, and a headline, followed by a live defense. Claude retrieves, defines, and critiques; the candidate authors everything — this material gets cross-examined live, so it has to genuinely be theirs.

## Scope

**In scope:** live, real-time assistance during an actual interview — competitive/customer-voice lookups and the translation-test exercise.

**Out of scope:** anything done before the interview (research, mock practice, scoring, debriefs, story bank) — see the `pmm-senior-principal-interview-coach` skill for that. Other live case-exercise formats (GTM launch, enablement, positioning/messaging, slides) aren't built yet.

## Usage

Trigger this skill when the user is currently in an interview and needs a fast fact, or is currently working through the translation-test brief. Natural language works ("they just asked about Competitor X's pricing") or use `/competitive-intel [question]`, `/customer-voice [question]`, and `/translation-test` directly.

## Files

- [`SKILL.md`](./SKILL.md) — full skill definition, operating principles, entry points, commands
- [`References/live-competitive-research.md`](./References/live-competitive-research.md) — live competitive research method
- [`References/customer-voice-research.md`](./References/customer-voice-research.md) — customer-voice source ranking and use cases
- [`References/translation-test-practice.md`](./References/translation-test-practice.md) — the 7-step product-to-value translation test workflow
