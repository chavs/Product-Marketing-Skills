# 0026: Keep a decision log in docs/decisions/ so decisions do not depend on compaction

- Status: Accepted
- Date: 2026-10-14
- Area: process
- Decided by: User (asked for it), Agreed (structure)
- Source: Conversation, 2026-10-14

## Context

Decisions and the reasons for them were spread across a long conversation, memory notes and commit messages. Claude Code compaction summarizes a conversation and can drop detail. The user asked for the decisions and why they were taken in a standardised file, so they do not rely on compaction.

## Decision

Keep an ADR-style log in `docs/decisions/`, tracked in git:
- `README.md` is the index. It has one row per decision, the open decisions, environment notes and related records.
- `TEMPLATE.md` is the entry template.
- One short file per decision, numbered `NNNN-short-title.md`, with the same fields every time.

An accepted decision is not rewritten. A changed decision gets a new file, and the old one is marked "Superseded by NNNN".

## Why

- A file in git survives compaction, recycled worktrees and new sessions.
- One file per decision lets a session read the index and then only the entries it needs, which keeps context small.
- A fixed template keeps entries comparable and makes gaps visible.

## Alternatives rejected

- Relying on compaction and on memory notes alone. Memory notes are short and unstructured.
- One long single file. It grows without bound and has to be read whole.
- Saving it outside the repo, as with generated files (0020). This is hand-written documentation that should be versioned.

## Consequences and follow-ups

- Open: whether `CLAUDE.md` should import `docs/decisions/README.md` so every session sees the index (about 2k tokens). Without it, a session finds the log through the memory pointer.
- Decisions made before 2026-08-30 (the original coach build) and the practice answers for the invented Cockroach Labs brief are not recorded here.

## Implemented in

- `docs/decisions/`.
