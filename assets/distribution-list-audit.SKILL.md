---
name: distribution-list-audit
description: Check the user's own distribution list or copy log for a recurring classified product, such as a situation report, against the UN Secretary-General's bulletin on information sensitivity, classification and handling. Flags copies sent outside the standard list, copies made without authorization, and copies missing from the special registry. Use when someone asks whether a forward or an extra copy was allowed, or wants an auditable distribution list and copy log.
---

# Distribution List Audit

One distribution list or copy log goes in and one audit comes out. Each finding quotes the line of the bulletin it rests on. The audit holds roles and document IDs only. It never holds the content of the report.

**Inputs**
- `document`: the user's own distribution list, copy log, or short note of who received which product. Replace names with roles before pasting.
- `product`: optional. The recurring product in question, for example a situation report, an operational update or a periodic political assessment.

## Why this exists

Recurring reports get forwarded on request. A colleague asks, the report looks useful, and the copy never reaches the registry. The bulletin treats this as a gap in control. Copying a classified sitrep needs authorization. Every copy goes in the special registry. Staff need a quick check against the actual text and a list format that an auditor can follow.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Secretary-General's bulletin "ST/SGB/2007/6" on information sensitivity, classification and handling | The section on handling classified information. It covers the special registry, the rule on duplication, and standard distribution lists for recurrent products | `https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf` |
| The user's own document | The list, the log, or the note of who received what | Supplied by the user |

The UN documents site sometimes fails or returns an empty page. If the bulletin does not open, say so plainly. Do not fill the rules from memory or from a search summary. Give the audit layout with each rule marked `NOT CHECKED: source did not open`.

## Steps

- Open the bulletin. Copy its symbol and title from the first page.
- Find and quote exactly the lines this skill rests on. These are the line on standard distribution lists for recurrent products, the line on the special registry, and the line on duplication.
- Read the user's document. List each recipient role and each document ID. Do not repeat any report content.
- Mark each recipient as on the standard list or off it.
- For each copy, check whether the document records who authorized it. Only the originator or the head of the receiving or originating department or office can authorize a copy.
- For each copy, check whether the document shows a registry entry.
- Build the clean template with a standard list, a copy log and the open gaps.

## Answer layout

```
<product> · bulletin opened <today's date>   (or NOT OPENED and why)

Rules checked
Standard list: "<quoted line>"
Registry: "<quoted line>"
Copies: "<quoted line>"

| Recipient role | Document ID | On standard list | Authorized by | In registry | Gap |
|---|---|---|---|---|---|
| <role> | <ID> | yes or no | <originator, head of office, or none recorded> | yes or no | <what to fix> |

Template (fill names in your own system only)
Standard list: <product>, <owner>, <recipient names>
Copy log: <document ID>, <recipient name>, <authorized by>, <registry entry>

Not covered: <anything asked that the bulletin does not state>
```

## Rules

- **A finding with no quoted line behind it is `UNVERIFIED`. Never state a handling rule from memory as confirmed.**
- Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.
- The audit and the template hold roles, names and document IDs only. Never copy the content of the report into the answer.
- Quote the bulletin's own words. Keep "must" and "may" as written. Shorten only by cutting.
- A request from the recipient is no authorization. Only the originator or the head of the receiving or originating department or office can authorize a copy.
- Do not judge the classification level of the report. If the user's document does not state it, write `NOT IN DOCUMENT`.
- If the question asks about a form, a system or a sanction the bulletin does not describe, write `NOT IN SOURCE`.
- Send any fix beyond the quoted rules to the originator or the head of office.

## Copy-paste prompt (works in any assistant)

> Check my distribution list and copy log for <product> against the UN Secretary-General's bulletin "ST/SGB/2007/6" on information sensitivity, classification and handling, at https://documents.un.org/api/symbol/access?s=ST/SGB/2007/6&l=en&t=pdf. Use only that bulletin and my document below. Quote the lines on standard distribution lists, the special registry and duplication. For each recipient, say whether they are on the standard list, who authorized the copy, and whether it is in the registry. Then give me a clean list and copy log with roles and document IDs only. If the bulletin does not open, say so and do not answer from memory. Do not repeat any report content. <paste list with names replaced by roles>
