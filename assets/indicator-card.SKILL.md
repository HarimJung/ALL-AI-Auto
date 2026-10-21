---
name: indicator-card
description: Build a one-page, citable card for any SDG indicator and country. Use when someone gives an SDG indicator code (like 6.1.1) and a country and wants the definition, the latest official value, the custodian agency and the methodological catch, each line traced to its official source.
---

# SDG Indicator Card

Two inputs, one card. Every line on the card says where it came from.

**Inputs**
- `code`: an indicator code from the global SDG indicator framework, e.g. `6.1.1`
- `country`: a country name as the SDG Global Database writes it, e.g. `Ghana`

## Why this exists

An assistant asked for an indicator value from memory gives a number, a rough year and a hedge. In a recorded test without this skill, Claude said Ghana's 6.1.1 figure was "about 38%" for "around 2022". The SDG Global Database read on 20 October 2026 has 42.9 percent for 2024, estimated. For Kenya it said "somewhere around 30–40%". The database has no Kenya row for the series `SH_H2O_SAFE` at all.

## Sources (use these and nothing else)

| What | Where | Cite as |
|---|---|---|
| Definition, custodian, method | `https://unstats.un.org/sdgs/metadata/files/Metadata-<CC-TT-II>.pdf` (6.1.1 becomes `06-01-01`) | `metadata <code> §<section>, last updated <date>` |
| Series list for the code | `https://unstats.un.org/sdgapi/v1/sdg/Indicator/List` | `SDG API, Indicator/List` |
| Country code | `https://unstats.un.org/sdgapi/v1/sdg/GeoArea/List` | `SDG API, GeoArea/List` |
| Values | `https://unstats.un.org/sdgapi/v1/sdg/Series/Data?seriesCode=<SERIES>&areaCode=<M49>&pageSize=1000` | `SDG Global Database, <SERIES>, <year>` |

## Steps

1. Open the metadata PDF. Copy the **last updated** date from the page header.
2. Copy the custodian agencies from **§0.g** and the first sentence of the definition from **§2.a**, word for word.
3. Read **§4.c** (computation), **§4.f** (missing values) and **§4.g** (aggregation). Pick the one rule a reader is most likely to get wrong. Quote it word for word with its §.
4. Get the series codes for the indicator, then the country's rows for each series.
5. Use the total row (`ALLAREA`, `BOTHSEX`, `ALLAGE` where those dimensions exist). Report the latest year, the value, the unit and the `Nature` attribute (estimated, modelled, country data).

## Card layout

```
<code> · <official indicator name>
<country> · <value><unit> (<year>, <nature>)        SDG Global Database, <SERIES>
Definition   "<first sentence of §2.a>"             metadata §2.a, <last updated>
Custodian    <agencies>                              metadata §0.g
The catch    "<quoted rule>"                         metadata §4.x
Source       <source field of the data row>
```

## Rules

- **No value in the database: write `NOT IN SOURCE` and say which series was empty.** Never fill it from a news story, a report or a guess.
- Never average, sum or convert values. If the method says how a figure is built, quote that sentence instead.
- If an indicator has several series, list each series code. Do not choose one silently.
- Take series only from the entry for the exact code in `Indicator/List`. A series filed under a neighbouring code, such as `SH_SAN_HNDWSH` under 6.2.1, is not a series of 6.1.1.
- Quotes are word for word. If the PDF text is broken by extraction (`t aken`), fix only the spacing.
- Keep the `Nature` label. An estimated or modelled value is not the same as country-reported data.

## Copy-paste prompt (works in any assistant)

> For SDG indicator <code> in <country>, take the value only from the UN SDG Global Database (unstats.un.org/sdgapi) and the definition and custodian only from the official metadata PDF (unstats.un.org/sdgs/metadata). Quote the definition word for word with its section number. Give the year, the unit and whether the value is estimated, modelled or country data. If the database has no row for this country, write NOT IN SOURCE and name the empty series. If you can't open these pages now, say so and give me the links instead of a number. Do not answer from memory.

## Running it as code

`engines/ai/indicator_card.py <code> <country>` in the claude-for-sdg repository does steps 1 to 5 and keeps a copy of every source it read, with its SHA-256.
