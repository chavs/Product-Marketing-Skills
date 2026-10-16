# 0001: Separate the live interview assistant from the pre-interview coach

- Status: Accepted
- Date: 2026-08-30
- Area: skills-architecture
- Decided by: User
- Source: Conversation, 2026-08-30

## Context

The coach skill held a competitive-intelligence method built for slow, thorough pre-interview research. The user wanted an assistant for use during an actual interview, and asked whether that method should move under it.

## Decision

Create `live-job-interview-assistant` as its own skill. Move the competitive-intelligence method out of the coach entirely. It is moved, not copied.

## Why

- The two need opposite operating assumptions. The coach works at minutes per turn. The live assistant works at seconds per turn, mid-conversation.
- One method with one owner stops two versions drifting apart.
- The user chose "move it out entirely" and later stated that the live assistant must be a separate skill.

## Alternatives rejected

- Keep a thorough async version in the coach and a faster live version in the new skill. Rejected: two methods to maintain.
- Keep the file in the coach as a shared reference (the assistant's first suggestion). Dropped after the user said the live version has to run live and multi-turn.

## Consequences and follow-ups

- The coach lost its Competitive intelligence entry point and its `/competitors` command.
- The coach's Research entry point now covers general, pre-interview research only, and points to the live assistant for anything live or deep.

## Implemented in

- Commit b55ee32 (PR #1).
- `.claude/skills/live-job-interview-assistant/` and the coach `SKILL.md`.
