---
name: metadata-read
description: Read the official SDG metadata PDF for any indicator code and return six fields in a fixed order (definition, unit, numerator and denominator, method of computation, limitations, custodian), each quoted word for word with its section heading. Use when someone asks what an SDG indicator measures, what it is divided by, how it is computed or who the custodian is.
---

# Metadata Read

One indicator code in, six quoted fields out, always in the same order. Every field says which section of the metadata it came from, and the section heading is copied as the PDF writes it.

**Input**
- `code`: an indicator code from the global SDG indicator framework, e.g. `3.1.1`

## Why this exists

The wrong denominator is the most common way a correct number gets misread. The maternal mortality ratio in 3.1.1 is per 100,000 live births, and the metadata itself warns that the maternal mortality rate, a different measure, divides by person-years lived by women of reproductive age.

In a recorded test without this skill, Claude got most of the 3.1.1 wording right and still put the custodian under `1.a "Organisation"`. The PDF names it in 0.g. Its 3.1.1 limitations were about vital registration and sibling histories, while 4.b of the PDF is about the ratio and the rate. For 6.1.1 it gave `Denominator (4.c): The total population.` Section 4.c of the 6.1.1 PDF never says what is divided by what.

## Sources (use these and nothing else)

| What | Where |
|---|---|
| Metadata PDF | `https://unstats.un.org/sdgs/metadata/files/Metadata-<CC-TT-II>.pdf`. Each part of the code becomes two digits, so 3.1.1 becomes `03-01-01` and 6.1.1 becomes `06-01-01` |
| Index of metadata files, if the PDF link fails | `https://unstats.un.org/sdgs/metadata/` |

Do not use a WHO, UNICEF or World Bank page, a textbook, a news story or a summary from memory, even when it agrees.

## Steps

1. Open the PDF. Copy the `Last updated` date from the page header and the template line (`Harmonized metadata template - format version 1.1` or the like).
2. Find each field under its section. In the harmonized template these are:

| Field | Section |
|---|---|
| Definition | `2.a. Definition and concepts (STAT_CONC_DEF)` |
| Unit | `2.b. Unit of measure (UNIT_MEASURE)` |
| Numerator and denominator | No section of its own. Look in 4.c first, then 2.a |
| Method of computation | `4.c. Method of computation (DATA_COMP)` |
| Limitations | `4.b. Comment and limitations (REC_USE_LIM)` |
| Custodian | `0.g. International organisations(s) responsible for global monitoring (SDG_CUSTODIAN_AGENCIES)` |

3. Copy each section heading exactly as the PDF prints it, spelling included (`organisations(s)` is the PDF's own spelling). If the PDF uses an older template with other numbers, copy its headings and say so.
4. Quote the first sentence of the definition, the whole unit line and the first sentence of the limitations. For the method, quote the first sentence in 4.c that says how the value is computed. If 4.c opens with a list of production steps, skip it and take the sentence with the rule, such as the 6.1.1 line that the service level is "taken as the minimum of these three indicators". Fix only spacing broken by text extraction (`t aken` becomes `taken`).
5. For numerator and denominator, quote the one sentence that says what is divided by what. If no sentence in the PDF names both, write `NOT IN SOURCE` and quote the unit line instead. Do not build a fraction from the definition.

## Answer layout

```
<code> · <indicator name from 0.c>       metadata last updated <date>, <template line>
Definition      "<quote>"                          <section heading>
Unit            "<quote>"                          <section heading>
Numerator and denominator  "<quote>" or NOT IN SOURCE    <section heading>
Method          "<quote>"                          <section heading>
Limitations     "<quote>"                          <section heading>
Custodian       "<quote>"                          <section heading>
Source: <PDF URL> · read <today's date>
```

## Rules

- **Cannot open the PDF: say "I can't open the metadata now" and give the link. Do not fill any field from memory.**
- The order of the six fields never changes, even when the question asks about one of them.
- A field the PDF does not have is `NOT IN SOURCE`. Never fill it from another indicator, another agency or what the field usually says.
- Never convert a unit. Per 100,000 live births stays per 100,000 live births. Do not restate it as a percent or per woman.
- When the PDF names a similar measure that uses a different denominator, add one line quoting that sentence with its section. For 3.1.1 that is the maternal mortality rate in 4.b.
- Never invent a number. Every number in the answer appears in the PDF.

## Copy-paste prompt (works in any assistant)

> Open the official UN metadata PDF for SDG indicator <code> at unstats.un.org/sdgs/metadata (the file is Metadata-CC-TT-II.pdf, so 3.1.1 is Metadata-03-01-01.pdf). Give me, in this order: definition, unit of measure, numerator and denominator, method of computation, limitations, custodian agency. Quote each one word for word and copy the section heading it sits under. If the PDF never says what is divided by what, write NOT IN SOURCE for that line. If you can't open the PDF now, say so and give me the link. Do not answer from memory.

## Running it as code

`engines/ai/indicator_card.py` in the claude-for-sdg repository downloads the same PDF, keeps its SHA-256 and cuts sections by their numbers. Copies of the 3.1.1 and 6.1.1 PDFs used for the recorded test are in `data/anchors/skills/metadata-read/`.
