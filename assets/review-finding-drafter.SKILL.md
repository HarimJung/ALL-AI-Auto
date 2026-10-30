---
name: review-finding-drafter
description: Turn a technical expert reviewer's own working notes on an issue into a side-by-side card that shows the same issue drafted as a question, as a recommendation and as an encouragement. Use when a first-time reviewer under the Enhanced Transparency Framework has a blank page and needs a worked example built from their own document.
---

# Review Finding Drafter

You give it your notes and get back a card. The card drafts the same issue as a question, a recommendation and an encouragement, side by side. Every fact in a draft comes from your own document.

**Inputs**
- `document`: required. Your own working notes or draft review text. Paste it or attach it.
- `issue`: optional. The point in the document you want drafted. If it is missing, take the first issue the notes raise and say which one you took.

## Why this exists

First review. Blank page. A UNFCCC report on the technical expert review process names this gap. It lists "Limited practical examples and guidance for drafting questions, areas of improvement, recommendations, encouragements and capacity-building needs, particularly for first-time technical expert reviewers". The same report gives lead reviewers the job of keeping each review consistent. A draft card gives the new reviewer a worked example from their own case to take to the lead reviewer.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UNFCCC report on the technical expert review process, the table of challenges | The line on limited examples and guidance for first-time technical expert reviewers | `https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf` |
| Same report, the passage on lead reviewers | "The LRs ensure consistency and quality in the TER process, facilitate communication between the Parties and the TERT, and provide guidance to the secretariat in compiling and editing the final TERRs." | Same file |
| The user's own document | The facts of the issue. This is the only source for the content of the drafts | Supplied by the user |

If the UNFCCC file does not open, say so at the top of the answer. Do not restate its content from memory or from a search summary. The card can still be drafted from the user's document.

## Steps

- Open the UNFCCC file. Find the two passages above and copy them word for word. If a passage is not in the opened file, write `NOT FOUND` next to it.
- Read the user's document. Pick the issue. List only the facts the document states about it. Write any missing fact as a gap.
- Draft the question. It asks the Party for the missing information. Keep it short and specific. Name the gap in the document's own words.
- Draft the recommendation. It states what the Party should do to fix the gap in its next report. Use only facts from the document.
- Draft the encouragement. It invites the Party to make an improvement it may choose to make. Keep it softer than the recommendation.
- Under each draft, write a short line on why that label fits. Mark these lines as drafting guidance, since the quoted passages do not define the labels.
- End with a line telling the reviewer to check the wording with the lead reviewer, and quote the lead reviewer passage.

## Answer layout

```
Issue: <the issue in the document's words>
Source: opened / UNFCCC source not opened

| Question | Recommendation | Encouragement |
|---|---|---|
| <draft> | <draft> | <draft> |
| Why: asks for missing information | Why: names a fix the Party should make | Why: invites an optional improvement |

Gaps in your notes: <facts the drafts need that the document does not state>
Check with your lead reviewer: "<quoted lead reviewer passage>"
Label guidance is drafting help. It is not a UNFCCC definition.
```

## Rules

- **Use only facts in the user's document. Never add a method, gas, sector, figure or name the document does not state.**
- Quote the UNFCCC passages word for word. Never present a paraphrase as a quote.
- The quoted passages list the drafting types without defining them. Say so on the card. Do not claim an official definition from memory.
- If the UNFCCC file cannot be opened, write `UNFCCC source not opened` and do not fill its content from memory or a search summary.
- Keep every draft neutral and polite. Address the report and the information. Do not blame the Party.
- Use plain English and short sentences.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> I am a first-time technical expert reviewer. Using only my notes below, draft the same issue three ways, side by side: as a question to the Party, as a recommendation and as an encouragement. Under each draft, add a short line on why that label fits, and say that this is drafting help and not an official definition. Do not add any fact my notes do not state. List any gaps in my notes. If you can open the UNFCCC report at https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf, quote its passage on lead reviewers word for word and remind me to check my wording with my lead reviewer. If you cannot open it, say so and do not fill it from memory. My notes: <paste your notes>
