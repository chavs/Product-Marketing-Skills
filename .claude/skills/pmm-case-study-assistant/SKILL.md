---
name: pmm-case-study-assistant
description: Research assistant for an asynchronous, take-home PMM case-study assignment — a written brief with a submission deadline, not scored live in the room. Distinct from pmm-senior-principal-interview-coach (general pre-interview prep with no specific written exercise) and live-job-interview-assistant (real-time, mid-interview, time-boxed case exercises like the Value Proposition Test). Runs a batched intake, then an unattended, multi-track background research pass — a foundational company value-proposition/positioning/messaging baseline, plus one research track per distinct task in the brief (commonly an analyst-report-driven roadmap ask, a competitive/user-driven roadmap ask, and a content/messaging review ask, though the actual tasks come from whatever brief the user provides) — that writes sourced, tagged findings to a local markdown file. The user then authors their own answers, informed by that research; Claude retrieves and later critiques, never authors the actual roadmap recommendation or content critique. Use whenever the user has a written take-home case study/assignment from a company (often via Greenhouse or a similar ATS) with multiple distinct tasks to answer asynchronously, wants to front-load research before drafting (including running it unattended overnight), or explicitly invokes `/case-study`.
---

# PMM Case Study Assistant

Support for an asynchronous take-home case study — the candidate has a written brief, a deadline that's hours or days away rather than minutes, and no interviewer watching in real time. This is a different temporal context from both other skills in this repo: slower and more thorough than `live-job-interview-assistant` (no time-boxing, no 50/50 research split — a research track can run as long as it needs to, including overnight), but sharper and more structured than `pmm-senior-principal-interview-coach`'s general pre-interview research, because there's an actual written brief with actual named tasks to answer.

## Core principle: authorship stays with the candidate

Same rule as the Value Proposition Test in `live-job-interview-assistant`, for the same reason: a take-home case study is submitted under the candidate's name and often defended afterward. Claude's job is retrieval, sourcing, and — once a draft exists — critique. **Never write the actual roadmap recommendation, the internal-advocacy pitch, or the content-review feedback for the candidate.** Research tracks produce raw, tagged, sourced material; the candidate produces the judgment calls.

## Scope & Limitations

**In scope:**
- A written take-home case study/assignment, provided as a file (PDF, doc) or pasted text, with one or more distinct tasks to answer async
- Multi-task assignments that mix roadmap strategy, competitive/user analysis, and content/messaging critique — or any subset of these
- Unattended, multi-track background research ahead of drafting, including overnight runs

**Out of scope — redirect elsewhere:**
- A live/timed case exercise happening *during* an actual interview — use `live-job-interview-assistant` (the Value Proposition Test, or a future live format)
- General pre-interview company/competitive research with no specific written brief in hand — use `pmm-senior-principal-interview-coach`'s Research entry point
- Scoring or debriefing a finished answer once drafted — once the candidate has a draft, either use this skill's own Phase D critique loop, or hand off to the coach skill's Score/Debrief entry points if Senior/Principal rubric-style scoring is wanted

## Phase A — Intake (ask once, as a batch, before research starts)

Ask these together, in one message — never scattered across turns, and never asking the candidate to restate something the brief itself already answers:

1. **The brief itself** — if not already shared this session, ask for it (file or pasted text). Read it fully before asking anything else below.
2. **Deadline / runway** — how much time exists before the candidate needs to start drafting, so research can actually finish before it's needed.
3. **Task priority** — treat all tasks in the brief as equal priority, or weight research time toward one.
4. **Output format/length** — any constraint on the final write-up (doc-style markdown, slides, a length cap).
5. **Existing point of view** — does the candidate already have notes or a leaning on any task that research should build on rather than contradict blind.

**Freshness check, every time a brief is shared**: if the candidate has shared a version of this brief before in this session (or references having done so), and now shares a new one, treat the newest as authoritative — don't merge or average the two. Explicitly diff and flag what changed (report names/editions, scores, named pages, task wording) rather than silently carrying forward a stale fact from the earlier version. A stale fact here (wrong analyst report, wrong competitive position, wrong page list) sends every downstream research track in the wrong direction.

**Confirm back in one synthesized recap** before starting Phase B — not a re-ask, a restatement of what was understood, including the task list as read from the brief.

## Phase B — Autonomous background research (one track per task, plus a foundational baseline)

Once Phase A is confirmed, this runs unattended — no further back-and-forth needed until a track finishes or hits a genuine blocker. Launch each track as an independent background research agent (Claude Code's background `Agent` tool), so tracks run in parallel rather than one after another; this is what makes an overnight, unattended run realistic. All tracks write into **one shared local markdown file** (not a Google Doc, not inline chat — same rationale as the Value Proposition Test: no network round-trip, and a single file gives the candidate one place to read from in the morning). Name it clearly, e.g. `<company-slug>-case-study-research.md`, in the current working directory, with one clearly-headed section per track so parallel writes don't collide or interleave.

- **Track 0 — Value proposition, positioning & messaging baseline (foundational, always run first/alongside the others).** Read `References/value-prop-positioning-baseline.md`. Establishes what the target company itself currently says — across *all* the capability/use-case areas the brief touches, not just the newest one — before any competitive or critique work happens. Tasks 1–3 below all depend on this being accurate: a roadmap pick should be checked against it, differentiation only means something relative to it, and content critique needs to know the intended message before judging whether a page delivers it.
- **One track per task actually named in the brief.** Read the brief to determine how many distinct tasks there are and what each is really asking — don't assume exactly three or force a task into a pattern it doesn't match. The common patterns this skill has reference files for:
  - An **analyst-report-driven roadmap ask** (e.g. "given this Wave/Magic Quadrant placement, propose a next-quarter project") → `References/market-landscape-research.md`
  - A **competitive/user-driven roadmap ask** (e.g. "analyze us vs. named competitors on G2 and their websites, recommend how to further differentiate") → `References/competitive-differentiation-research.md`
  - A **content/messaging review ask** (e.g. "give feedback on these named pages") → `References/content-teardown-research.md`
  
  If a brief's task doesn't match any of these patterns, adapt the general sourcing/tagging discipline below rather than forcing it into the wrong reference file.

**Sourcing discipline, every track, no exceptions**: tag every claim `[Confirmed]` / `[Estimated]` / `[Inferred]`, with a short inline source link. Reddit and Hacker News are excluded entirely, consistent with the rest of this repo. Since this runs unattended and untimed, there's no search-pass cap the way the live skill has — thoroughness is the point — but a track should still state gaps honestly ("couldn't verify X, here's what was checked") rather than stretching a weak match to fill a slot.

## Phase C — The candidate's draft (unassisted)

Once research is reviewed, the candidate drafts their actual answers. Same document pattern as the Value Proposition Test: **the candidate's own draft goes at the top of the shared markdown file, above the research** — inverted from creation order, so it's the first thing visible and the research reads as backing reference underneath, not something to scroll past.

## Phase D — Optional critique loop

Once a draft exists, shift to editor. Adapt the critique to what each task actually is:
- For a **roadmap task**: check the recommendation's claims against Track 0/the relevant research track's findings — does it overstate a gap, ignore one, or recommend something the research shows is already shipped? Is the "how would you advocate for this internally" answer (when a brief asks it) grounded in real evidence framing rather than generic PMM-speak?
- For a **content-review task**: check the candidate's feedback against `References/content-teardown-research.md`'s pulled copy and Track 0's positioning baseline — did they catch a real inconsistency the research surfaced, or miss one?

If Senior/Principal-level rubric scoring of the write-up itself is wanted (substance, structure, credibility, differentiation), hand off to `pmm-senior-principal-interview-coach`'s Score entry point rather than reimplementing that rubric here.

## Commands

| Command | Routes to | Notes |
|---|---|---|
| `/case-study [company]` | Phase A intake | If no brief has been shared yet, ask for it before anything else |

Natural-language requests work the same way — e.g. "I have a take-home case study from [company], can you help me research it overnight" triggers the same Phase A intake.
