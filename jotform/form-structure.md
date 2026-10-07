# Form structure (Jotform form 262794266723063)

Reference copy of how the form is set up. Jotform is the source of truth; this is for review and rebuilding.

## Page 1 — Intro
- Top-bar link (`brandBar1`) → https://www.arcadiaimpact.org/alignment
- Header: "Measuring Automation in AI Safety Research" / "Arcadia Impact"
- Text: "Why We're Doing This" (opens "We at the Arcadia Impact Alignment Team…", links [1] [2]) and "Dual Use & Privacy"
- Button: **Start**

## Page 2 — Questions
- Email (optional) — hint: "Optional — if you opt in for future communications and surveys."
- Job Title (required, single choice + Other): Fellow · Member of Technical Staff · Research Lead · Programme Manager · Senior Leadership
- Role type (required, single choice + Other): Technical AI Safety · Policy / Governance · Field-building · Grant-making
- Coding experience (required): < 1 year · 1-2 years · 2–5 years · 5+ years
- Describe how you use AIs to help with your work (required, long text)

## Page 3 — Distribute 100 points
- Points table (`#id_33`, Input Table, numeric): one "Points" column, rows =
  Conceptual / strategy work, idea generation · Experiment design · Building experiment infra ·
  Running experiments · Writing / communication · Collaborating
- Total (`#id_22`, read-only, required, min 100 / max 100) — blocks Next unless the points sum to exactly 100
- Condition (Update/Calculate): if the points table is filled →
  Total = `{33_0_0}+{33_1_0}+{33_2_0}+{33_3_0}+{33_4_0}+{33_5_0}`

## Page 4 — Active human time on a recent project
- Instructions text (anchor project, four questions, reminders)
- Hours table (`#id_26`, Input Table, numeric, optional): same six task rows × columns
  Without AI assistance · Using AI tools from 1 year ago (tooltip) · Using current AI tools · Projection 6 months from now
- Notes on your estimates (optional, long text)

## Page 5 — Automation barriers
- What research tasks would be the highest value for you to automate that you currently aren't or can't? (required)
- For the tasks you mentioned above, what's stopping you? … (required, with examples hint)
- How do you keep track of what the agents did? (required)
- Button: **Submit**

## Thank-you page
See `thank-you.html`.

## Known gaps vs. the original custom survey
- Partly filled rows in the hours table are allowed (the original required all four cells once one was filled).
- Answers are not saved as a draft between visits.
- Jotform's free-plan banner shows at the bottom.
