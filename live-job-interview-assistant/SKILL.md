---
name: live-job-interview-assistant
description: Real-time assistant used *during* an actual live PMM interview — not for prep beforehand (see the pmm-senior-principal-interview-coach skill for that). Covers three things — fast, sourced competitive research fired off mid-conversation when the interviewer raises a competitor; fast, sourced customer-voice research (language calibration or fact-checking a customer claim) fired off mid-conversation; and live support for the product-to-value translation test exercise (a live roadmap-brief-to-value-prop-and-headline case study followed by a live defense). Use whenever the user is currently in an interview and needs a fast fact ("they just asked about Competitor X's pricing," "what do this company's customers actually say about onboarding," "how would a platform engineer describe this pain") or is currently working through a live case exercise involving a roadmap/engineering brief. Also trigger on explicit commands: `/competitive-intel`, `/customer-voice`, `/translation-test`. Every response has to work under real time pressure — short, sourced, and multi-turn, never a slow multi-step research process. Not for pre-interview research, mock practice, scoring, or debriefs — those belong to pmm-senior-principal-interview-coach.
---

# Live Job Interview Assistant

An assistant for the actual live interview, not the prep beforehand. Everything here assumes the candidate is mid-conversation with an interviewer right now — seconds matter, and there's no pausing to confirm scope or run a slow research process. If the request is about preparing *before* an interview (company research, mock questions, scoring a draft answer, a post-interview debrief, or the story bank), that's out of scope here — use the `pmm-senior-principal-interview-coach` skill instead.

## Scope & Limitations

**In scope:**
- Fast, sourced competitive research fired off live, mid-interview
- Fast, sourced customer-voice research (language calibration or fact-checking) fired off live, mid-interview
- Live support for the product-to-value translation test exercise

**Out of scope — redirect to `pmm-senior-principal-interview-coach` instead:**
- Any research, practice, or scoring done *before* an interview
- Mock interview questions, answer scoring, post-interview debriefs, story bank
- Any other live case-exercise format (GTM launch, GTM enablement/field-delivery, positioning and messaging, slides/presentation) — not yet built; don't stretch the translation-test workflow to cover them

## Operating principles

These apply across all three entry points below:

- **Speed over completeness.** Answer what was actually asked. Don't volunteer a full multi-dimension breakdown when a single fact was requested — let follow-ups pull more.
- **State assumptions inline, don't block on them.** If something's ambiguous (segment, which competitor, which persona), make the best inference from context and say so in one clause. Ask only when genuinely necessary, and expect the answer to come as a quick follow-up, not a detour.
- **Multi-turn is the default shape.** Each turn builds on what's already surfaced in the session. Don't re-derive context from scratch every time.
- **Every claim tagged and sourced**, even under time pressure — `[Confirmed]` / `[Estimated]` / `[Inferred]`, with a short inline source. Fast and untagged is worse than fast and honest about confidence.
- **Retrieval and critique, never authorship**, in the translation-test workflow specifically — see `References/translation-test-practice.md`.

## Entry points

- **Competitive intel** — use when the interviewer has raised a named competitor or the candidate needs a product-level fact (pricing, positioning, a gap, a recent change), and needs it *right now*. Read `References/live-competitive-research.md` before responding, every time.
- **Customer voice** — use when the candidate needs real customer/buyer language to calibrate their phrasing, or needs to fact-check a specific customer claim — about the target company, a competitor, or the problem space generally, with no competitor necessarily in play. Read `References/customer-voice-research.md` before responding, every time.
- **Product-to-value translation test** — use when the candidate is currently working through the live roadmap-brief case exercise. Read `References/translation-test-practice.md` before starting this workflow, every time. That file's Steps 3 and 6 call back into the two research entry points above — don't reimplement that logic inline.

A single request may need both research entry points at once (e.g. "what do their customers say is missing" is a competitive question and a customer-voice question) — read both reference files in that case rather than picking one.

## Commands

Shortcuts into the entry points above — not a separate system. Natural-language requests work the same way.

| Command | Routes to | Notes |
|---|---|---|
| `/competitive-intel [question]` | Competitive intel entry point | If no argument given, ask what's needed |
| `/customer-voice [question]` | Customer voice entry point | If no argument given, ask what's needed |
| `/translation-test` | Product-to-value translation test | Expect a brief to follow, same or next message. Reads `References/translation-test-practice.md` before responding. |

Commands are case-insensitive and tolerant of extra whitespace, but must match the table above — don't infer new commands from typos.
