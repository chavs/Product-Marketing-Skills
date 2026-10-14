# Analyst Landscape Scan

A scan of what the main analyst firms say about a company or a category. It reports what was actually read and what was not.

## Scope

- Firms: Gartner, Forrester, IDC, SACR, and others that matter for the category (for example KuppingerCole, Frost and Sullivan, G2 Grid).
- Dates: reports from 2023 onward only. Note older ones once as out of range.

## Steps

1. **Check what the user already has.** Look in uploaded files, project files and the session first. Never say a report is unavailable before checking.
2. **Find the reports.** For each firm, search for the specific report: title, firm, market category, publish date or quarter.
3. **Set a status for each.** Use exactly one:
   - `read in full`: the user supplied it, or it was freely available and read end to end.
   - `public summary only`: only an abstract, press release or vendor excerpt was read.
   - `paywalled, not read`: found but not opened.
4. **Handle paywalled reports.** Show the user what was found, with a link. Ask for the report as pasted text, PDF or Markdown if they have access. Ask on the first failed fetch (working rule 7). If they cannot get it, fall back to secondary signals tagged `[Inferred]` or `[Estimated]`, never `[Confirmed]`. A vendor press release shows only the flattering placement. Once the user supplies the real report, treat it as `[Confirmed]` and take placements and category definitions from it.
5. **Record vendor position.** Report a vendor's position (leader, challenger and so on) only if it is visible in what was read. Otherwise write "position not visible in what was read".
6. **Add cautions.** Firms draw category lines differently, so the same vendor can sit in different categories. A placement is not a measure of capability. A report excerpt the vendor republishes is advocacy, so read it that way.

G2 profile pages are usually open without a login. Check before assuming a paywall applies.

## Output

A table with these columns: firm, report and date, status, vendor position, caution. Then one short paragraph on how the firms' category definitions differ, if they do.

End with a **Coverage** block: reports read in full, reports seen only in summary, reports not read, and what the user could upload to close the gaps. Never present a sample as a full sweep.

## Tagging

`[Confirmed]` / `[Estimated]` / `[Inferred]` on every claim, with the source link inline. Reddit and Hacker News are excluded.

## Where it goes

Short results stay in the chat. If the user wants to keep one, add it to the "Analyst view" section of the prep guide (see `prep-guide.md`).

## Out of scope

Drafting a recommendation from the analyst view. For a take-home brief built around one analyst report, see `market-landscape-research.md` in the case-study skill.
