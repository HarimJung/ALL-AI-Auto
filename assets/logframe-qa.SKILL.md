---
name: logframe-qa
description: Check a user's own results framework or logframe line by line and say whether each line labelled as an outcome reads as an outcome or as an output with a new label. Each verdict gives a short reason, and background on why this happens is quoted from a Joint Inspection Unit report. Use when someone asks whether the outcomes in their logframe are really outputs, or wants them reworded before a progress report.
---

# Logframe QA

Your own results framework in, a verdict on every outcome line out. Each verdict rests on your document's words and on the control question below.

**Inputs**
- `document`: required. The user's own results framework or logframe, pasted or attached. Only the lines to check are needed.
- `team`: optional. What the team delivers with its own resources, for example workshops or guidance notes. It helps decide which lines the team controls.

## Why this exists

Results frameworks often call something an outcome when the team can deliver it alone. A workshop held is in the team's control. What participants do afterwards is not. A Joint Inspection Unit report on results-based management found that organizations focus on outputs they control and sometimes label them outcomes. It links this to how the accountability system works. The same report names the pressure to report outcomes every reporting cycle, even when outcomes take longer than a cycle to appear. An output with an outcome label makes a report claim a change that nobody has shown.

## Sources (use these and nothing else)

| Document | What it holds | File |
|---|---|---|
| Joint Inspection Unit report on results-based management | Summary of challenges, where outputs the organization controls get identified as outcomes. A later list of challenges, where staff face pressure to report on outcomes every reporting cycle | `https://www.unjiu.org/sites/www.unjiu.org/files/jiu_rep_2017_6_english__0.pdf` |
| The user's own document | The lines to check, and any definitions of output and outcome it gives | Pasted or attached by the user |

Find these two passages in the report by searching for their words.
- "identifying those as outcomes, given the nature of the accountability system, as well as"
- "Disconnect between the longer-term outcome requirements of results-based management and the reporting cycle, with pressure to report on outcomes no matter the situation"

If the PDF does not open, say so. Do not fill it from memory or from a search summary. The verdicts can still be given from the user's document alone.

## Steps

- Open the report PDF. Copy its title and document symbol from the cover. Find both passages and check they read as quoted. If the PDF does not open, record `REPORT NOT OPENED` and go on.
- Read the user's document. If it defines output and outcome, copy those definitions and use them in place of the control question. Say that you did.
- List every line the document labels as an outcome. Keep its exact words. If the document has no labels, ask the user which lines are meant as outcomes.
- Put the control question to each line. Could the team finish all of its own work and this line still not be true? If yes, the line reads as an outcome. If no, the team controls it and it reads as an output.
- If the document does not say who has to change, or what the team delivers, mark the line `UNCLEAR` and name the missing piece.
- For each output labelled as an outcome, write a rewrite that names the change the output should lead to. Use an actor the document already names. If it names none, write `ACTOR NOT IN DOCUMENT`. Keep the original line in the framework as an output.
- If the report opened, add the first passage as the reason this pattern is common. Add the second passage only when the user mentions pressure to report outcomes every cycle.

## Answer layout

```
<document name> · checked <today's date>
Report: opened, "<title from cover>"      (or REPORT NOT OPENED and why)
Test used: the control question           (or the document's own definitions, quoted)

| Line as written | Labelled | Reads as | Reason |
|---|---|---|---|
| "<line>" | outcome | OUTPUT | The team delivers this with its own work. |
| "<line>" | outcome | OUTCOME | It needs <actor> to change. |
| ... | | | |

Rewrites: <each OUTPUT line, then a rewrite that names the actor and the change>
Why it happens: "<passage>"  JIU report, Summary of challenges
Not covered: <anything asked that the document and the report do not answer>
```

## Rules

- **A verdict rests on the user's document and the control question. Anything said about why the pattern happens is a quoted passage from the report, or it is left out.**
- Quote each line as the user wrote it. Do not tidy its wording in the table.
- Never add a target, baseline, indicator value or date that the document does not contain.
- Keep `UNCLEAR` when the document does not settle it. Do not guess a verdict to make the table look complete.
- If the report did not open, say so at the top and quote nothing from it.
- Do not judge the project or the team. The check is about labels only.
- Use your own working notes, leave out anything marked confidential, and use the AI tool your organization allows.

## Copy-paste prompt (works in any assistant)

> Check the results framework I paste below. For every line labelled as an outcome, tell me if it reads as an outcome or as an output. Use this question. Could my team finish all of its own work and this line still not be true? If yes, it is an outcome. If no, my team controls it and it is an output. If my document defines output and outcome, use those definitions instead. Quote each line as I wrote it and give your verdict with a short reason. Write UNCLEAR where my document does not say enough. For each output labelled as an outcome, suggest a rewrite that names who should change, using only actors named in my document. For background, use only the Joint Inspection Unit report at https://www.unjiu.org/sites/www.unjiu.org/files/jiu_rep_2017_6_english__0.pdf and quote it word for word. If you cannot open it, say so and do not fill from memory. Do not add targets or dates that are not in my document.
