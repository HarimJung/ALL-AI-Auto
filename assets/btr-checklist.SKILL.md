---
name: btr-checklist
description: Build a preparation checklist for a country's next Biennial Transparency Report (BTR) under the Enhanced Transparency Framework of the Paris Agreement, with every item and every date traced to a UNFCCC decision paragraph. Use when someone asks what a country must submit in its BTR, by when, and what flexibility or discretion applies.
---

# BTR Checklist

One country situation in, one checklist out. Each line names the decision and paragraph it comes from. A date that no opened document states is marked unverified.

**Inputs**
- `country`: optional. Matters only for whether it is a least developed country (LDC) or small island developing State (SIDS), and whether it is a developing country Party applying flexibility.
- `report`: which BTR, e.g. the second.

## Why this exists

BTR questions get answered from slides and blog posts that mix the old biennial update reports with the new framework, and that state deadlines without saying where they come from. A deadline in a brief needs a decision number and a paragraph, or it needs the word unverified next to it.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Decision 1/CP.21, FCCC/CP/2015/10/Add.1 | Para 90, how often Parties report under Article 13 | `https://unfccc.int/resource/docs/2015/cop21/eng/10a01.pdf` |
| Decision 18/CMA.1 and its annex (the MPGs), FCCC/PA/CMA/2018/3/Add.2 | Decision para 3 (first BTR date), para 4 (LDC and SIDS discretion). MPG paras 5 and 6 (flexibility), para 10 (what a BTR contains), paras 11 to 16 (format and submission), para 58 (latest inventory year), para 198 (late submission) | `https://unfccc.int/sites/default/files/resource/CMA2018_03a02E.pdf` |
| UNFCCC page for the report in question | The secretariat's statement of the due date and the list of submissions | `https://unfccc.int/second-biennial-transparency-reports` (for BTR2) |
| Paris Agreement, Article 13 | The paragraphs 7 to 10 the decisions refer to. The Agreement is the annex to decision 1/CP.21 | Same file as decision 1/CP.21 |

The UNFCCC site often serves a bot check instead of the page. The PDFs usually open with a plain download. If a page does not open, say so and do not fill it from memory or a search summary.

## Steps

1. Open both decision PDFs. Copy each document symbol and its date from the first page.
2. Find the due date. Quote decision 18/CMA.1 para 3 for the first BTR and decision 1/CP.21 para 90 for the frequency.
3. For a later BTR, open the UNFCCC page for that report and quote its date. If the page does not open, write the date as derived from the two paragraphs above and mark it `UNVERIFIED: not stated in an opened document`.
4. Build the checklist from MPG para 10, one line per sub-paragraph, keeping the decision's own verb. "Shall" is required. "Should" is expected. Do not turn a "should" into a must.
5. Add the format and submission lines from MPG paras 12, 15 and 16, the inventory year rule from para 58, and the LDC and SIDS line from decision para 4 and MPG para 11.
6. If the country is a developing country Party, add the flexibility rule from MPG para 6 in one line.

## Answer layout

```
<report> · sources read <today's date>
Due: <date>   "<quoted line>"   <decision>, para <n>     (or UNVERIFIED and why)
Frequency:    "<quoted line>"   decision 1/CP.21, para 90

| # | Item | Shall or should | Source |
|---|---|---|---|
| 1 | <item in the decision's words> | shall | MPG para 10(a) |
| ... | | | |

Not covered: <anything asked about that the opened documents do not state>
```

## Rules

- **A date with no paragraph behind it is `UNVERIFIED`. Never give a deadline from memory, a news item or a search result summary as confirmed.**
- Quote the decision's words for every item. Shorten only by cutting, never by paraphrase that changes "shall" or "should".
- Keep BTRs apart from national communications and from biennial update reports. They are different reports under different decisions.
- If the question asks about a tool, a template or a table the opened documents do not describe, write `NOT IN SOURCE` and name the document that would hold it, if known.
- Never invent a number of tables, pages or chapters.

## Copy-paste prompt (works in any assistant)

> Make me a checklist for <country>'s <first/second> Biennial Transparency Report under the Paris Agreement. Use only UNFCCC decisions: decision 1/CP.21 paragraph 90, decision 18/CMA.1 and its annex of modalities, procedures and guidelines (paragraph 10 for contents), and the UNFCCC page for that report. For each item, give the decision paragraph and say whether the text says "shall" or "should". For the due date, quote the paragraph or page that states it. If no document you opened states the date, write UNVERIFIED next to it. Do not answer from memory.

## Running it as code

Copies of the two decision PDFs used for the recorded test, with SHA-256, are in `data/anchors/skills/btr-checklist/` in the claude-for-sdg repository. The UNFCCC page for BTR2 could not be opened when this skill was written.
