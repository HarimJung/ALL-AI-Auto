---
name: redd-annex-presubmission-check
description: Check a draft REDD+ technical annex to a Biennial Transparency Report (BTR) before it leaves the ministry. The check finds gaps, open placeholders, broken cross-references and mismatches in the user's own document. It also flags timing risk, using the UNFCCC secretariat's finding on annexes that arrive late. Use when a national team or a transparency officer asks whether an annex is ready to send.
---

# REDD+ Annex Pre-submission Check

One draft annex goes in and one ready-or-not list comes out. Every flag points to a place in the user's document or to a quoted line from the UNFCCC report.

**Inputs**
- `annex`: required. The user's own draft technical annex, pasted or attached.
- `send_plan`: optional. The user's own words on when the team plans to send the annex and when review week falls.
- `btr_text`: optional. The main BTR text that goes with the annex. The check uses it to confirm that the two agree.

## Why this exists

The secretariat has reported that some annexes arrived just before review week. The LULUCF experts then had little time to prepare. The secretariat also expects more annexes in the second BTR cycle. An annex that is complete and easy to follow when it arrives gives the experts the time they need. A check before the file leaves the ministry catches gaps that would otherwise come up during review.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UNFCCC secretariat report on the technical analysis | The finding that some annexes came shortly before review week. The expectation of more annexes in the second BTR cycle. | `https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf` |
| The user's own draft annex | Everything the check says about content, structure and gaps | Supplied by the user |
| The user's BTR text, if given | Values and terms the annex must match | Supplied by the user |

The UN document link sometimes returns an error page or a login page instead of the PDF. If it does not open, say so in the answer. Do not quote it from memory or from a search summary. Run the document checks anyway and mark the timing line `SOURCE NOT OPENED`.

## Steps

- Open the UN document. Find this line and copy it exactly with its page: "In some cases, technical annexes were submitted shortly before the corresponding review weeks, leaving limited time for the secretariat and LULUCF experts to prepare for the technical analysis."
- Find this line too and copy it with its page: "The number of technical annexes submitted is likely to increase in the second cycle of BTRs as developing country Parties seek to demonstrate their REDD+ results"
- Read the whole annex before writing anything.
- List every section heading in the annex. If it has a table of contents, check that each listed section is there.
- Find every placeholder. Look for TBD, to be added, XX, empty tables, highlighted notes and comments left in the text.
- Find every cross-reference. Check that each table, figure, annex or section it points to exists in the document.
- Flag any passage that sends the reader to another document without naming that document.
- If `btr_text` is given, compare each value and term the annex shares with it. List each mismatch with both locations.
- If `send_plan` is given, compare it with the quoted finding. If the plan puts the annex close to review week, flag the timing risk and quote the line. Do not state a deadline. The opened sources do not set one.
- Sort the flags. Blockers come first, then fixes, then notes.

## Answer layout

```
Annex check · <annex title as written in the document>
Source opened: yes, or SOURCE NOT OPENED and why
Timing: <flag, or no plan given>   "<quoted line>"   UN document, page <n>

| Flag | Where in the annex | What is wrong | Fix |
|---|---|---|---|
| Blocker | <section or table> | <placeholder, broken reference or mismatch, quoted> | <one short action> |
| Fix | ... | ... | ... |
| Note | ... | ... | ... |

Ready to send: yes, or no with the count of blockers
Not checked: <anything asked that the opened sources do not cover>
```

## Rules

- **If the UN document does not open, say so. Never fill the quote or the page from memory.**
- Judge the annex only against itself, the BTR text the user gives and the quoted finding.
- The opened sources do not list what a REDD+ annex must contain. If the user asks about required content, write `NOT IN SOURCE`.
- Never invent a deadline, a review week date, a required section or a number of tables.
- Quote the user's document exactly when you cite a problem.
- Do not change technical values in the annex. Point to them and say what does not match.
- Keep the user's document inside this conversation. Do not send it to any other service or tool.
- Write in plain English with short sentences.

## Copy-paste prompt (works in any assistant)

> Check my draft REDD+ technical annex before we send it with our Biennial Transparency Report. Use only my annex, the BTR text I give you and the UNFCCC document at https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf. List every placeholder, every cross-reference that points to something missing, every passage that sends the reader to an unnamed document and every value that differs from my BTR text. Quote my text for each problem and say where it is. Sort the list into blockers, fixes and notes. If my send plan puts the annex close to review week, quote the UN document's line about annexes that arrived shortly before review weeks, with its page. If you cannot open the UN document, say so and do not quote it from memory. Do not invent deadlines or required sections.
