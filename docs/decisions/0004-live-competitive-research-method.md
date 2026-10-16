# 0004: Live competitive research method and the /competitive-intel command

- Status: Accepted
- Date: 2026-08-30
- Area: live-assistant
- Decided by: Agreed (user approved the design), user chose the command name
- Source: Conversation, 2026-08-30

## Context

The coach's original method was built for async prep. It confirmed scope with the user, hunted for paywalled analyst reports, showed a competitor list and waited for approval, and researched seven dimensions per product.

## Decision

Adapt it for live use. State assumptions inline instead of asking. Skip the paywalled-analyst chase and tag the claim `[Estimated]`. Do not show a list and wait. Answer only what was asked. Allow follow-up turns. Keep the source-trust ranking and the tagging. The command is `/competitive-intel [question]`, renamed from `/live-research`.

## Why

- A live turn has seconds, not minutes. Correction is cheap in a multi-turn flow.
- Tags keep fast answers honest.
- The user said live and multi-turn applies to competitive research itself, not only to the assistant.

## Alternatives rejected

- Pre-built research that the assistant only retrieves. This was the assistant's first reading of the spec. Rejected when the user said the research itself runs live.

## Consequences and follow-ups

- Reddit and Hacker News are excluded at every tier.
- Budget competitors are out of scope.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/live-competitive-research.md`.
- Commit b55ee32 (PR #1).
