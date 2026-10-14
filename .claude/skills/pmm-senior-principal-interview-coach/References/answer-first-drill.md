# Answer-First Drill

A timed, spoken drill for one problem: the so-what has to land first. The same note came back from four directions in real interviews: "land the so-what before the detail", "concise and precise", marked down on format while content was fine, and the strongest point buried behind a caveat. This drill trains that one skill.

## Setup (once per session)

- Confirm the target level (Senior or Principal). The existing rule applies.
- Confirm tone. The existing rule applies.
- Confirm the time per answer. Default is 90 seconds. The user can set another one, for example `/drill 60`. The word target is about seconds x 2.2, which is roughly 130 words a minute. At 90 seconds that is about 200 words.
- Say plainly: the user speaks the answer (voice dictation works well) and Claude reads the transcript. Claude sees text only. It cannot judge tone, pace or pauses.

## The loop

1. Ask one question. Calibrate it to the confirmed level. Draw it from the user's story bank, the upcoming role, or the question type they named. Give no hints.
2. The user answers within the time they set.
3. Score the Format check first (below), then the content rubric.
4. Ask for one redraft that fixes the format failures. Rescore it.
5. Append one row to the drill log. Ask whether to go again.

## Format check (always first)

1. **First sentence.** Quote it. Does it state the answer or the so-what? Pass or fail. Context and caveats do not count as an answer.
2. **Buried point.** Name the strongest point in the answer and say where it sits. Flag it if it comes after a caveat, a definition or background.
3. **Length.** Count the words. Compare with the target. Give the difference.
4. **Hedges and fillers.** Count and quote the ones in the transcript: "I think", "kind of", "sort of", "basically", "maybe", "just", "hopefully", "a bit". This is the confidence signal Claude can read in text.

## Then the content rubric

Use the 5 dimensions in the main `SKILL.md`. Show them second, so format is never confused with content. An answer can be strong on content and still fail on format. Say so when that happens.

## Tone

Tone follows the session setting. `brutal` states each format failure and stops, with no fix. `tough_but_fair` gives the failure and one concrete fix. `warm` leads with what worked.

## Drill log

Append one row per attempt to `drill-log.md` in `~/Documents/interview-prep/<company-slug>/`, or in `~/Documents/interview-prep/general/` when there is no company. Columns: date, question type, seconds, first sentence pass or fail, words vs target, hedge count, redraft pass or fail. Create the file with a header row if it is missing. Tell the user the full path. At the start of a later session, read the last few rows and say whether the first-sentence pass rate and the hedge count are moving.

## Out of scope

Writing the answer for the user. Giving a model answer unless the user asks for one after the redraft.
