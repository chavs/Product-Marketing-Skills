# 0023: Add prep, handoff, crash course and analyst scan to the coach

- Status: Accepted (the modes have not been run end to end)
- Date: 2026-10-14
- Area: coach
- Decided by: User (selected from options)
- Source: Conversation, 2026-10-14

## Context

The learnings document showed the same loop in nearly every chat, with only half of it covered by a skill. Among the uncovered parts were a technical crash course and an analyst landscape scan (about 12 chats each), plus a prep guide and handoff file (saved for every company). The user picked three additions from the options offered.

## Decision

- `/prep [company]` and `/handoff`. One intake batch: company, job link, interviewer LinkedIn, stage and what it tests, hours left, optional own take. Claude reads the link and profile itself and asks for a paste on the first failure. Triage by hours left (under 24 hours, 2 to 3 days, a week or more). One per-company guide with fixed sections. A one-page handoff summary. Final questions to ask are drafted, then critiqued and trimmed, using four criteria: shows research, probes what success looks like, reveals the interviewer's view, tests fit.
- `/crash-course [product]`. Four layers, one at a time: what it is, architecture, deeper with systems vocabulary, edge cases. Stop after each. Capabilities kept separate from use cases. Vendor docs first. "Not documented" flagged.
- `/analysts [company or category]`. Gartner, Forrester, IDC, SACR and others, 2023 onward. Per report, a status: read in full, public summary only, or paywalled and not read. Vendor position only if visible in what was read. A Coverage block. Ask for an upload on the first failed fetch. Reuses the paywalled-report handling from commit fd5780a.

## Why

- These were the most frequent recurring workflows not covered by a skill.
- Triage tiers are borrowed from the generic claude.ai `interview-coach`, which the user also used.

## Alternatives rejected

- Merging the generic `interview-coach` into the PMM coach. The user did not select it and asked what it meant. It holds interviewer archetypes, narrative frameworks, a mock playbook and intake questions. `/prep` borrows only its time tiers and four question criteria. The merge decision moves to the claude.ai project.

## Consequences and follow-ups

- Open: end-to-end runs of `/prep`, `/crash-course` and `/analysts` have not been done.

## Implemented in

- `.claude/skills/pmm-senior-principal-interview-coach/References/prep-guide.md`, `technical-crash-course.md`, `analyst-landscape-scan.md` and `SKILL.md`.
- Commit 51bef5d (PR #5).
