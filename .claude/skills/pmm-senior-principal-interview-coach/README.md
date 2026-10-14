# PMM Senior/Principal Interview Coach

A Claude skill that coaches candidates through Senior and Principal Product Marketing Manager (IC track) interview prep — company/competitive research, messaging and positioning practice, mock interviews, and answer scoring calibrated specifically to the Senior-to-Principal PMM IC band.

## What it does

- **Research** — company positioning, competitive landscape, and interviewer/panel background for a specific PMM interview
- **Practice** — mock interview questions calibrated to the target level's bar (Senior or Principal)
- **Score** — rates draft/live answers on 5 dimensions (Substance, Structure, Relevance, Credibility, Differentiation) against a Senior vs. Principal calibration table
- **Diagnose** — flags *why* an answer is scoring Mixed/Weak (e.g. "reads Senior when targeting Principal") and what to change, not just that something's off
- **Drill** — a timed, spoken, answer-first drill. The Format check (first sentence, buried point, length, hedges) comes before the content score, and each attempt is logged.
- **Prep and handoff** — one intake batch, triage by hours left, a per-company prep guide, and a one-page summary to carry into another session.
- **Technical crash course** — how a company's product works, one layer at a time, vendor docs first, gaps flagged.
- **Analyst landscape scan** — what Gartner, Forrester, IDC, SACR and others say (2023 onward), with a status per report and a Coverage block.
- **Debrief and story bank** — score a real past interview from a transcript, and build a bank of pre-scored real stories.

## Scope

**In scope:** Senior PMM and Principal PMM, individual-contributor track only — research, prep, mock questions, drills, answer scoring, post-interview debrief, and a story bank.

**Out of scope:** People-manager PMM tracks (Director/Head/VP Marketing), Junior/Associate PMM, non-PMM GTM roles, resume/LinkedIn optimization, salary negotiation, or outreach.

## Usage

Trigger this skill for any Senior/Principal PMM interview prep task, including partial requests like "help me research this company," "score this answer," or "what should I ask them." If the target level isn't stated, the skill asks whether you're prepping for Senior or Principal before scoring, since the two bars are evaluated differently.

In Claude Code the commands are real slash commands: `/prep`, `/handoff`, `/research`, `/crash-course`, `/analysts`, `/practice`, `/drill`, `/score`, `/debrief`, `/bank`, `/level`, `/tone` and `/bonus`. Generated guides, handoffs and drill logs are saved to `~/Documents/interview-prep/<company-slug>/`.

## Files

- [`SKILL.md`](./SKILL.md) — full skill definition: calibration bar, scoring rubric, root-cause diagnosis patterns, and workflow
- [`References/answer-first-drill.md`](./References/answer-first-drill.md) — the timed, spoken drill and the Format check
- [`References/prep-guide.md`](./References/prep-guide.md) — prep intake, triage, the per-company guide, and handoff
- [`References/technical-crash-course.md`](./References/technical-crash-course.md) — the layered product crash course
- [`References/analyst-landscape-scan.md`](./References/analyst-landscape-scan.md) — the analyst scan method
- [`References/post-interview-analysis.md`](./References/post-interview-analysis.md) — debrief of a real past interview
- [`References/story-bank.md`](./References/story-bank.md) — the persistent story bank
