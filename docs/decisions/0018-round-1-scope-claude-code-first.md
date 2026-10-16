# 0018: Round 1 covers Claude Code only; claude.ai work is deferred

- Status: Accepted
- Date: 2026-10-14
- Area: process
- Decided by: User
- Source: Conversation, 2026-10-14 (plan approval)

## Context

A 24-chat learnings document (built 2026-10-06 from the user's claude.ai Project chats) listed seven candidate skills, eight recurring corrections and four suggested next actions. It only saw the skills installed on claude.ai. The user asked how to implement it.

## Decision

Round 1 works in Claude Code only. In scope: shared working rules, case-study upgrades, the answer-first drill, `/prep` and `/handoff`, `/crash-course`, `/analysts`, real slash commands, and a stable output folder.

Out of Round 1, each as its own later round: offer evaluation, an interview deck builder, and the target-company tracker. Deferred as a separate claude.ai project: trimming descriptions to 1,024 characters, a packaging script and upload zips, uploading to claude.ai, and pasting the rules into the Project instructions.

## Why

- The user said to fix the problem in Claude Code first, and to move everything claude.ai into a future project.
- claude.ai is a different surface with different limits: 1,024-character descriptions and a restricted set of frontmatter keys. Custom skills do not sync across surfaces.
- Each new skill is its own design conversation.

## Alternatives rejected

- Doing publishing to claude.ai in the same round. Rejected by the user.

## Consequences and follow-ups

- Finding: the doc's "install the finished PMM skill" is a publishing problem, because the repo already had the story bank, debrief, `/score`, `/tone` and `/bonus`. Its "build the take-home skill" was mostly done by `pmm-case-study-assistant`.
- To keep the later upload easy, SKILL.md frontmatter stays limited to `name` and `description`.
- The deferred list is in memory note `project-claude-ai-publishing-deferred`.

## Implemented in

- Plan approved 2026-10-14.
- PR #5 (commits 2c21a73 to 7cd2fea).
