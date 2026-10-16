# 0002: The live assistant returns sourced facts, not drafted answers

- Status: Accepted
- Date: 2026-08-30
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-08-30

## Context

It was unclear what the assistant should hand back mid-interview: facts only, or facts plus a ready-to-say line.

## Decision

Return raw facts, each tagged `[Confirmed]`, `[Estimated]` or `[Inferred]` with a short source. No answer-crafting and no coaching wrapper.

## Why

- The candidate turns facts into their own words.
- Mid-interview, speed matters more than polish.
- Scoring and answer help belong to the coach, which works before the interview.

## Alternatives rejected

- Sourced facts plus one ready-to-say sentence. Rejected by the user.

## Consequences and follow-ups

- The user set these exclusions at the same time. The live assistant has no pre-interview brief step, does not use the story bank, does not answer general live questions, and does not handle objections or pushback. Those belong to the coach or are out of scope.
- Operating principles: speed over completeness, state assumptions inline, multi-turn by default, every claim tagged and sourced.

## Implemented in

- `.claude/skills/live-job-interview-assistant/SKILL.md` (Scope, Operating principles).
- Commit b55ee32 (PR #1).
