# How to hunt

One hunt run = read, re-check, search, score, write, tell. Keep each run small: quality over volume.

## 1. Read first

1. The `Setup` tab: which categories are `Y`, fields, regions, funding rule, home time zone.
2. Every data tab, all rows. Note the green columns (`Track?`, `My notes`) on each row and act on them:
   - `Track? = Y` and Status is New or Watch → set Status `Preparing`, create `Applications/{ID} - {name}/` with a "Plan" doc (see section 6), add Calendar events if Setup allows.
   - `My notes` says skip / not interested / no → Status `Skipped`.
   - `My notes` gives new facts ("I have a referee now", "I'm 31") → use them in the fit check. If they belong in the profile, say so in the digest; never edit the profile doc yourself unless the user asks.
3. `My Opportunity Profile`. Treat `TBC` as unknown, not as "no".

## 2. Re-check what is already there

For rows with Status New, Watch or Preparing:
- Deadline passed → `Closed`, and note "Closed {date}". If it was tracked, ask in the digest whether they applied.
- Reopen the official link for anything with a deadline in the next 21 days; update deadline, funding and eligibility if they changed, and say what changed in Notes.
- Update `Last checked`.

## 3. Search

Only for the categories ticked in Setup. Per run, about 4 searches per category, at most 8 new rows per category. Mix:
- the user's fields and themes + the category + the current and next year ("AI fellowship 2027 Africa fully funded"),
- eligibility hooks from the profile (nationality, age band, women in tech, region, language),
- known recurring programmes in the field that may have reopened.

Category hints:

| Category | Look for | Must capture |
|---|---|---|
| Jobs / internships | Company career pages, ATS boards (Greenhouse, Lever, Ashby, Workable), official listings | Work rights, location, posted date, closing date |
| Scholarships | University and government pages, foundation pages | Level, field, what is covered, age and nationality rules, test scores |
| Fellowships / programmes | Programme's own site | Length, stipend, time commitment, cohort dates |
| Hackathons | Devpost, MLH, lu.ma, organiser pages | Themes, team rules, submission deadline, prizes, what the entry needs |
| Competitions / prize challenges | Organiser page | Stage required (idea / prototype / revenue), prize, finals location and travel |
| Accelerators | Accelerator's apply page | Equity taken, stage, location, dates |
| Conferences / speaking | CFP pages, Sessionize, scholarship or travel grant pages | CFP deadline, travel support, format |
| Grants | Funder page | Amount, who can apply (individual / org), reporting |
| Courses / certifications | Provider page | Cost after funding, length, certificate |
| Awards | Organiser page | Nomination vs self-apply, criteria |

## 4. Verify before adding

Add a row only when:
- you opened the **official** page (aggregators are fine for discovery, never as the Link),
- the deadline is in the future or rolling,
- the user is not clearly ineligible (if clearly ineligible, skip it; if unsure, add it as `Possible` and say what to check).

Red flags: an application fee for a "scholarship", requests for bank details or passport numbers, no named organiser, guaranteed visas or jobs, Telegram/WhatsApp-only contact. Don't add these; mention the count as "scams skipped" in the Log.

Duplicates: same organiser and same intake = same row. Update it instead of adding.

## 5. Score fit

| Fit | Means |
|---|---|
| Strong | Meets every stated requirement from the profile and matches goals or fields |
| Possible | Meets most; one gap or one unknown (TBC) that the user can check |
| Weak | Eligible but a poor match for goals, or a long shot |
| Not eligible | Fails a hard rule (age, nationality, degree, work rights). Add only if the user asked for this kind specifically; otherwise skip |

`Why / gaps / info needed` quotes the profile: "Eligible: born 1998, under 35. Gap: needs 2 referees, profile §11 is TBC."

Prep days: 1–2 for a form, 3–5 with essays, 7–14 with references, a video or a working build. `Start prep by = deadline − prep days`.

## 6. Preparing a tracked opportunity

In `Applications/{ID} - {name}/` create a Google Doc "Plan - {name}":
- checklist of everything the application needs, with dates counted back from the deadline,
- for each essay question: which essay-bank entry to start from and what to change (do not write the essay),
- facts from the profile that answer each form field, and the TBCs the user must fill,
- for hackathons: a build plan sized to the time left and the judging criteria,
- the official link and the exact deadline in both time zones.

For jobs, also a tailored CV draft and a cover letter draft as Google Docs, using only what is in the profile. Never invent experience, numbers, or titles.

## 7. Write and tell

1. Write new and changed rows. Never touch green columns. Keep IDs in order.
2. Add one row to `Log`.
3. Send the digest (see `digest.md`) only if something needs the user: new Strong or Possible rows, a tracked deadline inside 7 days, a start-prep date today or past, or a question.
