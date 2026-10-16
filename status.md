# Status for the next session

Written: 2026-10-16. This file is only for the next session. At the end of that session, replace it with a new status.md that covers that session's decisions and changes. Do not append to it.

Permanent decisions and reasons are not kept here. They live in `docs/decisions/README.md`.

## State at the end of this session

- Round 1 (PR #5, commits 2c21a73 to 7cd2fea) is merged to `main`. It added the shared working rules, the case-study upgrades, the answer-first drill, `/prep`, `/handoff`, `/crash-course`, `/analysts`, and 17 real slash commands.
- The decision log (`docs/decisions/`, 26 decisions plus README and TEMPLATE) is written and checked, but it is not committed. It sits untracked in worktree `priceless-greider-67f611`, branch `claude/interview-learnings-round-1`. A recycled worktree deletes it.
- This `status.md` is also untracked.
- Memory notes are updated and are not in the repo: the architecture note, the deferred claude.ai note, and a pointer to the decision log.

## Do first

1. Commit `docs/decisions/` and this file on a new branch off `origin/main` (for example `claude/decision-log`). Open the PR with the compare link, because `gh` is not installed: `https://github.com/chavs/Product-Marketing-Skills/compare/main...<branch>?expand=1`.
2. Answer the two open questions below.

## Questions waiting for the user

1. Should `CLAUDE.md` import `docs/decisions/README.md` (about 2k tokens every session)? Or should sessions find the log through the memory pointer only?
2. Should the live assistant (1,341 characters) and the case-study skill (1,336) be trimmed to about 900 each? The live assistant showed as only its title in the skill list. The cause is unconfirmed.

## Checks that need a fresh Claude Code session

- Typed commands autocomplete (0024).
- The `CLAUDE.md` `@interview-working-rules.md` import loads (0019).
- `/drill`, `/prep`, `/crash-course` and `/analysts` run end to end (0022, 0023). Only the mechanics were tested, on throwaway input.

## Other open items

The full list is in the README under "Open decisions and pending checks". The two not mentioned above:
- Copy the gitignored `case-study-work/` folder from the DataDome worktree to `~/Documents/interview-prep/datadome/`.
- Choose a model for each mode, if any.
