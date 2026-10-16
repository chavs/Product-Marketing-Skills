# 0015: Skills live under .claude/skills/ so Claude Code can find them

- Status: Accepted
- Date: 2026-09-01
- Area: skills-architecture
- Decided by: User (asked why the skill was not a slash command), Agreed (fix)
- Source: Conversation, 2026-09-01

## Context

The user asked why the live assistant could not be evoked with a slash command, since the code was committed to GitHub. The skill folders sat at the repo root.

## Decision

Move both skills (and any future skill) to `.claude/skills/<name>/SKILL.md`, using `git mv` so history is kept.

## Why

- Claude Code discovers project skills from `.claude/skills/`. Folders at the repo root are invisible to it.
- Committing to GitHub and skill discovery are unrelated systems.
- Checked directly: `.claude/` held only `worktrees/`. After the move, the session's skill list showed both skills.

## Alternatives rejected

- None recorded.

## Consequences and follow-ups

- This made the skill names invocable. It did not make the commands written inside a SKILL.md invocable. See 0024.

## Implemented in

- Commit e36845a (PR #2).
