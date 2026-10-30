---
name: meeting-actions
description: Turn your own meeting minutes into an action table with a draft follow-up for each action and the staff role who signs it off. Use when an intern or new joiner has written the minutes and must draft follow-ups they cannot send or sign in UNDP's name.
---

# Meeting Actions

Your minutes in, an action table out, with every follow-up marked as a draft and a staff role named to sign it off.

**Inputs**
- `minutes`: your own minutes or working notes, pasted or attached, with names and personal details removed.
- `meeting`: optional. The group's name as you want it in the header, for example the Result Group.
- `sign_off`: optional. The staff role who approves your messages, for example your supervisor.

## Why this exists

An intern may write the minutes and draft the follow-up. A UNDP Rwanda internship description lists this work: "ONE UN Rwanda, writing minutes and following up with communication, etc." The same document sets a limit: "Interns are not staff members and may not represent UNDP in any official". You can draft the follow-up. A staff member has to send and sign it. A quick draft from a chat assistant reads as if you could send it yourself. This skill puts the sign-off next to every message so nobody misses it.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| UNDP Rwanda internship description | Responsibilities and Accountabilities section: the intern writes minutes and follows up on communication. Conditions section: interns are not staff and may not represent UNDP officially | `https://www.undp.org/sites/g/files/zskgke326/files/migration/rw/Internship_ME.pdf` |
| Your minutes or notes | The actions the meeting agreed and who owns each one | The text you paste or attach |

If the PDF does not open, say so at the top of the answer and write `SOURCE NOT OPENED` in place of each quote. Do not fill the quotes from memory or a search summary. Do not use any other page, policy or template.

## Steps

- Open the internship PDF. Find the Responsibilities and Accountabilities section and the Conditions section. Copy the two quoted lines word for word. If the file does not open, mark both `SOURCE NOT OPENED` and carry on with the minutes alone.
- Read the minutes. If you see a name or other personal detail, stop. Ask the user to replace it with a role and paste the minutes again.
- List each action the meeting agreed. Keep the minutes' own words. Give each action its own row.
- Write the owner as a role taken from the minutes. Copy a due date only if the minutes state it. If they do not, write `NOT IN MINUTES`.
- Draft a short follow-up for each action that needs a message. Start it with DRAFT. Write it for a staff member to send and leave the signature for them.
- Fill the sign-off column with the staff role who approves and sends the message. Use `sign_off` if the user gave it. If nothing says who, write `ASK SUPERVISOR`.
- Put anything the minutes leave unclear under Open questions. Leave it open for the user to check.

## Answer layout

```
<meeting> · minutes from user · source read <today's date>
Task:  "ONE UN Rwanda, writing minutes and following up with communication, etc."   Responsibilities and Accountabilities
Limit: "Interns are not staff members and may not represent UNDP in any official"   Conditions
(write SOURCE NOT OPENED in place of a quote that could not be checked)

| Action, in the minutes' words | Owner role | Due | Draft follow-up | Signs off |
|---|---|---|---|---|
| <action> | <role> | <as written, or NOT IN MINUTES> | DRAFT: <short message> | <staff role, or ASK SUPERVISOR> |

Open questions: <what the minutes leave unclear>
All messages above are drafts. None has been sent or signed.
```

## Rules

- **Every follow-up is a draft. The intern does not send or sign anything in UNDP's name. A staff member signs off each message.**
- Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.
- Use only the internship PDF and the user's minutes. Add nothing the minutes do not say.
- Quote the PDF word for word. If it does not open, say so. Never quote it from memory or from a search summary.
- Put roles in the owner and sign-off columns. The user adds names after the draft leaves the AI tool.
- A draft does not promise money or agree to anything for UNDP. If an action needs that, flag it in Open questions for the staff member who signs off.
- If the user asks you to send or sign a message, decline and point to the sign-off column.

## Copy-paste prompt (works in any assistant)

> I am an intern and I wrote these meeting minutes. I removed names and personal details. Turn them into a table of actions in the minutes' own words. For each action give the owner as a role, the due date only if the minutes state it, a short follow-up message marked DRAFT, and the staff role who signs it off. I may not send or sign anything in UNDP's name. Open https://www.undp.org/sites/g/files/zskgke326/files/migration/rw/Internship_ME.pdf and quote the line "Interns are not staff members and may not represent UNDP in any official". If you cannot open that file, say so and do not quote it from memory. Use no other source. If something in the minutes is unclear, list it as an open question.
