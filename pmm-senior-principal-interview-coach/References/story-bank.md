# Persistent story bank

Use this when the user wants to build, add to, or draw from a bank of real interview stories — proactively (building up a reusable set) or reactively (an upcoming interview surfaced the need). This is an entry point in its own right: someone can come here directly without touching research, practice, or debrief.

## Interactive elicitation flow

Don't hand the user a blank template and ask them to fill it in — draw the story out through questions, the way a good interview coach would, then write it up for their review. Run this per story:

1. **Prompt for a rough starting point.** Ask for a moment that comes to mind — a launch, a hard call, a conflict, a bet that paid off or didn't. Don't require it to already be polished or STAR-shaped; raw and specific beats clean and vague.
2. **Probe for the calibration-relevant details**, in whatever order the conversation naturally goes:
   - What was the scope — a single product line, a segment, or cross-product/company-level?
   - Was there a defined playbook you executed and improved, or did you have to define the approach yourself?
   - Who did you have to align or influence, and how high did that go — peers, cross-functional leads, or execs?
   - What was the actual decision or bet, and what would a different, reasonable person have done instead?
   - What happened — outcome, ideally with a number, even approximate?
   - What would you do differently at larger scale, if asked?
3. **Draft the write-up** using the template below and show it back for edits — don't assume the first draft is final.
4. **Score it** against the calibration table (see main SKILL.md) using the Fit rubric below, and tag it.
5. **Move to the next story** or stop — there's no fixed number required; 6-10 well-differentiated stories is a reasonable target, but don't pad the bank with filler just to hit a count.

Keep the tone here closer to Practice mode than Debrief mode — this is generative and iterative, not retrospective, so direct feedback while drafting is fine and useful.

## Story write-up template

```
### [Short story title]

**Situation:** 1-2 sentences of context.
**Scope:** [product line/segment | cross-product/company-level]
**The call/bet:** What was decided, and what a different reasonable person might have done instead.
**Stakeholders navigated:** Who was aligned or in conflict, and at what level.
**Outcome:** Result, with a number if available.
**At larger scale:** What you'd do differently or bigger, if pushed.

**Fit:** [Strong Fit | Workable | Stretch | Gap]
**Proves:** [Senior | Principal] — [which calibration dimension(s): Scope / Ambiguity / Influence / Evidence / Stakeholder handling]
**Best for:** [question types this answers well, e.g. "cross-functional conflict," "biggest bet," "failure/what would you change"]
```

## Fit scoring (against the calibration table in the main SKILL.md)

- **Strong Fit** — clearly clears the target level's bar on scope, ambiguity, and influence; outcome is concrete; the "why this call" is sharp.
- **Workable** — clears the bar on most dimensions but is thin on one (e.g., good scope and outcome, but the strategic bet isn't sharply named).
- **Stretch** — genuinely belongs to the level below the target, but can be reframed by naming what the person would do differently at the larger scope. Flag it as a Stretch honestly rather than inflating the fit rating.
- **Gap** — doesn't fit the target level at all and shouldn't be forced; better to acknowledge the gap than distort the story.

Be honest about Stretch and Gap ratings — the point of the bank is surfacing real gaps before an interview, not inflating everything to Strong Fit.

## Gap-finding

Once several stories are scored, periodically summarize coverage: which calibration dimensions (Scope, Ambiguity, Influence, Evidence, Stakeholder handling) have Strong Fit stories and which are thin or missing, for each target level. Call out gaps plainly — e.g., "you have three Strong Fit stories for Senior-level execution, but nothing rated Strong Fit for Principal-level 'sets the tiebreaker' — worth thinking about whether a story exists that hasn't come up yet, or whether that's a real experience gap worth naming honestly in-interview rather than forcing."

## Matching stories to a specific interview

Given a job description or company context (pull via the Research entry point if needed), suggest which banked stories are the strongest fits for what that panel will likely probe, and flag if the bank's coverage is thin for that particular role's apparent emphasis (e.g., a JD that emphasizes cross-functional launches at scale wants Influence-dimension Strong Fit stories specifically).

## Staleness

Stories don't stay accurate forever — remind the user (lightly, not every session) that fit ratings should be revisited periodically, especially before a new interview loop, rather than trusted indefinitely from when they were first scored.

## Output format: summarizing the bank

When the user wants an overview of the bank rather than help drafting a new story, output a table, not prose:

| Story Title | Description | Level / Fit | Status |
|---|---|---|---|
| Short, memorable title | 1-2 sentences: situation + the call + headline outcome | e.g. "Principal — Strong Fit" | "Ready" or "Needs work," with the specific gap named (not just the label) |

Rules for this table:
- **Description is a compressed summary, not the full write-up** — 1-2 sentences, enough to jog memory and let the user pick the right story for a question, not enough to replace the full entry.
- **Status must name the actual gap**, not just "needs work" — e.g. "soft adoption numbers need real figures," not "needs more detail." A vague status defeats the point of the table.
- **Don't inflate Level/Fit in the summary table** — if a story was scored Workable or Stretch during elicitation, it stays that way here; the table is for honest triage, not a highlight reel.
- If the bank as a whole is skewed (e.g. everything clusters on one or two calibration dimensions), say so once below the table — that's often more useful than the table itself for deciding what story to build next.

## Where this bank lives

This skill doesn't have its own persistent storage — the bank is just a markdown file (or a section the user maintains) that lives in their notes or repo. Offer to output the current state of the bank as a file the user can save and bring back into future sessions; without that, none of this persists between conversations.
