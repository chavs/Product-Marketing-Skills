# 0009: Phase A asks four questions, once, and only what the brief cannot answer

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User, with the assistant's draft corrected twice
- Source: Conversation, 2026-09-01

## Context

The dry run asked questions piecemeal. The assistant's first draft of the intake also asked the candidate to list personas the brief already named, and the user pushed back.

## Decision

Phase A asks these together, in one message:
1. Is the brief tied to a real company (which one), or fully hypothetical?
2. What is the time constraint, or is it untimed?
3. Is there a competitor list from earlier prep, or should it be derived?
4. Personas, only if the brief does not name them: does the candidate know who they should be, or should Claude derive candidates?

Then confirm all answers back in one synthesized recap before research starts.

## Why

- The principle: ask only what the brief itself cannot answer. Anything a careful read of the prompt surfaces is extracted, never asked.
- Phase B runs uninterrupted, so a misunderstood answer would waste the whole research budget. The recap catches that.
- The competitor question pulls forward a check that already existed inside the competitive method, so it is asked once.

## Alternatives rejected

- A fifth question on business segment and tier. The user said it is evident from the prompt.
- Asking the candidate to list personas already in the brief. The user said to derive them from the brief.

## Consequences and follow-ups

- The same extract-first principle is used in the case-study skill's intake (0021) and in working rule 8.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Phase A).
- Commit e36845a (PR #2).
