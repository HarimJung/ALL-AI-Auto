---
name: claim-check
description: Check a short draft (a brief, talking points, a donor note) sentence by sentence against the public UN documents it cites. Returns one table row per sentence with the source, the page or section, the line quoted word for word, and a verdict of SUPPORTED, NOT IN SOURCES or WRONG PAGE. Use before a draft with figures goes to a reviewer, a donor or a meeting.
---

# Claim Check

A draft and its sources in, one row per sentence out. A sentence passes only when a line in the source says the same thing on the page the draft cites.

**Inputs**
- `draft`: up to about 15 sentences. Number them if they are not numbered.
- `sources`: the documents the draft cites, as links or files. Official UN documents only (see below).

## Why this exists

A reviewer checks the number and the page. A checker that reads from memory, or matches only the numbers, passes a sentence whose figure sits on another page or belongs to another sentence. Long UN reports repeat the same percentages for different subjects, so a number found on the right page is not yet a match.

## Sources (use these and nothing else)

- The documents the user gives, if they are published by the UN system: documents with a UN symbol (A/..., E/..., FCCC/...) from `documents.un.org` or the publishing office, and reports on `un.org`, `unstats.un.org` or a UN agency's own site.
- Nothing else. Do not confirm a sentence from memory, from a news story or from a different edition of the same report.
- A source the user names but you cannot open is not a source. Every sentence that cites it gets `NOT IN SOURCES` with the note "could not open".

## Steps

1. Open each source. Copy its symbol or title and its date as printed on the first page.
2. Work out how the document numbers its pages. Use the page number printed on the page. Say so if it differs from the PDF page count.
3. For each sentence, go to the page or section it cites. Look for a line that states the same claim: the same figure, the same year, the same unit and the same subject.
4. If the cited page has no such line, search the whole source. If the line is on another page, the verdict is `WRONG PAGE` and the row gives the right page.
5. If no page in any source has the line, the verdict is `NOT IN SOURCES`. Quote the closest line, if there is one, so the reader sees what the source does say.
6. Fill one row per sentence. Never merge two sentences into one row.

## Verdicts

| Verdict | Means |
|---|---|
| SUPPORTED | A line on the cited page states the same figure, year, unit and subject |
| WRONG PAGE | The line exists in the source but not on the page the draft cites |
| NOT IN SOURCES | No line in any source states it. This includes a figure that differs from the source by any amount |

A number that matches but belongs to a different subject is not support. A share of adults with a bank account does not support the same share of people with electricity.

## Answer layout

```
Source: <symbol or title>, <date as printed> · <URL> · read <today's date>
Pages: <printed page numbers | PDF page numbers>

| # | Sentence | Source | Page/section | Quoted line | Verdict |
|---|---|---|---|---|---|
| 1 | <first words of the sentence> | <symbol> | p. <n>, para <n> | "<line, word for word>" | SUPPORTED |
| 2 | ... | ... | cited p. <n>, found p. <m> | "<line>" | WRONG PAGE |
| 3 | ... | ... | cited p. <n> | closest: "<line>" or none | NOT IN SOURCES |

<n> of <total> supported.
```

## Rules

- **Cannot open a source: say which one and mark its sentences NOT IN SOURCES with "could not open". Do not judge them from memory.**
- Quotes are word for word. If text extraction breaks spacing, fix only the spacing.
- Never round, convert or recompute a figure to make it match. A source that says 12% does not support 13%.
- Do not rewrite the draft. The table says what is wrong, the author fixes it.
- Do not add sources the draft did not cite. If a better source exists, say so in one line under the table.

## Copy-paste prompt (works in any assistant)

> Check my draft against its sources, one sentence at a time. For each sentence, open the source and the page it cites, and give me a table: sentence, source, page or section, the line from the source word for word, and a verdict. The verdict is SUPPORTED only if a line on the cited page states the same figure, year and subject. If the line is on another page, write WRONG PAGE and give the right page. If no line in the source says it, write NOT IN SOURCES and quote the closest line. Do not judge any sentence from memory. If you can't open a source, say so for every sentence that cites it.

## Demo

`demo/draft_brief.md` is a five-sentence draft citing the Secretary-General's SDG progress report A/81/93-E/2026/73 (8 June 2026). Two sentences carry planted errors, and the answer key is in the same file. A copy of the report and its SHA-256 are in `data/anchors/skills/claim-check/` in the claude-for-sdg repository.
