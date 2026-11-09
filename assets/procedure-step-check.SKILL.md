---
name: procedure-step-check
description: Run a procedure-first check on the user's own anonymized timeline of a contested staff decision. Each step is checked against the procedural rules the user supplies, before any merits review. Use when an appeals or legal desk is preparing a case that may reach the ILO Administrative Tribunal and wants to find missed steps early.
---

# Procedure Step Check

One anonymized timeline in, one procedure check out. Every required step is matched to a timeline entry or marked missing. The merits come after.

**Inputs**
- `timeline`: the user's anonymized timeline of the contested decision, one event per line.
- `rules`: the procedural text that applied, pasted from the user's own document. Each step keeps its reference as written there.
- `decision`: optional. One line naming the contested decision.

## Why this exists

Legal desks tend to start with the merits of a contested decision. The Joint Inspection Unit review of UNESCO appeals points to procedure: "Adverse judgments were largely due to procedural noncompliance and legal errors, underscoring the need for strengthened compliance and early dispute resolution." A skipped step is easier to find and fix before a case is argued than after.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| JIU review highlights | The section "Appeals processes and the ILO Administrative Tribunal", with the finding on adverse judgments | `https://www.unjiu.org/sites/www.unjiu.org/files/jiu-rep-2026-1_review_highlights.pdf` |
| The user's own document | The anonymized timeline and the procedural rules text that applied | Supplied by the user |

If the JIU file does not open, say so in the answer and write SOURCE NOT OPENED. Do not quote it from memory or from a search summary. The check still runs on the user's document. If the user gives no rules text, do not supply rules from memory. Write RULES NOT PROVIDED and list only the timeline events.

## Steps

Run these in order.

- **Open the JIU file.** Copy the quoted line and the section heading it sits under. If the file does not open, record that.
- **Screen the user's document.** If it contains names or personal details, stop and ask the user to remove them.
- **List the required steps.** Take each procedural step from the rules text, in its own words. Keep "shall" as required and "should" as expected. Note a time limit only as the rules state it.
- **Match each step to the timeline.** Find the entry that shows the step was done. Quote that entry.
- **Mark a status.** Done when an entry shows it. Missing when no entry shows it. Unclear when the entry is vague. Late when the rules set a time limit and the timeline shows it was passed.
- **List the gaps.** Put Missing, Late and Unclear steps at the top. Name the record that would close each one.
- **Only then turn to the merits.** Say the procedure check is complete and that merits review can start. Do not review the merits inside this skill.

## Answer layout

```
Procedure check · sources read <today's date>
Finding: "<quoted JIU line>"  JIU review highlights, <section heading>   (or SOURCE NOT OPENED)

| Step | Rule says | Timeline shows | Status | Rule reference |
|---|---|---|---|---|
| <step> | "<rule words>" | "<entry>" or none | Done, Missing, Unclear or Late | <reference in the user's document> |

Gaps before merits: <Missing, Late and Unclear steps, with the record that would close each>
Not covered: <anything asked that the opened documents do not state>
```

## Rules

- **Remove names and personal details first. Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.**
- Every required step comes from the user's rules text. Never add a step from memory or from general practice.
- Quote the rules and the timeline. Shorten only by cutting. Never turn a "should" into a "shall".
- A step with no timeline entry is Missing. Do not assume it happened.
- Do not predict how the Tribunal would rule. Do not give a view on the merits.
- If the question needs a rule, a time limit or a form that the user's document does not hold, write NOT IN SOURCE.
- Never invent a number, a time limit or a date.

## Copy-paste prompt (works in any assistant)

> Check the procedure in this anonymized case before any merits review. Here is my timeline and the procedural rules that applied: <paste>. Use only my text and the JIU review highlights at https://www.unjiu.org/sites/www.unjiu.org/files/jiu-rep-2026-1_review_highlights.pdf. List each step the rules require, in their own words. For each step, quote the timeline entry that shows it was done, or mark it Missing, Late or Unclear. Put the gaps first. If you cannot open the JIU file, say so and do not quote it from memory. Do not add rules I did not give you. Do not give a view on the merits or the likely outcome.
