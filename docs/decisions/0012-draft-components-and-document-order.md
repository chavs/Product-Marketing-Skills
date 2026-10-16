# 0012: The draft has four parts and goes at the top of the document

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-09-01

## Context

The user wanted the candidate's own answer to be the first thing visible when defending live. They also wanted the list of areas to be careful about written by the candidate, not elicited by a question from Claude later.

## Decision

The candidate's draft has four parts:
1. The so-what.
2. The persona value propositions.
3. The headline.
4. The candidate's own list of areas not to overstep and areas that need go-to-market validation.

The draft is written into the same file as the research, at the top, above the research. If it is unclear which section or persona a sentence belongs to, Claude asks before filing or critiquing it. It never guesses.

## Why

- When defending live, the candidate needs their own answer first and the research as backup.
- The boundaries list is the candidate's judgment, so it is authorship (see 0003). Phase D then only checks it against the research.

## Alternatives rejected

- Eliciting the boundaries list with a question in Phase D. It was moved into the draft at the user's request.
- Keeping the draft in chat only.

## Consequences and follow-ups

- Phase D can be uniformly evaluative. No step asks the candidate to produce content.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Phase C).
- Commit e36845a (PR #2).
