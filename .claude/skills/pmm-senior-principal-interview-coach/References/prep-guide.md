# Prep Intake, Guide and Handoff

Three connected modes: `/prep` (intake and triage), the prep guide (one file per company), and `/handoff` (a carry-forward summary).

## Intake (one batch)

Ask once, in one message. Allow "other" on every item.

1. Company.
2. Job link.
3. Interviewer LinkedIn links, if known.
4. The stage and what it will test.
5. Hours until the interview.
6. Optional: your own take on the company in about 3 lines.

Then read the job link and each profile yourself. If one will not open on the first try, say so at once and ask for a paste (working rule 7). Do not retry several times. Derive the role and level from the posting and confirm the level with the existing target-level rule. Ask only for what you could not extract.

If the user gave their own take, critique it before building on it (working rule 5).

## Triage by hours left

Tiers borrowed from the generic `interview-coach`:

- **Under 24 hours: surgical.** Fix the biggest gaps only. Put one `/drill` block and the questions to ask first. Skip a full landscape scan.
- **2 to 3 days: structured.** Add `/crash-course` on the product, `/analysts`, interviewer prep and story-bank matching, then drills.
- **A week or more: comprehensive.** Everything above, plus repeated drills and a full guide.

Output a short prioritized checklist. Each line names the command to run and roughly what it will produce. Do not run the checklist unasked.

## The prep guide

One file per company, saved as `~/Documents/interview-prep/<company-slug>/<company-slug>-prep-guide.md`. Tell the user the full path. Fixed sections:

1. Role and stage
2. Value props
3. Competitors
4. Analyst view
5. How it works
6. Interviewers and what they will probe
7. Final questions to ask
8. Assumptions to confirm

Fill each section from the mode that owns it: research for competitors and value props, `/analysts` for the analyst view, `/crash-course` for how it works. A section that has not been researched says "not yet researched". Never fill a section with guesses.

### Final questions

Draft 4 or 5 questions, then critique them and trim. Each question should do at least one of these:

- Show you did the research by naming something specific.
- Probe what success looks like in the role.
- Reveal the interviewer's own view.
- Help you judge whether the role fits you.

Cut any question that is generic or answered on the company website.

## Handoff

`/handoff` writes a one-page summary the user can paste into another chat or session: the company and role, what is confirmed (with sources), the user's own view, decisions made, open items, and the next step. Save it as `<company-slug>-handoff.md` in the same folder. After the interview, the user adds what the interviewer said and the guide is adjusted.

## Out of scope

Resume, LinkedIn profile and salary work (see the scope in the main `SKILL.md`).
