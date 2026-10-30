---
name: question-batch-tracker
description: Turn a batch of reviewer questions in the user's own document into a tracker that logs each question with its batch, owner, due date and response status. Use when a Party's focal point gets another batch of reviewer questions and has to restart coordination with national agencies.
---

# Question Batch Tracker

One document in, one tracker out. Each question gets a batch, an owner, a due date and a status. Anything the document does not state is marked OPEN.

**Inputs**
- `document`: required. The user's own file with the reviewer questions. It can be pasted text, an export from the question and answer platform, or an earlier version of this tracker.
- `batch`: optional. The name of the new batch, as the reviewers labelled it.
- `owners`: optional. The agencies or colleagues who usually answer each topic.

## Why this exists

Reviewers send questions in several batches. Each batch starts the chase across agencies again, and there is little time to consult. The online platform does not help much. A UNFCCC document records both problems as Parties reported them. A plain tracker kept outside the platform shows who owes which answer and by when.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UNFCCC CMA document (PDF) | A table of challenges Parties reported. It names the batch problem and the platform problem in the two lines quoted below | `https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf` |
| The user's own document | The questions, any owners, any due dates and any answers already drafted | Supplied by the user |

The two lines to quote:
- "Multiple batches of questions requiring repeated internal coordination and limited time for inter-agency consultation and preparation of responses"
- "Technical issues with online question and answer platforms (e.g. character limits and attachment size restrictions, limited functionality for notifications, follow-up exchanges and tracking responses)"

The UN document server sometimes serves a check page instead of the PDF. If the file does not open, say so. Do not fill the quotes from memory or a search summary.

## Steps

- Open the UNFCCC PDF and find the two lines above. If it does not open, write `SOURCE NOT OPENED` in the header and work from the user's document only.
- Read the user's document. Copy each question in the reviewers' own words. Shorten only by cutting.
- Keep any question ID the reviewers gave. If there is none, use the batch name and a letter.
- Take the owner from the document or from `owners`. If there is none, write `OPEN: no owner`.
- Copy a due date only if the document states one. If there is none, write `OPEN: no due date`.
- Set the status to one of these: Not started, With owner, Draft in, Cleared, Sent. Take it from the document. If the document is unclear, use Not started.
- If the document holds an earlier tracker, keep the earlier batches and add the new batch below them. Flag any older question that is still not sent.
- If a draft answer is long or needs an attachment, flag it `CHECK PLATFORM LIMITS`. Use the limits the platform itself shows.
- End with a chase list. Give one line per owner with the question IDs they still owe.

## Answer layout

```
<batch> · tracker built <today's date> · source: opened or SOURCE NOT OPENED
Why: "<quoted line on batches>"

| ID | Question (reviewers' words) | Owner | Due | Status | Flag |
|---|---|---|---|---|---|
| <id> | <question> | <owner or OPEN> | <due or OPEN> | <status> | <flag or blank> |

Chase: <owner>: <IDs still owed>
Open items: <questions with no owner or no due date>
```

Keep the answer short. Use one row per question.

## Rules

- **An owner or due date the document does not state is `OPEN`. Never fill one from memory or a guess.**
- Keep the reviewers' wording for each question. Do not merge questions.
- Quote the UNFCCC lines word for word, or leave them out.
- Do not state the platform's character or file size limits. The source does not give them.
- Do not draft the technical answers unless the user asks. This skill tracks them.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> I am a focal point and I just received another batch of reviewer questions. From the document I paste below, build a tracker table with one row per question. Give the reviewers' own wording, the owner, the due date, the status (Not started, With owner, Draft in, Cleared or Sent) and a flag. Take owners and due dates only from my document. Where one is missing, write OPEN and do not guess. Keep any earlier batches I include and flag questions that are still not sent. Mark answers that are long or need attachments with CHECK PLATFORM LIMITS. End with a chase list for each owner. If you cite the UNFCCC document at https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf, quote it word for word. If you cannot open it, say so. Do not answer from memory.
