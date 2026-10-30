---
name: sensitivity-precheck
description: Check a UN staff member's own draft before it goes into an AI tool. Help them decide whether it is sensitive, mark it, and keep classified material on protected channels, with every rule quoted from the Secretary-General's bulletin on information sensitivity. Use when someone is about to paste a note, email or draft into an AI tool and has not yet decided how it is classified.
---

# Sensitivity Precheck

One draft in, one pre-paste check out. Every rule is quoted from the bulletin. The person who wrote or received the document makes the classification call.

**Inputs**
- `document`: the user's own draft, note or email, with names and personal details already removed.
- `marking`: optional. Any classification the document already carries.
- `origin`: optional. Whether the user wrote it or received it from an outside source.

## Why this exists

New staff often paste a draft into an AI tool to fix the wording before anyone has asked whether it is sensitive. The bulletin gives that decision to the person who created or received the information. It also limits how classified material may travel electronically. An AI tool cannot make this decision for the user. The user decides and marks first, and only then picks a channel.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Secretary-General's bulletin on information sensitivity | The section on identification and markings (who decides and marks). The handling section and its line on electronic transmission. The section that lists the classification levels | `https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf` |
| The user's own document | The text to check | Supplied by the user |

The PDF usually opens with a plain download. If it does not open, say so in the first line of the answer. Then use only the two quotes in the Steps below and write `NOT OPENED` for everything else, including the list of levels. Do not fill the gaps from memory or a search summary.

## Steps

- Open the bulletin. Copy its symbol and date from the first page.
- Find the passage on identification and markings. Check that it reads: "Section 3 Identification and markings 3.1 The originator of the information concer ned, or its recipient if the information is received from an outside source, under the overall supervision and guidance of the head of department or office, shall decide whether the information is sensitive and mark it with the appropriate classifi cation as detailed in section 4 below."
- Find the line on electronic transmission. Check that it reads: "(f) Electronic transmission of classifi ed information shall be performed only through the use of protected means of communication, in accordance with section 5.4 below."
- Open the section the first quote points to ("as detailed in section 4 below"). List each classification level in the bulletin's own words, with its own definition. If that section does not open, write `NOT OPENED`.
- Read the user's document. If it already carries a classification marking, or the user says it is classified, stop. Quote the transmission line and do not work on the text.
- Otherwise, go through the draft and find each passage that may make it sensitive under the definitions you opened. Quote the passage. Give the reason in a few words, tied to the bulletin's wording. Mark each one `YOUR CALL`.
- Close with the marking step. The user decides the level and marks the draft before sharing it. Point them to their head of department or office for guidance, since the bulletin places the decision under that supervision.

## Answer layout

```
Sensitivity precheck · bulletin <symbol>, <date> · read <today's date>
Who decides: "<quoted line>"   <section and paragraph>
How it may travel: "<quoted line>"   <section and paragraph>
Levels: <each level in the bulletin's words>   (or NOT OPENED)

| Passage in your draft | Why it may be sensitive | Bulletin wording | Status |
|---|---|---|---|
| "<quoted text>" | <a few words> | "<short quote>" | YOUR CALL |

Your next step: decide the level, mark the draft, then choose the channel.
Not covered: <anything asked that the opened bulletin does not state>
```

## Rules

- **Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.**
- **Never decide the classification for the user. Flag and quote. The originator or recipient makes the call.**
- Never tell the user a draft is safe to paste. Say what the bulletin requires and leave the decision with them.
- If the document is marked or described as classified, stop and quote the transmission line.
- Quote the bulletin for every rule. Keep its "shall" as "shall".
- Use the bulletin's names for the levels. Never invent a level or a definition.
- If the user asks which AI tools count as protected means of communication, or which tool their organization allows, write `NOT IN SOURCE`. Treat no tool as protected unless an opened document says so.
- If the bulletin does not open, say so first. Never fill a section from memory.
- Write in plain English with short sentences.

## Copy-paste prompt (works in any assistant)

> Before I share my draft anywhere, help me check it for sensitivity. I have removed names and personal details. Use only the Secretary-General's bulletin at https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf and my draft below. Quote the bulletin's lines on who decides and marks sensitivity, on electronic transmission of classified information, and its list of classification levels. Then quote each passage in my draft that may be sensitive, say why in a few words, and mark it as my call. Do not decide the level for me and do not tell me the draft is safe to paste. If you cannot open the bulletin, say so and do not answer from memory. My draft: <paste here>
