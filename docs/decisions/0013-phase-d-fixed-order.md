# 0013: Phase D critique runs in a fixed seven-step order

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User, refined over several rounds
- Source: Conversation, 2026-09-01

## Context

In the dry run, the critique order was improvised, so the user could not tell what path the critique would take or whether it would repeat between interviews.

## Decision

Critique runs in this order every time:
1. So-what: does it lead with business impact, is it specific to this company's feature, and does it match the Step 2 to 4 research claim by claim.
2. Persona coverage: does every persona have a value proposition, are two of them the same argument, and does the draft carry the customer voice found in Step 6.
3. Gap honesty: has the draft overstated a benefit beyond what the brief claims, or contradicted something the brief says the feature cannot do.
4. Boundaries list: check the candidate's own list against the research.
5. Headline: a real headline, not a value proposition with the full stop removed; differentiated; tone and emotion fit the primary persona.
6. Order of personas: which one leads, and is that consistent with what was established.
7. "Why I cut this": rehearse the reason for every angle dropped.

## Why

- Content correctness comes first, then craft, then readiness to defend live. A headline's craft is not worth critiquing before the claims are sound. Cuts cannot be rehearsed until the pass has shown what was cut.
- The order is the same between interviews.

## Alternatives rejected

- Eliciting the boundaries list in Phase D (see 0012).

## Consequences and follow-ups

- All seven steps check the candidate's authored material against the research. None originates content.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Phase D).
- Commit e36845a (PR #2).
