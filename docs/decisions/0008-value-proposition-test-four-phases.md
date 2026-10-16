# 0008: Restructure the Value Proposition Test into four phases

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User (feedback after a dry run), Agreed (design)
- Source: Conversation, 2026-09-01

## Context

A live dry run of the original seven-step workflow, on an invented Cockroach Labs brief, took about an hour against a simulated 20 minutes. The causes the user named:
- Many scattered open questions. Personas emerged over four or more turns.
- Step 3's dependence on Step 2 was not stated, so it looked like it was waiting on the user.
- Research pasted into chat crowded out the UI.
- Customer-voice research was weak because there was no clear category to search.

## Decision

Run the workflow in phases:
- Phase A: intake, one batch of questions, then a confirmation recap (see 0009).
- Step 1: mechanics and term definitions, interactive (see 0010).
- Phase B: Steps 2 to 6 run autonomously with no back-and-forth, and write to a file (see 0011).
- Phase C: the candidate drafts, unassisted (see 0012).
- Phase D: critique, interactive, in a fixed order (see 0013).

## Why

- Ask every question once, up front, so nothing interrupts research.
- Keep research inside the first half of the time (see 0007).
- Keep the chat usable by moving bulk output into a document.
- State step dependencies in the file so the user never has to guess what unblocks the next step.

## Alternatives rejected

- None recorded for the overall shape. See the linked decisions for the parts.

## Consequences and follow-ups

- The user flagged two possible future splits, not acted on: Phase A may move to the coach, and Phase D may become its own skill.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md`.
- Commit e36845a (PR #2).
