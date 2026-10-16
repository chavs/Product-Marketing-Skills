# 0003: Authorship stays with the candidate

- Status: Accepted
- Date: 2026-08-30
- Area: skills-architecture
- Decided by: User (from the exercise spec they supplied), extended to take-homes on 2026-09-14
- Source: Conversation, 2026-08-30. The take-home extension is recorded from the case-study skill and memory notes.

## Context

The user's spec for the product-to-value exercise says it rewards demonstrated understanding and the ability to defend choices live, not polished output. The candidate is cross-examined on the material.

## Decision

Claude retrieves, defines, sources and critiques. Claude never writes the so-what, the value propositions, the headline, the roadmap recommendation, the content review, or the candidate's own list of boundaries. Claude flags problems and asks questions. It rewrites only if the candidate asks.

## Why

- The material has to be genuinely the candidate's, because they defend it live or after submitting.
- A take-home is submitted under the candidate's name.

## Alternatives rejected

- None recorded.

## Consequences and follow-ups

- Phase D critique is evaluation only.
- The same rule became working rule 1 ("critique and ask questions instead of rewriting") in 0019.
- The one factual exception: Claude may draft the AI-use note for a submission, from what happened in the session, for the candidate to confirm (see 0021).

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Core principle).
- `.claude/skills/pmm-case-study-assistant/SKILL.md` (Core principle).
- `interview-working-rules.md` (rule 1).
