---
name: partner-report-indicator-check
description: Check the indicators and deliverables in an implementing partner's narrative report against the baseline and end line in the user's own programme document. Use when someone asks whether a partner report matches the programme document, or whether a target the partner says was met is backed by the indicator as written.
---

# Partner Report Indicator Check

You give it one programme document and one partner report. It gives back one checked line per indicator, and each line says where its evidence was found. If the report says a target was met but gives no value, the line says so.

**Inputs**
- `programme_document`: the user's own programme or project document, or the part of it that holds the results framework. It must give each indicator, its baseline, its end line and its source of verification.
- `partner_report`: the implementing partner's narrative report, or the section of it that reports on results.
- `indicator`: optional. Name one indicator to check. If this is left out, check every indicator in the programme document.

## Why this exists

Partner reports often say a target was met without giving the value, the unit or the source. A new officer then has to decide whether that sentence fits the baseline and end line agreed in the programme document. The UNDP terms of reference for an M&E intern name this task directly. This skill turns it into a fixed side-by-side check that shows the evidence for each line.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UNDP Rwanda, Monitoring and Evaluation internship terms of reference | Its section on responsibilities and accountabilities states the task: "Review the programme documents and annual work plans, ensuring the indicators and deliverables of narrative reports from the implementing partners are in line with the baseline/end line information defined in the documents." It also names "the analysis of the collected data and the final reporting against project indicators." | `https://www.undp.org/sites/g/files/zskgke326/files/migration/rw/Internship_ME.pdf` |
| The user's programme document | Indicators, baselines, end lines and sources of verification | Pasted or attached by the user |
| The user's partner narrative report | What the partner says was achieved | Pasted or attached by the user |

The terms of reference only describe the task. Every value in the answer comes from the user's two documents. If the UNDP file does not open, say so in one line and carry on with the user's documents. Do not describe what it says from memory. If a user document is missing or cannot be read, stop and ask for it.

## Steps

- **Read the programme document.** List each indicator with its exact wording, baseline, end line, unit and source of verification. Note the page or section where each one sits.
- **Read the partner report.** For each indicator, find the passage that reports on it. Copy the words and note the page or section.
- **Match the indicator.** Check that the report talks about the same indicator. It must measure the same thing, in the same unit, for the same group of people or places. If the wording differs, quote both versions.
- **Compare the value.** Put the reported value next to the baseline and the end line. Compare them only when both use the same unit. If the report gives no value, write `NO VALUE GIVEN`.
- **Check the source.** Say whether the report names the source of verification that the programme document asks for.
- **Check deliverables.** If the programme document or annual work plan lists deliverables, check each one the same way.
- **Give a status** for each line. Use only these labels: `MATCHES`, `DIFFERS`, `NO VALUE GIVEN`, `NOT REPORTED`, `NOT IN PROGRAMME DOCUMENT`.
- **List questions for the partner.** Write one line per gap, in plain words the officer can send.

## Answer layout

```
Indicator check · <programme name from the document> · <partner name from the report>
UNDP terms of reference: opened / could not be opened

| Indicator (programme document words) | Baseline | End line | Partner report says | Source named | Status | Where |
|---|---|---|---|---|---|---|
| <indicator> | <baseline> | <end line> | "<quote>" | yes / no | <status> | programme document <section>, report <section> |

Questions for the partner:
- <one line per gap>

Not covered: <anything asked about that neither document states>
```

## Rules

- **"Target met" is a claim. It counts only when the report gives a value in the same unit as the end line. If there is no such value, the status is `NO VALUE GIVEN`.**
- Quote both documents. Do not reword an indicator into a different one.
- Never fill a missing baseline, end line or value from memory, from a similar project or from a guess. Write `NOT IN PROGRAMME DOCUMENT` or `NOT REPORTED`.
- Do not work out new totals unless both documents give the parts in the same unit. If you do, show the working.
- Mark a changed unit, group or place as `DIFFERS`, even when the partner calls the target met.
- Do not judge the partner. Report what the documents say and what is missing. The supervisor decides.
- If a source cannot be opened, say so. Do not fill it from memory or a search summary.
- Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> I will paste two texts. The first is the results framework from my programme document. The second is an implementing partner's narrative report. For each indicator in the programme document, quote its wording, baseline, end line and source of verification. Then quote what the partner report says about it, and say where in the report it appears. Mark each line MATCHES, DIFFERS, NO VALUE GIVEN, NOT REPORTED or NOT IN PROGRAMME DOCUMENT. A statement that a target was met counts only if the report gives a value in the same unit as the end line. Do not fill any gap from memory and do not guess. End with a short list of questions I can send to the partner. If you cannot read one of the texts, tell me and stop.
