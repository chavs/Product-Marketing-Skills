# Competitive Intelligence Research

A method for identifying and researching product-level competitors ahead of a PMM interview. Fully generic — it asks for company, segment, and tier every time it's run, the same way the rest of this skill asks for target company/role rather than assuming one. Never hardcode a specific company or example into this file.

## Step 1: Check if the user already knows the competitor list

Ask directly. If yes, skip straight to per-product research (Step 4) using the user's list. Don't re-derive it.

## Step 2: Scope the segment and tier

If the user doesn't already know the list, ask two things:

- **Which business line/segment** is relevant? A single company can have multiple segments (e.g. an enterprise product line vs. a separate self-serve/developer product line), and each may have a genuinely different competitive set. Don't assume one segment — ask, and scope separately if more than one applies.
- **What tier does that segment serve?** Enterprise, self-serve/developer, or mid-market. This determines which source to route to next.

## Step 3: Identify named (product-level) competitors

**Routing by tier:**
- Enterprise → Gartner, Forrester, or IDC market analysis for the relevant category.
- Self-serve / developer / mid-market → G2 for the relevant category.

**Handling paywalled analyst content** (Gartner/Forrester/IDC reports are almost always paywalled and can't be fetched directly):
1. Web search to identify the specific relevant report (title, analyst firm, market category, publish date/quarter).
2. Show the user what was found, with a link to wherever it surfaced (press release, analyst abstract page, etc.).
3. Ask the user to supply the actual report content — pasted text, PDF, or markdown — if they have access via their own or an employer's subscription.
4. If the user can't get access, fall back to secondary signals (e.g. vendor press releases announcing placement), explicitly tagged `[Inferred]` or `[Estimated]`, never `[Confirmed]` — a press release only shows the flattering placement, not the full picture.
5. Once the user supplies real report content, treat it as `[Confirmed]` and extract competitor placements/category definitions directly from it.

G2 profile pages are usually accessible without login — check before assuming a paywall applies there too.

**Confirm the market category** with the user before proceeding — state which category you're using and ask them to confirm it's right for this problem space. If unsure which category applies, research candidates and present them for the user to choose from; don't guess silently.

**Resolve to product level, not company level, not feature level.** Once candidate competitor companies are identified, resolve each to the specific *product* relevant to this problem space (e.g. "Aurora RDS," not "AWS," and not "Aurora RDS's multi-region failover capability"). This decomposition step only matters for companies with multiple products in their portfolio — a single-product company needs no further resolution.

**Show the resulting product-level competitor list to the user and ask them to confirm it** before running per-product research.

## Step 4: Per-product research (named competitors)

Run once per confirmed competitor *product*, not once per company. Research:

1. **Value proposition**
2. **Ideal customer profile** — who it's for
3. **Benefit(s)** — what it delivers
4. **Pricing model** — how it's priced, and any cost dynamic relevant to the problem space
5. **Known limitations/gaps** — what it doesn't do, or does worse, relative to the same problem space
6. **The competitor's own positioning language** — how they describe themselves, not how anyone else (including the interviewing/researching company) frames them. Guards against arguing against a strawman.
7. **Recent, relevant product changes** — anything shipped in roughly the last 6–12 months that closes or widens the gap in this problem space. This is what makes an existing positioning bet stale.

Tag every claim `[Confirmed]`, `[Estimated]`, or `[Inferred]`, and cite the source inline for each claim, per the source-trust ranking below.

## Step 5: Process competitors (separate from named competitors)

Process competitors are not products — they're the end-to-end way a persona actually solved the problem before/without this product. Don't decompose into individual tools; trace the whole journey. Tools may appear inside it, but the journey itself is the competitor to displace.

Trace, per relevant persona:
- **Trigger** — what caused the need to solve this problem
- **Steps** — what they actually did, in order
- **Tools/products touched along the way** — named only where relevant, not the focus
- **Pain points** — where it was slow, manual, error-prone, or required specialized knowledge
- **Failure mode** — what happened when it broke, and what the fallback was

Source against the same source-trust ranking below as Step 4. Tag every claim `[Confirmed]`, `[Estimated]`, or `[Inferred]`, with inline sourcing.

## Out of scope (explicitly — not a placeholder)

**Budget competitors** (alternative uses of the same budget, unrelated to any technical solution) are out of scope for this version. Don't build placeholder logic for this — skip it entirely unless the user asks to add it later.

## Source-trust ranking

Applies to every claim produced by this reference file — both per-product research (Step 4) and process-competitor research (Step 5):

1. The competitor's own documentation, pricing, and architecture pages
2. The interviewing/researching company's own comparison pages about the competitor — read as advocacy, not neutral fact; needs independent verification before being stated as settled
3. Practitioner-level content — conference talks, engineering blogs from people who've actually used the product
4. Independent analyst sources — Gartner, Forrester, IDC, G2

**Reddit and Hacker News are excluded entirely — not deprioritized, not used at any tier.**
