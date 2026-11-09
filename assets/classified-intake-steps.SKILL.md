---
name: classified-intake-steps
description: Turn a classified item that arrived by email into a short intake card for UN staff. The card says to print it on receipt, file and store it as the bulletin directs, keep it on protected systems, and use AI only on the unclassified parts of the work. Every step is quoted from the Secretary-General's bulletin on classified information. Use when someone has a classified attachment in their inbox and asks whether AI can summarise it.
---

# Classified Intake Steps

One classified item in, one intake card out. Each step quotes the bulletin. Anything the opened text does not state is marked NOT IN SOURCE.

**Inputs**
- `document`: the user's own working notes about the item. This can be the cover email with the attachment removed, or a short note of what arrived and how it is marked. It is never the classified content itself.
- `question`: what the user wants to do with the item, such as get a summary or pass it to a colleague.

## Why this exists

A classified attachment looks like any other file in an inbox. The quick move is to drop it into an AI tool for a summary. The bulletin asks for a paper step on receipt and protected systems for any electronic handling. Unless your office has approved an AI tool for classified work, treat it as an unprotected system. Staff need the steps at the moment the file arrives, with the bulletin's own words behind each one.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Secretary-General's bulletin on classified information | The paragraph on printing items received in electronic form, the paragraph on filing and storage it points to, the paragraph on protected means of communication, and the paragraph on controls for automated information systems | `https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf` |
| The user's own document | What arrived, how it is marked, and what the user wants to do | Pasted or attached by the user |

The UN documents site sometimes returns an error or a bot check instead of the PDF. If the bulletin does not open, say so plainly. Do not fill the steps from memory or a search summary. Give the user the link and stop.

## Steps

- Read the user's document first. If it holds classified content, stop. Tell the user to remove it from the chat and not to paste it again. Work only from the marking and the user's own notes.
- Open the bulletin PDF. Copy the document symbol and the title from the first page.
- Find the paragraph that begins "(e) A hard copy of classified information received in an electronic form". Quote it as the receipt step.
- Find the subparagraph that the receipt step points to with the words "as detailed in subparagraph (d) above". Quote what it says on filing and storage. If the text is not there, write NOT IN SOURCE.
- Find the paragraph that begins "(f) Electronic transmission". Quote it as the sending step.
- Find the paragraph that begins "Heads of departments and offices". Quote the part on "controls that both prevent access by unauthorized persons".
- Answer the user's question. If they asked AI to summarise, read, translate or rewrite the classified item, say no and quote the sending step. Then list what AI can still help with on the unclassified side. Examples are a reply to the sender asking which protected channel to use, a plan for the user's own unclassified tasks, or a checklist built from this card.
- Say who decides which systems are protected. The bulletin gives this to heads of departments and offices working with IT services. Tell the user to ask their office which systems are approved. Do not name a system yourself.

## Answer layout

```
Intake card · <document symbol from the first page>
Item: <what arrived and its marking, from the user's notes>

On receipt: print it.          "<quoted line>"   <paragraph label>
Store it: as the bulletin says. "<quoted line>"   <paragraph label>   (or NOT IN SOURCE)
Sending it: protected means only. "<quoted line>"   <paragraph label>
Systems: approved controls only.  "<quoted line>"   <paragraph label>

AI on this item: no. Use it only for the unclassified parts below.
- <unclassified task AI can help with>
- ...

Ask your office: <which protected systems are approved, and anything else the bulletin leaves to the office>
Not covered: <anything asked that the bulletin does not state>
```

## Rules

- **Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.**
- Never summarise, translate, rewrite or analyse the classified content. If it is pasted, stop and say so.
- Quote the bulletin for every step. Shorten only by cutting. Keep "must" and "shall" as written.
- If the bulletin does not open, say it could not be opened. Do not fill the steps from memory, a news item or a search summary.
- Never say that a named AI tool or platform is approved for classified information. The bulletin leaves approval to heads of departments and offices.
- If the question asks about a classification level, a form or a procedure the opened text does not describe, write NOT IN SOURCE and point the user to their office.
- Never invent a paragraph label, a classification level or a contact.

## Copy-paste prompt (works in any assistant)

> I have a classified email attachment and I want to know what to do with it. Do not ask me to paste it and do not summarise it. Use only the Secretary-General's bulletin at https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf and my own notes below. Make me a short intake card. Quote the bulletin's lines on printing classified items received in electronic form, filing and storing them, sending them only through protected means of communication, and controls on automated information systems. Give the paragraph label for each quote. Then list what AI can help me with on the unclassified parts of my work only. If you cannot open the bulletin, say so and do not answer from memory. My notes: <what arrived, how it is marked, what I want to do>.
