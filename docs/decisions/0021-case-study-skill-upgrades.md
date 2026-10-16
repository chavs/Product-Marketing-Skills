# 0021: Close six gaps in the case-study skill

- Status: Accepted
- Date: 2026-10-14
- Area: case-study
- Decided by: Agreed (user approved the plan)
- Source: Conversation, 2026-10-14

## Context

The learnings document ranked a take-home workflow as its top candidate and listed what it should do: decompose the brief and grading criteria, agree the source hierarchy before research, calibrate voice on the right medium, track the length limit, check consistency across sections, and write submission notes on AI use. The case-study skill covered the rest but not these.

## Decision

- Phase A extracts the task sub-asks, grading criteria, medium and length limit with its unit from the brief. It does not ask the candidate to restate them. It proposes a source order, which the candidate confirms in the same recap. It asks only what the brief cannot answer: the target voice if unstated, and whether an AI-use note is required.
- Phase B adds an optional voice-calibration track: 3 to 5 samples from the same medium as the deliverable, measured, with sources. Every track ends with a Coverage block and a Needs upload list.
- Phase D becomes six fixed, critique-only checks: claims against research, grading-criteria coverage, cross-section consistency, a scripted length count, plain-writing flags, and a drafted AI-use note.
- `/case-study check` runs Phase D.

## Why

- Each item came from the doc's checklist, compared with what the skill already did.
- The length count uses a script because counting by eye is unreliable.
- Claude drafts the AI-use note because it is a factual statement about Claude's role in the session. The candidate confirms or edits it.

## Alternatives rejected

- None recorded.

## Consequences and follow-ups

- The skill remains critique-only. It lists locations of plain-writing problems and cut candidates. It does not write replacement text.

## Implemented in

- `.claude/skills/pmm-case-study-assistant/SKILL.md`.
- `.claude/skills/pmm-case-study-assistant/References/voice-calibration.md` and `submission-checks.md`.
- Commit 76b08fc (PR #5).
