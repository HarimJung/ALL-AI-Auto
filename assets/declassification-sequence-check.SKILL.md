---
name: declassification-sequence-check
description: Check the order of steps in an office's own plan for sending closed classified files to the Archives and Records Management Section, against the Secretary-General's bulletin on information sensitivity, classification and handling. Use when someone is packing project files for the Archives, or has a transfer plan, and asks whether declassification review has to happen first.
---

# Declassification Sequence Check

You give it one transfer plan and get back one sequence card, with each step tied to a quoted line of the bulletin.

**Inputs**
- `document`: required. The user's own transfer plan, checklist, email or file list. Working notes are fine.
- `markings`: optional. The classification levels the files carry, in the user's own words.

## Why this exists

Offices close a project, pack the boxes and send them to the Archives. Often nobody thinks of declassification review until the boxes have gone. The bulletin sets the order. Review comes first. Transfer to the Archives comes after. A plan with these steps the wrong way round needs to be caught before the boxes move.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Secretary-General's bulletin on information sensitivity, classification and handling | The declassification section. The paragraph on marking a date or event that triggers declassification. The paragraph on review before transfer to the Archives. The sub-paragraph on item-by-item review of strictly confidential records | `https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf` |
| The user's own document | The steps the office plans to take, in its own order | Pasted or attached by the user |

If the bulletin does not open, say so in the first line of the answer. Do not fill in its wording from memory or from a search summary. Check the user's document for order only, and mark every bulletin line UNVERIFIED.

## Steps

- Open the bulletin. Copy its symbol and title from the first page.
- Find the declassification section. Copy the paragraph that begins "4.1 The originator of the information".
- Copy the paragraph that begins "4.3 Review for possible declassification shall take place before records are transferred".
- If the user's document mentions strictly confidential files, copy the sub-paragraph that begins "(a) Records that are classified as “strictly confidential”".
- Read the user's document. List each step in the order it appears. Keep the user's words.
- Put each step into one of three stages. Set a declassification date or event. Review the records. Transfer them to the Archives and Records Management Section. Steps that fit none of these go under Other.
- Compare the user's order with the bulletin's order. Flag any transfer that comes before review. Flag any classified file that has no date or event marked on it. Keep the bulletin's words "where appropriate" next to that flag.
- Write the sequence card.

## Answer layout

```
Sequence check · bulletin read <today's date>   (or: bulletin did not open, every quote UNVERIFIED)

Your order:     <step> / <step> / <step>
Bulletin order:
  Set:       "<quote from the marking paragraph>"
  Review:    "<quote from the review before transfer paragraph>"
  Transfer:  to the Archives and Records Management Section, after review

| Your step | Stage | In order? | Bulletin line |
|---|---|---|---|
| <user's words> | review | no, it comes after transfer | "<quote>" |

Strictly confidential: "<quote from sub-paragraph (a)>"   (only if the document mentions it)
Fix: <which step to move, in one line>
Not covered: <anything asked that the bulletin does not state>
```

## Rules

- **Review comes before transfer. Quote the bulletin for this every time. Never state the order from memory.**
- Quote the bulletin's own words. Shorten only by cutting. Keep "shall" and "where appropriate" exactly as written.
- Work only on the user's document. Do not add steps it does not mention, apart from the three stages.
- Do not name who in the user's office may carry out the review. Quote what the bulletin says about who reviews and stop there.
- How to recall boxes that have already gone is NOT IN SOURCE. Say so. Name the Archives and Records Management Section as the office that holds them.
- Do not work out when a record becomes old enough for review. Quote the sub-paragraph and leave the counting to the user.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> Check the order of steps in my office's plan for sending closed project files to the UN Archives. My plan is pasted below. Use only the Secretary-General's bulletin on information sensitivity, classification and handling at https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf and my own plan. Quote the declassification paragraph on marking a date or event, the paragraph on review before transfer to the Archives and Records Management Section, and, if my plan mentions strictly confidential files, the sub-paragraph on item-by-item review. List my steps in my order, say which stage each one belongs to, and flag any transfer that comes before review. If you cannot open the bulletin, say so and mark every quote UNVERIFIED. Do not answer from memory.
