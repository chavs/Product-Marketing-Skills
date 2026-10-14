# PMM Case Study Assistant

A Claude skill for an asynchronous, take-home PMM case study — a written brief with a submission deadline, not scored live in the room. Not for prep before an interview with no specific brief (see `pmm-senior-principal-interview-coach`), and not for a live, timed case exercise during an actual interview (see `live-job-interview-assistant`).

## What it does

- **Batched intake** — reads the brief and extracts the task list with sub-asks, grading criteria, medium and length limit instead of asking for them. Proposes a source order for the candidate to confirm. Asks only what the brief cannot answer, in one pass, including a freshness check if a newer version of the brief replaces an earlier one.
- **Unattended, multi-track background research** — one foundational track establishing the target company's own current value proposition/positioning/messaging (across every capability area the brief touches, not just the newest one), plus one research track per distinct task in the brief (commonly: an analyst-report-driven roadmap ask, a competitive/user-driven roadmap ask, and a content/messaging review ask). If the candidate shares a working hypothesis, a dedicated stress-test track actively tries to disprove it (not just report whatever confirming evidence surfaces incidentally), and a competitive-response-simulation pass surfaces how named competitors would push back on the target company's own position. All tracks write sourced, tagged findings into one shared local markdown file, and can run overnight since there's no live time pressure. If the deliverable is writing in a particular voice, a voice-calibration track measures real samples from the same medium. Every track ends with a Coverage block (read in full, skimmed, unreachable). Files are saved to `~/Documents/interview-prep/<company-slug>/`.
- **Candidate's draft, unassisted** — the candidate's own answers go at the top of the research file once drafted; Claude never authors the roadmap recommendation, the advocacy pitch, or the content critique itself.
- **Optional critique loop** — critique only, never rewrites. Six checks in a fixed order: claims against research, grading-criteria coverage, cross-section consistency, a scripted length count, plain-writing flags, and a draft AI-use note. Can hand off to the coach skill's rubric for Senior/Principal-level scoring of the write-up.

## Usage

Trigger with `/case-study [company]` (or `/case-study check` once a draft exists), or naturally — "I have a take-home case study from [company], can you help me research it overnight." Share the brief (file or pasted text) if it hasn't been shared yet.

## Files

- [`SKILL.md`](./SKILL.md) — full skill definition, phases, scope, commands
- [`References/value-prop-positioning-baseline.md`](./References/value-prop-positioning-baseline.md) — the foundational Track 0 method
- [`References/market-landscape-research.md`](./References/market-landscape-research.md) — analyst-report-driven roadmap research method
- [`References/competitive-differentiation-research.md`](./References/competitive-differentiation-research.md) — G2/website competitive research method
- [`References/content-teardown-research.md`](./References/content-teardown-research.md) — content/messaging review research method
- [`References/hypothesis-stress-testing.md`](./References/hypothesis-stress-testing.md) — actively falsifying a candidate's stated working hypothesis
- [`References/competitive-response-simulation.md`](./References/competitive-response-simulation.md) — simulating named competitors' pushback on the target company's stated position
- [`References/voice-calibration.md`](./References/voice-calibration.md) — measuring real samples when the deliverable must match a company's voice
- [`References/submission-checks.md`](./References/submission-checks.md) — the Phase D checks: criteria coverage, consistency, length, plain-writing flags, AI-use note
