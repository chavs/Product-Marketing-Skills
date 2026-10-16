# 0011: Research output goes to a local markdown file

- Status: Accepted (the folder it is saved in was changed by 0020)
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-09-01

## Context

Long research pasted into the chat crowded out the UI during a timed exercise. A Google Drive connector was available, so the mechanism had to be chosen.

## Decision

Phase B and Phase C output is written to one local markdown file. It is not pasted into chat and it is not a Google Doc.

## Why

- A local write has no network round-trip, so it stays fast under time pressure.
- It works in a session where the Drive connector is not available.
- The user chose "local markdown file" when asked.

## Alternatives rejected

- A Google Drive document. It persists across devices but depends on the connector and is slower to create and update.

## Consequences and follow-ups

- The case-study skill uses the same pattern.
- The default save location moved outside the repo on 2026-10-14 (0020).

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md`.
- Commit 5587362 (PR #3).
