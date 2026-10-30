---
name: latest-edition
description: Answer any request for a figure from a UN flagship report (HDI, SDG Report, World Population Prospects, SOFI, World Health Statistics and the like) from the latest edition only. Use when someone asks for a number "from the latest report", or names a report without an edition. Names the edition and its publication date, reads the publisher's current file, and refuses to give a number from memory.
---

# UN Latest Edition

One question in, one answer that says which edition it came from. A figure without an edition is not an answer.

**Inputs**
- `report`: a UN flagship report, e.g. `Human Development Report`
- `figure`: what is wanted, e.g. `HDI for Ghana`

## Why this exists

Flagship reports come out every year or two, and each edition recomputes past years. An assistant answering from memory tends to give the numbers of the edition it saw in training and call them current. In a recorded test, Claude without this skill named the 2025 Human Development Report and quoted the 2023/24 edition's Ghana figures.

## Sources (use these and nothing else)

The publisher's own page for the report, then the data file linked from that page. Start here:

| Report | Publisher | Where the edition is listed |
|---|---|---|
| Human Development Report | UNDP | `https://hdr.undp.org/data-center/documentation-and-downloads` |
| Sustainable Development Goals Report | UN DESA | `https://unstats.un.org/sdgs/report/<year>/` |
| World Population Prospects | UN DESA Population Division | `https://www.un.org/development/desa/pd/` |
| State of Food Security and Nutrition in the World | FAO, IFAD, UNICEF, WFP, WHO | `https://www.fao.org/publications/fao-flagship-publications/the-state-of-food-security-and-nutrition-in-the-world/en` |
| World Economic Situation and Prospects | UN DESA | `https://desapublications.un.org/publications/` |
| World Health Statistics | WHO | `https://www.who.int/data/gho/publications/world-health-statistics` |
| State of the World's Children | UNICEF | `https://www.unicef.org/reports/state-of-worlds-children` |
| Employment and Social Trends | ILO | `https://www.ilo.org/research-and-publications` |
| World Investment Report | UNCTAD | `https://unctad.org/topic/investment/world-investment-report` |
| State of the Global Climate | WMO | `https://wmo.int/publication-series/state-of-global-climate` |

For the HDI the data file is the composite indices time series CSV linked from the downloads page.
Do not hard-code the file name. It carries the edition in its prefix, so read it off the page you just
opened (checked on 2026-10-25: the file was named `HDR<YY>_Composite_indices_complete_time_series.csv`).
The value is in column `hdi_<year>`, the rank in `hdi_rank_<year>`.

## Steps

1. Open the publisher's page. Find the newest edition and its publication date. Copy the line that shows both, word for word.
2. Follow that page to the edition's data file or report. Do not use a file from another edition, even for older years. Editions recompute the past.
3. Read the figure from the file. Note the column or table and the row.
4. Answer in this order: edition, publication date, figure, where in the file, source URL, date you read it.

## Answer layout

```
<report> <edition> (published <date>, "<line from the publisher's page>")
<figure>: <value>                           <file>, <column or table>, <row>
Source: <URL> · read <today's date>
```

## Rules

- **Cannot open the page or the file: say "I can't check the current edition" and give the link. Do not give a number.**
- Never answer from memory, even with "about" or "I believe". A remembered figure is from an unknown edition.
- The edition year is not the publication year. The 2025 State of the Global Climate came out in 2026. Copy both as the page writes them.
- If you remember a different figure, say which edition you think it came from, then give the current one from the file.
- Do not mix editions in one table. If a reader needs a time series, take every year from the same file.

## Copy-paste prompt (works in any assistant)

> Before you give any figure from a UN report, tell me which edition it comes from and when that edition was published. Read the publisher's own page and the current data file first. If you can't open them now, say "I can't check the current edition" and give me the link instead of a number. Do not answer from memory.

## Running it as code

`engines/material/` in the claude-for-sdg repository keeps a copy of each publisher page with its SHA-256 and accepts an edition or a date only when it is written in the quoted sentence of that stored page.
