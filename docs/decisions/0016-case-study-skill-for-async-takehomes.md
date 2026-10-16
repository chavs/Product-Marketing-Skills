# 0016: A third skill for asynchronous take-home case studies

- Status: Accepted
- Date: 2026-09-14
- Area: skills-architecture
- Decided by: Recorded from memory and commits (made in another session)
- Source: Memory notes `project-pmm-skills-architecture` and `project-datadome-pmm-case-study`; commit 87532ce

## Context

The user had a real take-home case study for a Product Marketing Manager role: a written brief with several tasks and a deadline days away, with no interviewer watching.

## Decision

Create `pmm-case-study-assistant`. It runs a batched intake, then unattended, parallel background research with one track per task in the brief plus a track for the company's positioning baseline. The candidate drafts unassisted. A critique loop is optional. There is no time-boxing. If a newer version of the brief arrives, treat it as authoritative and diff it. Do not merge versions.

## Why

- A take-home is a different temporal context from both existing skills. The coach is reflective. The live assistant is real-time and time-boxed. A take-home is deadline-bound but untimed, so research can run overnight.
- A stale brief caused wrong downstream research in this case, so the newest version must replace the old one.

## Alternatives rejected

- Folding take-homes into the coach or the live assistant. The coach has no written brief to work from. The live assistant is built for seconds per turn.

## Consequences and follow-ups

- Competitive and customer-voice methods stay in the live assistant. The case-study skill's competitive reference reuses that ranking and does not redefine it.
- Generated research originally stayed in gitignored files in the working directory. That changed on 2026-10-14 (0020).

## Implemented in

- `.claude/skills/pmm-case-study-assistant/`.
- Commits 87532ce and eb442e2 (PR #4).
