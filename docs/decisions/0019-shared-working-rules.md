# 0019: One shared rules file, loaded through CLAUDE.md

- Status: Accepted (loading through the `@` import is not yet verified)
- Date: 2026-10-14
- Area: working-rules
- Decided by: Agreed (user approved the plan)
- Source: Conversation, 2026-10-14

## Context

The learnings document's most frequent correction was "do less than you just did", seen in 8 chats. The Project instructions were empty, and the repo had no `CLAUDE.md`.

## Decision

Write the eight corrections once, as rules, in `interview-working-rules.md`. `CLAUDE.md` loads it in every Claude Code session through an `@` import. The rules:
1. Do only what was asked. Confirm the ask in one line before any build. Critique and ask questions instead of rewriting drafts.
2. Primary sources first. State the source order up front. Say what was and was not read. Cite inline.
3. List load-bearing definitions and org facts as one assumptions block and get a yes.
4. Short, plain sentences. No em dashes. Meet length limits on the first pass.
5. Be critical by default.
6. Look at rendered output before showing it.
7. Say so on the first failed fetch and ask for an upload.
8. Re-read earlier asks before finalizing. Intake questions allow "other".

## Why

- The corrections kept recurring across chats, and nothing held them.
- One file means one place to change them.

## Alternatives rejected

- Copying the rules into every SKILL.md. They would drift, and there is no portability need yet.
- Keeping them only in memory notes. They would not be visible in the repo.

## Consequences and follow-ups

- Rule 4 applies to anything the user might send or submit, and chat replies stay plain too. That scope was the assistant's reading, approved with the plan.
- To verify in a fresh session: that the `@interview-working-rules.md` import loads. If it does not, inline the rules into `CLAUDE.md`.
- For claude.ai, the same file is pasted into the Project instructions. That is deferred (0018).

## Implemented in

- `interview-working-rules.md` and `CLAUDE.md`.
- Commit 2c21a73 (PR #5).
