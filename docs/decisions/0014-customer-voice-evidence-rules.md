# 0014: Customer-voice evidence rules (attribution, relevance, search order)

- Status: Accepted
- Date: 2026-09-01
- Area: live-assistant
- Decided by: User
- Source: Conversation, 2026-09-01

## Context

In the dry run:
- A "$1.5M saved per state" claim was tagged `[Confirmed]`. It was a vendor blog paraphrasing an unnamed customer.
- A real, named Form3 quote was generic praise and not about the pain point.
- The best source, a practitioner's first-person blog post, was found only after the user asked for it.
- A reply with quoted claims went out without source links until the user asked.

## Decision

Apply two independent checks to every claim.
- Attribution sets the tag. A named person's quote is `[Confirmed]`. A case study naming a real customer and product, told in vendor voice, is `[Estimated]` and still usable. A fully anonymized claim is a last resort and is flagged as anonymized.
- Relevance: does the claim address the specific pain point, or is it general praise.

Search order: practitioner or vendor-agnostic content first, then a case study naming a specific customer and product in the adjacent space, and avoid generic vendor blog narrative. Cap the search at two or three passes. State gaps honestly. Put the source link inline on every claim.

## Why

- The user said it does not matter whether a case study is written in the customer's language or the vendor's, as long as it is anchored to a named instance.
- The trust ranking is unchanged: direct quotes and case studies still outrank practitioner content when two claims conflict. The search order is about speed, not trust.

## Alternatives rejected

- Treating a page found in the company's own case-study directory as a real quote without checking.
- Applying the same two checks to Step 3 now. The user chose Step 6 only for now, because Step 3 held up in the dry run.

## Consequences and follow-ups

- Step 6 ends with the gap stated if nothing clears both checks inside the cap.
- Reused in the case-study skill as a Coverage block (0021).

## Implemented in

- `.claude/skills/live-job-interview-assistant/References/value-proposition-test-practice.md` (Step 6).
- Memory note `feedback-research-claim-verification`.
- Commit e36845a (PR #2).
