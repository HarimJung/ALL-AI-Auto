---
name: donor-template
description: Map a partnerships officer's own master results sheet to one donor's reporting fields. The results are written once and reused for each funder. Use when someone has to fill a donor report or assessment template with results they have already written.
---

# Donor Template

You give it one master results sheet and one donor template. It gives back one field map. Each field shows the line in your document that it came from. If your document does not cover a field, the field is marked GAP.

**Inputs**
- `results`: your own master results sheet or report text. Required.
- `template`: the donor's reporting fields or form, pasted or attached. Required.
- `donor`: optional. The funder's name, used only as a label.

## Why this exists

Partnerships officers rewrite the same results for each funder. Every donor has its own format and its own assessment. The Joint Inspection Unit found that donor assessments "overlap to a large degree in terms of the content covered. While valued, such" assessments bring heavy transaction costs. It also found that relying on many funders "subjects the United Nations system to various forms of external governance frameworks with various reporting requirements". If you write results once and map them to each template, you stop rewriting. Each result also stays worded the same way for every funder.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Joint Inspection Unit report on donor-led assessments of United Nations system organizations | The outcome section on how much donor assessments overlap. The section on global governance and the leadership role, on outside reporting requirements | `https://www.unjiu.org/sites/www.unjiu.org/files/jiu_rep_2017_6_english__0.pdf` |
| The user's own document | The results to report and the donor fields to fill | Provided by the user |

If the report does not open, say so in one line. Leave out the quotes and do not fill them from memory or a search summary. If the user's document cannot be read, stop and ask for it again.

## Steps

- Read the user's results. Split them into single statements. Label each one with the heading or row it sits under in the document.
- Read the donor template. List each field in the donor's own words and order. Note any word limit or format the template states.
- For each field, find the statements that answer it. Copy the user's wording. Shorten only by cutting.
- If no statement answers a field, write GAP and say in a few words what the field asks for.
- If a statement fits more than one field, use it in each one and mark it as reused.
- List the statements that no field used. This shows the officer what this donor does not ask for.
- Open the Joint Inspection Unit report only if the user asks why one master sheet helps. Quote it exactly.

## Answer layout

```
<donor> template · mapped from <document name>

| Donor field | Text from your results | From |
|---|---|---|
| <field in the donor's words> | "<your words>" | <heading or row in your document> |
| <field> | GAP: <what the field asks for> | none |

Not used by this template: <statements left over>
Check before sending: <word limits or formats the template states>
```

## Rules

- **Take results only from the user's document. Never add a result, figure, partner or place that the document does not state.**
- Keep the user's wording. Never turn a planned result into an achieved one.
- A field with no matching text is GAP. Never fill it with a guess or a generic phrase.
- Keep the donor's field names and their order exactly.
- If a source cannot be opened, say so. Do not fill it from memory or a search summary.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> I will paste my master results sheet and a donor's reporting template. Map my results to each donor field. Use the donor's own field names and keep them in the same order. Take results only from my document and copy my wording, shortening only by cutting. For each field, show the heading or row in my document it came from. If nothing in my document answers a field, write GAP and say what the field asks for. Do not invent results, figures or partners. At the end, list the results this template did not use. Leave out anything marked confidential. If you cannot read my document, say so and do not fill it from memory.
