# Mode: instahyre — Instahyre Opportunity and Application Assistant

Use this mode when the user asks to review or apply to a named job on Instahyre.
Instahyre is a logged-in, browser-based opportunity marketplace. This mode is
separate from `apply`, which is designed for employer ATS forms.

## Safety and scope

- **Scope — Opportunities tab only:** This mode works exclusively with jobs in
  the Opportunities tab at `/candidate/opportunities/` (the recommended/matching
  list). Do NOT use the "Search other jobs" search panel, do NOT browse company
  job listings, and do NOT apply through global job search. Only jobs that appear
  in the Opportunities tab may be reviewed or applied to.
- Use Playwright only in the visible browser session. Never request, store, or
  repeat passwords, one-time codes, or session cookies.
- If Instahyre is logged out, navigate to the sign-in page and wait for the user
  to authenticate. Do not fill credentials unless the user supplies them for
  this session.
- Read the selected opportunity's company, title, location, experience range,
  description, requirements, and visible skills before applying.
- Surface material fit gaps, especially experience, location, authorization,
  compensation, and required technologies. Do not reject the user's choice,
  but make the mismatch clear.
- Only click Instahyre's `Apply` button after the user explicitly names the
  listing or says to apply. Do not click `Apply on company site`, external
  submission buttons, or any final employer-portal submit control in this mode.
- Stop after Instahyre confirms the application. Dismiss premium/share prompts
  without accepting paid upgrades or sharing personal information.

## Resume

Use the generic resume for Instahyre unless the user asks for a tailored one:

`output/cv-asu-singh-generic-2026-07-20.pdf`

If that file is missing or stale, run the PDF workflow first. Never replace the
generic resume with a role-specific CV without telling the user.

## Workflow

1. Open `https://www.instahyre.com/` or inspect the active Instahyre tab. Stay on
   the Opportunities tab (`/candidate/opportunities/`).
2. If logged out, stop at the login screen and ask the user to authenticate.
3. Work only with the opportunities listed in the Opportunities tab. Do not use
   the "Search other jobs" panel and do not
   click `Not interested` while searching.
4. Open the opportunity card, take a Playwright snapshot of the full detail
   modal, and summarize the role and fit.
5. If the user has not explicitly authorized this named listing, stop and ask
   whether to click `Apply`.
6. Click only the opportunity modal's Instahyre `Apply` button.
7. Confirm the resulting state. A successful application is indicated by the
   opportunity changing state and/or the Instahyre confirmation/share prompt.
8. Dismiss the share/premium prompt with `No thanks` when available.
9. Record every confirmed Instahyre submission as `Applied` with the tagged
   channel `via=Instahyre` through the TSV/merge workflow before reporting
   completion. Use `N/A` for the score when no evaluation report exists; never
   invent a score or hand-edit `data/applications.md`.
10. Report the company, title, location, material fit gaps, submission status,
    tracker result, and resume path used. Never claim an external employer
    application was sent unless the external site itself confirms it.

## Tracking

Do not hand-edit `data/applications.md`. Every confirmed Instahyre submission
must be tracked. If there is an existing evaluated report, update its status
through `set-status.mjs` and preserve the channel as `via=Instahyre`. If there
is no report, create a properly numbered backfilled tracker addition through
the TSV/merge workflow with `Applied`, `N/A`, and `via=Instahyre`; never invent
a score.
