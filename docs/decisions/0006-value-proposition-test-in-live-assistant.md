# 0006: The Value Proposition Test lives in the live assistant

- Status: Accepted
- Date: 2026-08-30 (placement), 2026-09-01 (rename)
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-08-30 and 2026-09-01

## Context

The user supplied a spec for an exercise that turns a roadmap or engineering brief into a so-what, persona value propositions and a headline, then defends it. The spec described adding it to the coach and said competitive research there is pre-built, not run live.

## Decision

The exercise is a workflow inside `live-job-interview-assistant`. It runs live and multi-turn, and its competitive and customer-voice research runs live. It is called the Value Proposition Test. The file is `value-proposition-test-practice.md` and the command is `/value-proposition-test`.

## Why

- It is used during a real interview exercise, so it belongs with the live skill.
- The user overrode the spec's pre-built-research assumption.
- The deliverable is value propositions, so the old name "translation test" was wrong.
- The user chose to rename the file and command to match, not only the title.

## Alternatives rejected

- Adding it to the coach, as the spec said.
- Renaming only the display name and keeping `/translation-test`.

## Consequences and follow-ups

- Other exercise types (GTM launch, enablement, positioning and messaging, slides) are out of scope. Each gets its own reference file when built.
- The user's request said "valid proposition test". It was confirmed as "Value Proposition Test".

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md`.
- Commits b55ee32 (PR #1) and e36845a (PR #2).
