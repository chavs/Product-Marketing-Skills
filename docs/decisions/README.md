# Decision log

This folder records the design decisions for the three PMM interview skills in this repo, and why each was taken. It exists so decisions survive Claude Code compaction, recycled worktrees and new sessions. It is hand-written documentation and is tracked in git.

## How to use it

1. Read this index first. Open an entry only when you need its reasoning.
2. When a decision is taken, add an entry before the session ends. Copy `TEMPLATE.md`, use the next number, and add a row to the table below.
3. Never rewrite an accepted decision. If it changes, write a new entry and mark the old one "Superseded by NNNN".
4. Keep the open list below current. Remove an item when it is decided or verified.

Status values: Accepted, Proposed, Deferred, Superseded by NNNN. A note in brackets, such as "import unverified", means it is decided but not yet checked in practice.

## Index

| ID | Date | Area | Decision | Why, in short | Status |
|---|---|---|---|---|---|
| [0001](0001-separate-live-assistant-from-coach.md) | 2026-08-30 | skills-architecture | Separate the live assistant from the coach. Move competitive intelligence out of the coach. | Live (seconds per turn) and prep (minutes per turn) need opposite assumptions. One method, one owner. | Accepted |
| [0002](0002-live-assistant-returns-facts-not-answers.md) | 2026-08-30 | live-assistant | Return tagged, sourced facts only. No drafted answers. | The candidate speaks in their own words. Answer help is the coach's job. | Accepted |
| [0003](0003-authorship-stays-with-the-candidate.md) | 2026-08-30 | skills-architecture | Authorship stays with the candidate. Claude retrieves and critiques only. | They defend the material live or after submitting it. | Accepted |
| [0004](0004-live-competitive-research-method.md) | 2026-08-30 | live-assistant | Speed-adapted competitive research. Command `/competitive-intel`. | A live turn has seconds. Tags keep fast answers honest. | Accepted |
| [0005](0005-customer-voice-own-entry-point.md) | 2026-08-30 | live-assistant | Customer voice is its own entry point. Command `/customer-voice`. | Useful with no competitor in play. Different source ranking. | Accepted |
| [0006](0006-value-proposition-test-in-live-assistant.md) | 2026-08-30 | live-assistant | The Value Proposition Test lives in the live assistant. Command `/value-proposition-test`. | Used during a real exercise. The user overrode the pre-built-research assumption. | Accepted |
| [0007](0007-no-hardcoded-time-research-gets-half.md) | 2026-09-01 | live-assistant | No hardcoded time. Research gets half of the stated time. | Keeps the no-number rule. Simple to apply. | Accepted |
| [0008](0008-value-proposition-test-four-phases.md) | 2026-09-01 | live-assistant | Four phases: intake, autonomous research, candidate draft, critique. | A dry run took about an hour against 20 minutes. Scattered questions and a crowded chat. | Accepted |
| [0009](0009-phase-a-intake-questions.md) | 2026-09-01 | live-assistant | Phase A: four questions, once, only what the brief cannot answer. Then a recap. | Research runs uninterrupted, so a wrong answer wastes the budget. | Accepted |
| [0010](0010-adjacent-capability-anchor.md) | 2026-09-01 | live-assistant | Anchor research on the closest real capability. | A fictional feature has no real customers to quote. | Accepted |
| [0011](0011-research-output-local-markdown-file.md) | 2026-09-01 | live-assistant | Research goes to a local markdown file, not chat or Google Drive. | Chat was crowded. No network round-trip. | Accepted (folder changed by 0020) |
| [0012](0012-draft-components-and-document-order.md) | 2026-09-01 | live-assistant | Four-part draft at the top of the document. | The candidate needs their own answer first. The boundaries list is authorship. | Accepted |
| [0013](0013-phase-d-fixed-order.md) | 2026-09-01 | live-assistant | Phase D critique runs in a fixed seven-step order. | Same path every time. Correctness before craft. | Accepted |
| [0014](0014-customer-voice-evidence-rules.md) | 2026-09-01 | live-assistant | Attribution sets the tag. Relevance is a separate check. Practitioner content first. | An unnamed-customer claim was tagged Confirmed. | Accepted |
| [0015](0015-skills-under-claude-skills.md) | 2026-09-01 | skills-architecture | Skills live under `.claude/skills/`. | Claude Code does not find skills at the repo root. | Accepted |
| [0016](0016-case-study-skill-for-async-takehomes.md) | 2026-09-14 | skills-architecture | A third skill for async take-home case studies. | Deadline-bound but untimed, so research can run overnight. | Accepted |
| [0017](0017-adversarial-stress-test-tracks.md) | 2026-09-14 | case-study | A dedicated adversarial pass against the candidate's hypothesis. | Neutral tracks still lean toward confirming. It changed 2 of 5 verdicts. | Accepted |
| [0018](0018-round-1-scope-claude-code-first.md) | 2026-10-14 | process | Round 1 is Claude Code only. claude.ai is deferred. | The user said to fix Claude Code first. Different surface and limits. | Accepted |
| [0019](0019-shared-working-rules.md) | 2026-10-14 | working-rules | One rules file, loaded through `CLAUDE.md`. | The same eight corrections kept recurring. Instructions were empty. | Accepted (import unverified) |
| [0020](0020-outputs-outside-the-repo.md) | 2026-10-14 | process | Generated files live outside the repo. | Recycled worktrees delete untracked files. | Accepted |
| [0021](0021-case-study-skill-upgrades.md) | 2026-10-14 | case-study | Close six case-study gaps. Fixed, critique-only checks. | The doc's take-home checklist, compared with what the skill covered. | Accepted |
| [0022](0022-answer-first-spoken-drill.md) | 2026-10-14 | coach | An answer-first spoken drill, with the Format check first. | Four sources marked down format while content was fine. | Accepted (not run end to end) |
| [0023](0023-coach-prep-crash-course-analysts.md) | 2026-10-14 | coach | Add prep, handoff, crash course and analyst scan. No merge of the generic coach. | The most frequent workflows with no skill. The merge was not selected. | Accepted (not run end to end) |
| [0024](0024-real-slash-commands.md) | 2026-10-14 | commands-and-tooling | 17 slash-command wrappers in `.claude/commands/`. | Commands typed inside a SKILL.md are not slash commands. | Accepted (autocomplete unverified) |
| [0025](0025-skill-description-length.md) | 2026-10-14 | commands-and-tooling | Keep descriptions inside the skill-list limit. | The coach was cut at 1,536. The live assistant shows as only its title. | Coach accepted. Others Proposed. |
| [0026](0026-decision-log.md) | 2026-10-14 | process | Keep this decision log. | Do not rely on compaction. | Accepted |

## Open decisions and pending checks

1. Trim the live assistant (1,341 characters) and the case-study skill (1,336) to about 900 each. Proposed in 0025. Waiting for the user's answer.
2. Copy the gitignored `case-study-work/` scratch folder from the DataDome worktree to the interview-prep folder. Asked in 0020. No answer yet.
3. Choose a model for each mode, if any. The mechanism exists (0024). None chosen.
4. Verify in a fresh Claude Code session: typed commands autocomplete (0024), the `CLAUDE.md` `@` import loads (0019), and `/drill`, `/prep`, `/crash-course` and `/analysts` run end to end (0022, 0023).
5. Decide whether `CLAUDE.md` should import this index so every session sees it (0026).
6. Possible future splits, not acted on: move Phase A of the Value Proposition Test to the coach, and make its critique phase its own skill (0008).
7. The deferred claude.ai project (0018): trim descriptions to 1,024 characters, a packaging script and upload zips, upload to claude.ai, paste the rules into the Project instructions, claude.ai fallbacks for missing background agents and local folders, and the decision on merging the generic `interview-coach`.
8. Offer evaluation, an interview deck builder and the target-company tracker. Each needs its own design round (0018).

## Environment notes

- The GitHub CLI (`gh`) was not installed on 2026-10-14. Open a pull request with the compare link: `https://github.com/chavs/Product-Marketing-Skills/compare/main...<branch>?expand=1`.
- Pull merged changes in GitHub Desktop, in `C:\Users\saine\Documents\GitHub\Product-Marketing-Skills`, on `main`. Do not pull in anything under `.claude\worktrees\`. Those folders are temporary Claude Code worktrees and get recycled.
- Pull request history: #1 b55ee32 (live assistant), #2 e36845a (restructure, skills moved), #3 5587362 (output mechanism), #4 87532ce, eb442e2 and 43aa1c5 (case-study skill), #5 2c21a73 to 7cd2fea (Round 1).

## Related records

- Memory notes, in `C:\Users\saine\.claude\projects\C--Users-saine-Documents-GitHub-Product-Marketing-Skills\memory\`: `project-pmm-skills-architecture`, `project-claude-ai-publishing-deferred`, `project-datadome-pmm-case-study`, `feedback-hypothesis-stress-testing`, `feedback-live-assistant-interaction-design`, `feedback-research-claim-verification`, `user-pmm-candidate-building-own-tooling`.
- The learnings document, not in the repo: `C:\Users\saine\Downloads\interview-project-learnings.md`.
- Generated research, not in the repo: `C:\Users\saine\Documents\interview-prep\`.

## Not recorded here

- Decisions made before 2026-08-30, when the coach skill was first built in a claude.ai chat (calibration bar, scoring rubric, tone settings, story bank).
- The practice answers for the invented Cockroach Labs brief (so-what, value propositions, headline, persona order). They are in `value-proposition-test-notes.md` in the interview-prep folder.
