---
name: roster-availability-tracker
description: Turn the user's own expert roster into a sheet that flags when each expert last confirmed availability, who still needs a fresh check, and who the backups are. Every rule about timing is traced to a quoted line in the secretariat report on technical expert reviews. Use when a secretariat officer is building a technical expert review team and experts are declining because their work changed after the availability survey.
---

# Roster Availability Tracker

Your roster in, one checked sheet out. Each expert gets a status, a backup and a next action, and every timing rule is backed by a quote.

**Inputs**
- `roster`: required. The user's own document. A sheet or table with each expert, their area, when they last confirmed availability, and any named backup.
- `review`: optional. Which review the team is for and its review week, if the user knows it.

## Why this exists

An expert who said yes in the availability survey may not be free when the invitation arrives. The secretariat report says the most common reason for declining was "changes in work commitments since responding to the availability survey (50.6 per cent)". The team also has a fixed lead time. A roster that only shows survey answers hides who needs a fresh check and who has no backup.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Secretariat report on technical expert reviews | Section C on team composition: when the team must be formed. The reasons experts gave for declining. The section on challenges: limited availability and high rejection rates | `https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf` |
| The user's own roster document | Experts, areas, last confirmation, backups | Supplied by the user |

If the report does not open, say so in the first line of the answer. Do not fill the timing rule or the decline reasons from memory or a search summary. Still build the sheet from the roster and mark each timing line `SOURCE NOT OPENED`.

## Steps

- Open the report. Find and copy these lines word for word: "The secretariat forms the TERT for each TER at least 10 weeks prior to the review" and the line on "changes in work commitments since responding to the availability survey".
- Read the user's roster. Keep each expert's label exactly as the user wrote it.
- Give each expert one status. `Reconfirmed` if they confirmed after the survey. `Survey only` if their last confirmation was the survey. `No record` if the roster does not say.
- Mark every `Survey only` and `No record` expert as needing a fresh check before the team is formed.
- For each expert, name the backup from the roster. If there is none, write `NO BACKUP`.
- If the user gave a review week, state the latest day to form the team using the quoted lead time. If not, give the rule as quoted and ask for the review week.
- List any expert who appears as a backup for more than one person. One person cannot cover two gaps at once.

## Answer layout

```
Roster check · report opened: yes or SOURCE NOT OPENED
Team deadline: "<quoted line>"   <latest day, or ask for review week>

| Expert | Area | Last confirmed | Status | Backup | Next action |
|---|---|---|---|---|---|
| <label> | <area> | <as in roster> | Survey only | <name or NO BACKUP> | Reconfirm now |

Check first: <experts marked Survey only or No record>
Gaps: <experts with NO BACKUP, and backups used twice>
Why reconfirm: "<quoted decline reason>"
```

## Rules

- **Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.**
- Use only the report and the user's roster. Do not add experts, backups or confirmations the roster does not state.
- Quote the report for every timing rule. If the report did not open, write `SOURCE NOT OPENED` and do not supply the rule from memory.
- Treat a survey answer as a starting point. An expert is `Reconfirmed` only when the roster shows a check after the survey.
- Keep the user's own labels and wording for each expert and area.
- If the user asks about funding, eligibility or invitation rules the report does not state, write `NOT IN SOURCE`.
- Keep sentences short. Put the next action for each expert in plain words.

## Copy-paste prompt (works in any assistant)

> Here is my expert roster for a technical expert review team. Remove any names and personal details before you read it. For each expert, tell me when they last confirmed availability, whether that was only the availability survey, who their backup is, and what I should do next. Flag anyone with no backup and any backup listed for more than one person. Use only my roster and the secretariat report at https://documents.un.org/api/symbol/access?s=FCCC/PA/CMA/2026/10&l=en&t=pdf. Quote the report's line on when the team must be formed and its line on why experts decline. If you cannot open the report, say so and do not answer those points from memory.
