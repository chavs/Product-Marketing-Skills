# 0020: Generated files go outside the repo, in ~/Documents/interview-prep/

- Status: Accepted. Supersedes the earlier choice to keep outputs gitignored in the working directory (commit eb442e2) and the "current working directory" wording in 0011.
- Date: 2026-10-14
- Area: process
- Decided by: Agreed (user approved the plan)
- Source: Conversation, 2026-10-14

## Context

The DataDome research (1,594 lines) and the Cockroach Labs exercise notes (88 lines) sat in gitignored files inside Claude Code worktrees. A recycled worktree deletes untracked files. This session's own worktree was recycled mid-conversation.

## Decision

Generated files (research, prep guides, handoffs, notes, drill logs) are saved to `~/Documents/interview-prep/<company-slug>/`, outside the repo. The skill says the full path each time. The two existing files were copied, not moved, to `C:\Users\saine\Documents\interview-prep\datadome\` and `C:\Users\saine\Documents\interview-prep\cockroach-labs\`.

## Why

- Untracked files in a worktree are lost when it is recycled.
- The research is the most expensive thing to recreate.

## Alternatives rejected

- Leaving files gitignored in the working directory, as before.
- Committing the research to the repo. It is large, personal and generated.

## Consequences and follow-ups

- Open: a gitignored `case-study-work/` folder of scratch tracks remains in the DataDome worktree. It was not copied. The user has been asked and has not answered.
- This does not apply to this decision log, which is hand-written documentation and is tracked in git (0026).

## Implemented in

- `CLAUDE.md`, `.claude/skills/pmm-case-study-assistant/SKILL.md`, `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md`, and the new coach references.
- Commits 2c21a73 and 76b08fc (PR #5).
