# Custom Instructions -- career-ops

<!-- ============================================================
     THIS FILE IS YOURS. It will NEVER be auto-updated.

     Put your own house rules, custom workflows, and automations
     here -- anything you want the agent to ALWAYS do (or never do).

     This is for PROCEDURAL rules ("HOW I want things done").
     For WHO you are (archetypes, narrative, comp, negotiation),
     use modes/_profile.md instead. Keeping the two separate keeps
     each one readable.

     The agent reads this file alongside the system instructions;
     your rules here take precedence over the defaults, as long as
     they don't break the Data Contract (your files are never
     touched, and we never auto-submit an application for you).

     Because this is a user-layer file, anything you write here
     survives `node update-system.mjs`. Put customizations HERE,
     not in CLAUDE.md / modes/_shared.md / other system files --
     those get overwritten on update.
     ============================================================ -->

## House Rules

<!-- Rules the agent should always follow. Examples:
     - Always write evaluation summaries in British English.
     - Never include a photo in my CV (US / ATS-first market).
     - Cap each batch run at 20 listings unless I say otherwise.
     - If a report scores below 6, skip the cover letter. -->

- Always build CV/PDF HTML from `templates/cv-template.resume.html` (pass it as the third arg to `node build-cv-html.mjs`). Never use `templates/cv-template.html` (base) for CVs.
- Resume layout is fixed: header → Professional Summary → Skills → Work Experience → Projects → Education → Awards & Honors. Skills always immediately after Summary. Do not reorder sections.
- Always generate a FULL PAGE resume: exactly 1 page (A4), with content filling the page down to the bottom margin (aim ~88-95% of usable page height, ending near y≈780-795 of 842pt). The template is tuned so 10 ION bullets + Holisol + 3 projects + 4 awards fill exactly one page.
- Always include all 10 ION Trading experience bullets, 3 projects, and 4 awards (sourced from `cv.md`).
- Awards & Honors table format (2-column layout):
  1. Title: "Winner - IONathon XTP 1.0", Org (Col 2): "ION Trading"
  2. Title: "Top 0.1% Performer", Org (Col 2): "ION Trading"
  3. Title: "Inspire Program Fellow", Org (Col 2): "Government of India (Outstanding Academics in Xth Standard)"
  4. Title: "99.9 Percentile", Org (Col 2): "JEE Advanced" (JEE Advanced is an AWARD in Column 2, never education).
- Never include a Core Competencies section (redundant with Skills). Remove from the template and JSON payload.
- Always keep resume strictly to 1 page. Keep content concise and use the compact template spacing tuned in `templates/cv-template.resume.html`.
- **Bold impact numbers** in all resume bullets: any quantified result (e.g. **20x**, **90%**, **35%**) must be wrapped in `**…**` in the JSON payload so it renders bold in the PDF.
- **Referral-first, apply-later approach (since 2026-08-29):** for target companies, reach out to recruiters/contacts on LinkedIn for a referral BEFORE submitting an application. Do NOT contact multiple people at the same company simultaneously — space outreach by 3 working days. Record every outreach in `data/contacts.tsv` (name, company, channel, date, role).
- **Resume project links (since 2026-09-11):** project headings carry the link themselves (`### [Name](url)` in cv.md, `url` field in the PDF payload) — never bare URLs in body text. Link style: inherit title color, no underline, open in new tab (enforced in `templates/cv-template.resume.html` `.project-title a` CSS + `build-cv-html.mjs` project renderer `target="_blank"` — both are system files, so re-apply if a career-ops update reverts them).
- **Resume header portfolio label (since 2026-09-11):** show linked text `Portfolio` (from `portfolio_url` in profile.yml), never the raw URL.
- **Resume project badges (since 2026-09-11):** every project header carries a badge — `Open Source` (public systems repos like TailCache), `AI Application` (applied AI builds), `Published Research` (peer-reviewed work like HSGO).
- **Resume full-page fill (since 2026-09-11):** every PDF must fill ~92–95% of the usable page height (template tuned: 10.5px bullets/1.42 line-height, 10.5px summary/project text). Always render-check the PDF (`pdftoppm` → view) before delivery: 2 pages means dial back, visible bottom whitespace means dial up.

## Custom Workflows

<!-- Multi-step routines you run often, given a short name. Examples:
     - "weekly review": scan my saved portals, evaluate the new roles,
       then give me a one-paragraph summary of the top 3.
     - "prep <company>": pull the JD, generate STAR stories from
       article-digest.md, and draft 5 likely interview questions. -->

- **"outreach follow-ups"**: after any referral-first outreach (logged in `data/contacts.tsv`), wait 3 working days before any follow-up at the same company. On no response: send Deepak Yadav (Amex) and Sahil (BlueOptima) a LinkedIn connection request (they got InMail first); approach Moody's secondary contact Aksha; for NeoXam, approach a technical leader only after Anand and Surabhi have had time to respond. Never contact 2 people at the same company on the same day. When reporting outreach, distinguish NEW contacts from people already approached, and surface follow-ups only when due.

## Output Preferences

<!-- How you like results formatted. Examples:
     - Reports: lead with the score and the one-line verdict.
     - Show the per-step token breakdown after a batch run.
     - Save PDFs date-first: YYYY-MM-DD-company.pdf -->

(none yet -- add yours above)

## Off-Limits

<!-- Things the agent must never do for you. Examples:
     - Never auto-fill or submit an application without showing me first.
     - Never edit a system file to customize my setup -- put it here. -->

(none yet -- add yours above)
