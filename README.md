# Measuring Automation in AI Safety Research (Jotform version)

Live page: https://arcadiaimpact.github.io/automation-survey/
Form itself: https://form.jotform.com/262794266723063

## How this works

The survey lives in **Jotform** (form `262794266723063`, owned by the Arcadia Impact Jotform account).
Jotform stores the questions, the logic, the styling and every response.

This repo does two things:

1. `index.html` shows the Jotform full-screen on GitHub Pages, so the old survey link keeps working.
2. `jotform/` keeps a copy of everything we customised inside Jotform, so it can be restored or reviewed.

Responses are **not** stored here. See them in Jotform under **My Forms → Submissions** (Jotform Tables):
https://www.jotform.com/tables/262794266723063

The previous hand-built survey (custom page + Cloudflare Worker + Apps Script → Google Sheet) is in
[`ArcadiaImpact/automation-survey-custom`](https://github.com/ArcadiaImpact/automation-survey-custom).
It does not receive Jotform responses.

## Files

| File | What it is | Where it goes in Jotform |
|---|---|---|
| `index.html` | Full-screen embed of the form for GitHub Pages | — |
| `jotform/custom.css` | All Arcadia branding: colours, fonts, top bar, pill buttons, ticks, tables, tooltip, thank-you page | Form Designer → Styles → Inject Custom CSS |
| `jotform/thank-you.html` | Thank-you page content | Settings → Thank You Page (see warning below) |
| `jotform/form-structure.md` | Pages, questions and the points-total calculation, for reference | — |

## Things that are easy to break

- **Don't open Settings → Thank You Page in the Jotform editor.** Just opening it makes Jotform replace
  the custom thank-you HTML with its default template and auto-save. If that happens, paste
  `jotform/thank-you.html` back (Source/HTML view) or ask Claude to restore it via Jotform's API.
- **Task descriptions under each table row are added by CSS, by row position.** If you add, remove or
  reorder task categories in either table, update the six `nth-child(...)` lines in `custom.css` ("fixes 3").
- **Field IDs are hard-coded in the CSS**: `#id_33` (points table), `#id_26` (hours table), `#id_22` (total).
  If those fields are deleted and re-created, their IDs change and those rules stop applying.
- **The "Arcadia Impact" link on the top bar** is a hidden text element at the top of each of the 5 pages
  (`brandBar1`–`brandBar5`), pinned over the bar by CSS. Keep one at the top of any new page you add.
- **Changing the theme in Jotform's Form Designer** may regenerate Jotform's part of the CSS. Our part
  (after Jotform's `/*__INSPECT_SEPERATOR__*/` marker) should survive; if the fonts look wrong, re-check.

## Hosting

GitHub Pages serves `index.html` from the `main` branch root. To change the page, edit `index.html`, commit
and push; Pages redeploys in about a minute.
