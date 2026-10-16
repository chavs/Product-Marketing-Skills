# 0007: No hardcoded time limit, and research gets half of the stated time

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-09-01

## Context

The spec forbids hardcoding a time limit, because loops differ (20 minutes, 30 minutes, or untimed). A dry run needed a cap on research so most of the time was left for drafting and critique.

## Decision

Ask the candidate for their time constraint. Phase B research gets exactly half of whatever they state. The other half is for drafting and critique. It is a firm allocation: research stops and hands off when its half is used.

## Why

- It keeps the no-hardcoded-number rule.
- It is simple to apply.
- The user chose "always exactly half of the stated constraint".

## Alternatives rejected

- A fixed research budget of about 10 minutes regardless of total time (the assistant's recommendation). Its argument was that research effort should not grow in a longer exercise. The user preferred the simpler proportional rule.

## Consequences and follow-ups

- The user first said research should take only 10 minutes. In a 20-minute exercise that is half, and they then chose the proportional rule when asked.

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (opening note and Phase B).
- Commit e36845a (PR #2).
