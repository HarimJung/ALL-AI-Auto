---
name: ref-year-check
description: Check a country comparison table (CSV or pasted rows) for one SDG indicator against the UN SDG Global Database, and flag every row whose value comes from a different reference year than the rest, or from a partial row such as urban only. Shows the database year of each value. Use before a table with "latest" values goes into a brief, a slide or a donor report.
---

# Reference Year Check

One table in, the same table back with a database year next to every value. A table that compares countries is only fair when every value is from the same year and the same population.

**Inputs**
- `table`: CSV or pasted rows with a country column and a value column. A year column is optional.
- `code`: the SDG indicator code the values claim to be, e.g. `6.1.1`. If the table does not say, ask.

## Why this exists

Comparison tables are built over weeks from several downloads. Each value was "latest" on the day it was copied, so one table can hold several years and still carry one year in its header. The database also holds partial rows. For some countries the only rows for a series are urban or rural, and a value copied from them reads like a national figure.

## Sources (use these and nothing else)

| What | Where |
|---|---|
| Series codes for the indicator | `https://unstats.un.org/sdgapi/v1/sdg/Indicator/List`, the entry for the exact code |
| Country codes | `https://unstats.un.org/sdgapi/v1/sdg/GeoArea/List` |
| Values with years | `https://unstats.un.org/sdgapi/v1/sdg/Series/Data?seriesCode=<SERIES>&areaCode=<M49>&pageSize=1000` |

Do not use an agency portal, a report table or memory to find a year. The years in this check come from `timePeriodStart` in the database rows.

## Steps

1. Find the series for the code. If there are several, ask which one the table uses, or check each and say so.
2. Get the M49 code for every country in the table, using the names as the database writes them.
3. Pull every row for each country. Keep the total rows (`ALLAREA`, `BOTHSEX`, `ALLAGE` where those dimensions exist). Note when a country has no total row.
4. For each table value, find the database year whose value matches it. Round the database value to the table's number of decimals before comparing, and never round the table value.
5. Take the year most rows share as the table's reference year. Flag every row that differs from it, every row that matches only a partial row, every row with no match and every empty cell.
6. For each flagged row, also give the database value for the reference year, if there is one, so the author can replace it.

## Answer layout

```
<code> · series <SERIES> · SDG Global Database, read <today's date>
Reference year: <year> (<n> of <total> rows)

| Country | Table value | Table year | Database year of that value | Row used | Database value for <ref year> | Flag |
|---|---|---|---|---|---|---|
| <country> | <v> | <y> | <year> | ALLAREA | <value> (<nature>) | OK |
| <country> | <v> | <y> | <year> | ALLAREA | <value> (<nature>) | YEAR DIFFERS |
| <country> | <v> | <y> | <year> | URBAN only | NOT IN SOURCE for national | PARTIAL ROW |
| <country> | <v> | <y> | no match | ALLAREA | <value> (<nature>) | NO MATCH |
| <country> | empty | <y> | none | none | NOT IN SOURCE | NO DATA |

<n> rows flagged.
```

## Rules

- **Cannot reach the API: say "I can't check the database now", give the link and flag nothing. Do not guess years.**
- A row with no total in the database is `NOT IN SOURCE` for the national value. Never use an urban or rural value in its place, and never average urban and rural.
- A value that matches no year is `NO MATCH`. Do not pick the nearest year.
- If two years round to the same table value, list both years and flag the row.
- Keep the `Nature` attribute (estimated, modelled, country data) next to every database value.
- Never fill an empty cell. Report what the database has for it, or `NOT IN SOURCE`.

## Copy-paste prompt (works in any assistant)

> Here is a country comparison table for SDG indicator <code>. For every row, look up the country in the UN SDG Global Database (unstats.un.org/sdgapi, Series/Data) and tell me which year the value in my table belongs to. Use only the national total row. Tell me if a country has only urban or rural rows. Give the year most rows share, and flag every row from another year, every value that matches no year and every empty cell. For each flagged row, give the database value for the shared year. Do not guess any year from memory. If you can't open the database now, say so.

## Demo

`demo/water_6.1.1.csv` is an eight-country 6.1.1 table where every row claims 2024. `demo/answer_key.md` lists what is planted in it and what comes from the database itself. Copies of the API responses with their SHA-256 are in `data/anchors/skills/ref-year-check/` in the claude-for-sdg repository.
