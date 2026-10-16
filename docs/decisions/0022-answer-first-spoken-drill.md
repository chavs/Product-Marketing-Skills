# 0022: An answer-first spoken drill with a Format check

- Status: Accepted (not yet run in a fresh session)
- Date: 2026-10-14
- Area: coach
- Decided by: Agreed (user approved the plan)
- Source: Conversation, 2026-10-14

## Context

The same note came from four directions in real interviews: an Abnormal rejection ("land the so-what before the detail"), a Cato interviewer ("concise and precise"), Horizon3 mock scores (marked down on format, not content), and a Runlayer mock (strongest point buried behind a caveat). Earlier in this conversation the user also asked to test conciseness and confidence of delivery.

## Decision

Add `/drill [seconds] [question type]` to the coach. One question at a time. Default 90 seconds, set by the user. The word target is about seconds x 2.2. The user speaks, with voice dictation, and Claude reads the transcript.

A Format check comes first and is scored separately from the five-dimension content rubric:
1. Quote the first sentence. Does it state the answer?
2. Where does the strongest point sit, and is a caveat in front of it?
3. Word count against the target.
4. Hedges and fillers, counted and quoted.

One redraft, rescored. One row per attempt is appended to `drill-log.md`. The same Format check is shown in Practice, Score and Debrief.

## Why

- Past feedback marked format down while content was fine, so the two are scored apart and format goes first.
- The doc named a timed, spoken, answer-first drill as the highest-value addition.

## Alternatives rejected

- Folding answer-first into the existing Structure dimension only. It stays there for organization, but format is shown separately.

## Consequences and follow-ups

- Limit: Claude reads text only. It cannot judge tone, pace or pauses, and the skill says so.
- The mechanics (target words, hedge counting, first-sentence and buried-point detection) were tested on a throwaway transcript. The full mode has not been run end to end.

## Implemented in

- `.claude/skills/pmm-senior-principal-interview-coach/References/answer-first-drill.md` and `SKILL.md`.
- Commit 50bab17 (PR #5).
