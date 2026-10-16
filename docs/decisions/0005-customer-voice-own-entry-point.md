# 0005: Customer voice is its own entry point and command

- Status: Accepted
- Date: 2026-08-30
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-08-30

## Context

Customer voice research (how real customers talk about a problem, or checking a claim about a customer) started inside the competitive entry point. The user asked whether part of it should be its own command.

## Decision

Make `/customer-voice [question]` a separate entry point with its own reference file. It covers the target company's customers, a competitor's customers, or the problem space in general. It has two equal uses: language calibration and fact-checking.

Source ranking: the company's own case studies, videos and quotes first; then practitioner content; then review sites such as G2 and Gartner Peer Insights. Reddit and Hacker News are excluded entirely. Every claim is tagged and sourced.

## Why

- Language calibration is useful with no competitor in play, for example mid-exercise.
- Customer-experience claims need a different source ranking from product facts.

## Alternatives rejected

- Keep it inside `/competitive-intel`. Rejected by the user after the split was explained.

## Consequences and follow-ups

- A request that is both competitive and customer-voice (for example "what do their customers say is missing") reads both reference files.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/customer-voice-research.md`.
- `.claude/skills/live-job-interview-assistant/SKILL.md` (entry points, commands).
