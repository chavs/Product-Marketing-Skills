# 0017: Always run a dedicated adversarial pass against the candidate's hypothesis

- Status: Accepted
- Date: 2026-09-14
- Area: case-study
- Decided by: Recorded from memory and commits (the user asked for both passes in another session)
- Source: Memory note `feedback-hypothesis-stress-testing`; commit 43aa1c5

## Context

The first four research tracks were told to test, not assume, the user's working hypothesis. They did surface some counter-evidence. The user still worried the research had a "prove my hypothesis" bias and asked for a pass whose only job was to disprove it.

## Decision

When the candidate states a working hypothesis, always run a separate track whose only mandate is disconfirmation. Report both sides, evidence first, with a verdict that follows. Hold disconfirming evidence to the same sourcing bar as confirming evidence. For a competitive or user-roadmap task, also run a competitive-response simulation: how each named competitor would rebut the target company's position, grounded in the competitor's real public material, never invented quotes.

## Why

- A track built to research a claim structurally finds more confirming than disconfirming evidence, even when told to stay neutral.
- The adversarial pass gave a materially weaker verdict on 2 of the 5 hypothesis planks, so it changed the conclusion. It was not a redundant check.

## Alternatives rejected

- Instructing the regular tracks to stay neutral. It was not enough.

## Consequences and follow-ups

- Both passes are permanent parts of the case-study skill, not a one-off.

## Implemented in

- `.claude/skills/pmm-case-study-assistant/References/hypothesis-stress-testing.md`.
- `.claude/skills/pmm-case-study-assistant/References/competitive-response-simulation.md`.
- Commit 43aa1c5 (PR #4).
