# 0010: Find the closest real capability to anchor research

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-09-01

## Context

Customer-voice research came back thin. The exercise brief described a feature that does not exist, so there were no real customers to quote. The user's example: Cockroach Labs does not ship "adaptive leaseholder rebalancing", but it does ship database read and write storage for hot data.

## Decision

When Phase A shows a real company, Step 1 identifies the closest existing capability the company actually ships. That capability becomes the anchor category for the competitor research (Step 3) and the customer-voice research (Step 6).

## Why

- Case studies and customer language exist for the real adjacent capability, not the hypothetical one.
- The user said an adjacent area is still valuable even when the exact problem is not an existing product.
- Step 3 and Step 4 went well in the dry run. Step 6 was the weak one, and the missing target category was the cause.

## Alternatives rejected

- Searching directly against the fictional capability.

## Consequences and follow-ups

- Term definitions in Step 1 stay reactive to what the candidate flags.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Step 1).
