# 0024: Real slash commands through .claude/commands/ wrappers

- Status: Accepted (typed-command autocomplete is not yet verified)
- Date: 2026-10-14
- Area: commands-and-tooling
- Decided by: Agreed (the user wanted slash commands; user approved the plan)
- Source: Conversation, 2026-10-14. Claude Code skills docs: https://code.claude.com/docs/en/skills

## Context

The user wanted to evoke the skills with slash commands. Per the Claude Code docs, a command written inside a SKILL.md is only an instruction. Typing it does nothing. A skill name or a `.claude/commands/<name>.md` file is what creates `/name`. The docs read did not cover the last ~7,000 characters of the page.

## Decision

Add 17 thin wrappers in `.claude/commands/`, one for each command in the SKILL.md command tables. Each routes to the right skill and entry point, passes `$ARGUMENTS`, and sets `disable-model-invocation: true` so Claude does not auto-load it. `/case-study check` routes to Phase D.

Command files may carry `model`, `effort`, `context: fork` and `agent`. SKILL.md frontmatter stays limited to `name` and `description`, because a claude.ai upload hard-errors on other keys. No model has been chosen for any mode.

## Why

- It delivers what the user asked for with the least duplication: wrappers hold no logic.
- It corrects two earlier statements by the assistant: that moving the skills made their internal commands invocable (0015), and that a skill cannot choose its model. In Claude Code it can, through command files.

## Alternatives rejected

- One skill per command. More description tokens in the skill list and more upload-safe constraints.

## Consequences and follow-ups

- Adding a command to a SKILL.md table means adding its wrapper. Checked on 2026-10-14: 17 wrappers and 17 distinct table commands, matching in both directions.
- Open: confirm in a fresh Claude Code session that the commands autocomplete.
- Open: which modes should use which model (none chosen).

## Implemented in

- `.claude/commands/*.md` (17 files).
- Commit f01641f (PR #5).
