# 0025: Keep skill descriptions short enough to show in the skill list

- Status: Accepted for the coach. Proposed for the live assistant and the case-study skill.
- Date: 2026-10-14
- Area: commands-and-tooling
- Decided by: Agreed for the coach (user approved the plan). The other two are proposed and unanswered.
- Source: Conversation, 2026-10-14

## Context

Claude Code truncates a skill's description at 1,536 characters in the skill list. The coach description was 1,618 characters. The coach also pointed to `references/` in lowercase while the folder is `References/`, which works on Windows and breaks on macOS and Linux.

After the merge, the skill list showed `live-job-interview-assistant` (1,341 characters) as only its title. The other two showed in full. The live assistant's frontmatter is intact and shaped like the others.

## Decision

Accepted: the coach description was cut from 1,618 to 1,132 characters. Its seven lowercase `references/` pointers now read `References/`.

Proposed, not yet decided: trim the live assistant (1,341) and the case-study skill (1,336) to about 900 characters each, and move detail into the skill bodies.

## Why

- A description that is cut or replaced by its title weakens natural-language triggering. The slash commands still work, because they call the skill by name.
- Hypothesis for the live assistant's collapse: Claude Code shortens the longest descriptions when the whole skill list is large. The live assistant is now the longest of the three, and the coach was shown as only its title when it was the longest. This is not confirmed.

## Alternatives rejected

- None recorded.

## Consequences and follow-ups

- Open: the user's yes or no on trimming the other two.
- The claude.ai limit is stricter, at 1,024 characters. That belongs to the deferred claude.ai project (0018).

## Implemented in

- Coach: commit 51bef5d (PR #5).
- Live assistant and case-study: not changed.
