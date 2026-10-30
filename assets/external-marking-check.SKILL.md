---
name: external-marking-check
description: Check a draft that reuses text from a partner document marked confidential or otherwise sensitive. Confirms the partner's marking is kept or matched with equal or stronger protection, and flags where partner consent is needed before the text is declassified or made public. Use when a team wants to reuse partner material in a donor update, report or web page.
---

# External Marking Check

One draft in, one check out. Each finding points to a passage in the user's own document and to the bulletin clause that governs it. If the bulletin cannot be opened, the check says so and gives no ruling.

**Inputs**
- `draft`: the user's own document, e.g. a donor update. Mark partner passages with a short label. Do not paste the partner's confidential text.
- `partner_marking`: the marking on the partner's original, copied as printed, e.g. "Confidential".
- `audience`: who will see the draft. Internal, donors only, or public.
- `consent`: optional. Any written reply from the partner about reuse.

## Why this exists

Partner proposals arrive stamped confidential. Teams then lift text into donor updates and the stamp gets lost on the way. The UN rule on information from outside sources is short. Keep the partner's marking or use one that protects at least as much. Before declassifying, weigh what the partner expects and ask them first where that is appropriate.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UN Secretary-General's bulletin on information sensitivity, classification and handling | The clause on external information with prior markings. The clause on declassifying information from an outside source | `https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf` |
| The user's own draft | The text to check and the markings it carries | Supplied by the user |

The two clauses, as given in the evidence for this skill:

> "3.2 Where information from an external source contains prior sensitivity markings, it shall retain those markings or shall be assigned a classification that provides a degree of protectio n greater than or equal to that of the entity that furnished the information."

> "4.4 When declassifying information received from an outside source, the Organization shall give due regard to expect ations of confidentiality of that outside source and, if appropriate, shall seek the prior consent of the outside source."

If the bulletin does not open, write `SOURCE NOT OPENED`. Do not fill it from memory or a search summary.

## Steps

- Open the bulletin. Find both clauses and check that the wording matches the quotes above. If it does not open, say so and stop before any ruling.
- Read the user's draft. List every labelled partner passage. If it is unclear whether a passage comes from the partner, ask the user.
- For each passage, note the partner's marking and the marking the draft carries.
- Apply the marking clause. A passage passes only if the draft keeps the partner's marking or carries a classification that protects at least as much. A public draft carries no protection. Partner text marked confidential in a public draft fails.
- If the team wants to lower the marking or publish, apply the declassification clause. Say what the partner is likely to expect, based only on its marking and any reply supplied. Say whether consent should be sought first. Quote any consent reply.
- Give a fix for each failed passage. Remove it, hold it until the partner agrees, or replace it with text the team owns that holds nothing from the partner's document.

## Answer layout

```
Draft: <title of the user's document>   Audience: <audience>
Bulletin opened: yes, or SOURCE NOT OPENED

| Passage | Partner marking | Draft marking | Result | Clause |
|---|---|---|---|---|
| <label> | <as printed> | <as in draft> | kept, raised or fails | marking clause |

Consent: <seek first, given, or not needed and why>   "<quoted words from the declassification clause>"
Fix: <one line per failed passage>
Not covered: <anything asked that the bulletin does not state>
```

## Rules

- **No ruling without the bulletin open. If it cannot be opened, write `SOURCE NOT OPENED` and do not fill from memory.**
- Quote the bulletin's words. Keep "shall" as "shall". Never soften it to "may" or "should".
- Take the partner's marking as printed. Do not guess what it means beyond what the bulletin says.
- Whether consent is appropriate is the team's call. Flag it every time partner text moves to a wider audience, and lean toward asking.
- Never call partner text cleared for public use unless the user supplies a consent reply or states why consent is not appropriate.
- If the question goes beyond the two clauses, such as who may declassify or how long a marking lasts, write `NOT IN SOURCE`.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> Check my draft below for text taken from a partner document marked <marking as printed>. The draft is for <internal, donors only, or public>. Use only the UN Secretary-General's bulletin at https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf and my draft. Quote the clause on external information with prior sensitivity markings and the clause on declassifying information from an outside source. For each labelled partner passage, say whether my draft keeps the partner's marking or one that protects at least as much, and whether I should seek the partner's consent before this goes out. Suggest a fix for any passage that fails. If you cannot open the bulletin, say so and do not answer from memory. I have left out the partner's confidential text and put a label where each passage sits.
