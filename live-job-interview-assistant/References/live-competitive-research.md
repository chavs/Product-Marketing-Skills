# Live Competitive Research

A method for researching product-level competitors in real time, while a live interview or live exercise is actually happening. This is the same underlying discipline as a thorough pre-interview competitive research pass, compressed for a setting where the candidate has seconds, not minutes, and the conversation doesn't pause. Fully generic — never hardcode a specific company or example into this file.

## What's different from doing this research ahead of time

The candidate is mid-conversation. Every gate that would normally pause to confirm scope with the user before proceeding has to go — there's no time for a back-and-forth to agree on a market category before answering. Instead:

- **State assumptions inline, don't block on them.** If segment, tier, or market category isn't obvious from context, make the most reasonable inference from what's already been said in the interview and say so in one clause (e.g. "assuming enterprise segment based on the role") rather than stopping to ask. Correct on the next turn if the candidate flags it.
- **Skip the paywalled-analyst chase.** Gartner/Forrester/IDC reports can't be fetched live, and there's no time to ask the candidate to go find and paste one mid-interview. Default to what's actually reachable fast: the competitor's own site, G2 (usually unpaywalled), a quick web search. If a claim genuinely needs deeper analyst verification, tag it `[Estimated]` and move on — that verification can happen after the interview, not during it.
- **Skip the "show the list and confirm" step.** Give the best-fit competitor or product directly. If the candidate says that's the wrong one, adjust on the next turn — this is multi-turn by design, so correction is cheap.
- **Answer only what was asked, at first.** A per-product deep dive (Step 3 below) has several dimensions — don't dump all of them unprompted. Answer the specific question, then let follow-ups pull more.

## Multi-turn is the model

Each turn answers the immediate ask. Follow-ups ("now compare that to us," "what about their pricing," "and what do their customers say is missing") build on what's already surfaced in this session — don't re-derive context from scratch on every turn.

## Resolving to product level

Resolve a competitor to the specific *product* relevant to the problem space (e.g. "Aurora RDS," not "AWS," and not "Aurora RDS's multi-region failover capability"). This only matters for companies with multiple products in their portfolio — a single-product company needs no further resolution. State the resolution inline; don't ask for confirmation unless it's genuinely ambiguous which product is meant.

## Per-product research (on request)

When asked to go deeper on a named competitor product, cover whichever of these the question actually calls for — don't recite all of them by default:

1. **Value proposition**
2. **Ideal customer profile** — who it's for
3. **Benefit(s)** — what it delivers
4. **Pricing model** — how it's priced, and any relevant cost dynamic
5. **Known limitations/gaps** — what it doesn't do, or does worse, relative to the same problem space
6. **The competitor's own positioning language** — how they describe themselves, not how anyone else (including the interviewing company) frames them. Guards against arguing against a strawman.
7. **Recent, relevant product changes** — anything shipped in roughly the last 6–12 months that closes or widens the gap. This is what makes an existing positioning bet stale.

For customer-facing claims — what a customer actually experienced, said, or achieved — use `References/customer-voice-research.md` instead of general web sourcing; it has its own ranking tuned for that kind of claim.

## Process competitors (lighter-weight, live version)

Process competitors aren't products — they're the end-to-end way a persona actually solved the problem before/without this product. Live, give a quick sketch rather than the full journey map: what triggered the need, what they actually did, where it was painful, and what broke when it failed. Go deeper only if asked.

## Source-trust ranking

Applies to every product-fact claim (not customer-experience claims — see the customer-voice file for those):

1. The competitor's own documentation, pricing, and architecture pages
2. The interviewing company's own comparison pages about the competitor — read as advocacy, not neutral fact
3. Practitioner-level content — conference talks, engineering blogs from people who've actually used the product
4. Independent analyst sources — Gartner, Forrester, IDC, G2

**Reddit and Hacker News are excluded entirely — not deprioritized, not used at any tier.**

## Tagging

Tag every claim `[Confirmed]`, `[Estimated]`, or `[Inferred]`, with a short inline source. Live speed doesn't waive this — an untagged claim delivered fast is still a liability if it's wrong.

## Out of scope

**Budget competitors** (alternative uses of the same budget, unrelated to any technical solution) are out of scope. Skip entirely unless asked to add it.
