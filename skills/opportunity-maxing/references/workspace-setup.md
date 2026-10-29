# Workspace setup

Everything the user sees lives in their own Google Workspace. Build exactly this, in this order, and keep every name as written so later runs can find things by name.

## 1. Drive folder

```
Opportunity Maxing/                      (folder, in My Drive)
├── Opportunity Maxing Tracker           (Google Sheet)
├── My Opportunity Profile               (Google Doc)
├── Applications/                        (folder: one subfolder per opportunity the user tracks)
└── Documents/                           (folder: CVs, transcripts, certificates, headshot)
```

If a folder named `Opportunity Maxing` already exists, use it. Never create a second one.

## 2. The tracker sheet

Create the tabs in this order. Create a category tab only if the user ticked that category.

| Tab | When | Purpose |
|---|---|---|
| Start Here | always | How to use the sheet, in five lines |
| Setup | always | What the user is hunting and how often (the skill reads this every run) |
| Opportunities | if any of scholarships, fellowships, programmes, conferences, grants, awards, accelerators, short courses is ticked | Everything that is not a job or a hackathon |
| Hackathons & Challenges | if hackathons or competitions is ticked | Builds, prize challenges, pitch competitions |
| Jobs | if jobs or internships is ticked | Roles |
| Log | always | One row per hunt run |

Formatting for every data tab: freeze row 1 and the first 3 columns, bold header, wrap text, filter on the header row, a dropdown (data validation) on Fit, Track? and Status. Colour the header of the user columns green (`#B7E1CD`) and every other header grey (`#E8EAED`). Green means "yours: the hunter reads it but never writes it".

### Start Here (A1:A6)

```
Opportunity Maxing: your opportunities, checked every few days.
1. Green columns are yours. Type Y in "Track?" for anything you want to go for.
2. Add notes in "My notes" (e.g. "need a referee", "skip, too far"). The hunter reads them.
3. Grey columns are filled by the hunter. Edit them if something is wrong; it will re-check.
4. Fill in "My Opportunity Profile" (Google Doc) a little at a time. Better profile = better matches.
5. Nothing is ever submitted for you. You apply; the hunter prepares.
```

### Setup

Two columns, `Setting` and `Value`. The user edits Value.

| Setting | Value (example) |
|---|---|
| Hunting: Jobs | Y |
| Hunting: Internships | N |
| Hunting: Scholarships | Y |
| Hunting: Fellowships & leadership programmes | Y |
| Hunting: Hackathons | Y |
| Hunting: Competitions & prize challenges | Y |
| Hunting: Accelerators & startup programmes | N |
| Hunting: Conferences & speaking (funded) | Y |
| Hunting: Grants | N |
| Hunting: Short courses & certifications (funded) | N |
| Hunting: Awards | N |
| Fields / themes | AI, data, education |
| Where I can go | Online; Africa; anywhere if funded |
| Places to avoid | |
| Home time zone | Africa/Harare |
| Funding rule | Fully or mostly funded only |
| Check every | 2 days |
| Digest email | (the user's own address) |
| Add tracked deadlines to Calendar | Y |
| Profile doc link | (filled by setup) |
| Folder link | (filled by setup) |

### Opportunities: columns A to T

| Col | Header | Who | Notes |
|---|---|---|---|
| A | ID | hunter | `OPP-001`, `OPP-002`, … never reused |
| B | Opportunity | hunter | Official name and intake/year |
| C | Type | hunter | Scholarship, Fellowship, Programme, Conference, Grant, Award, Accelerator, Course |
| D | Organizer | hunter | |
| E | Link | hunter | Official page only, never an aggregator |
| F | Next deadline | hunter | Date in the user's home time zone |
| G | Deadline note | hunter | Original time and zone plus the converted time, e.g. "11:59 PM EDT = 05:59 on 27 Oct, Harare" |
| H | Format / location | hunter | Online, hybrid, in person + city |
| I | Funding | hunter | What is covered and what is not (flights, visa, fees) |
| J | Eligibility | hunter | Age, nationality, degree, experience, language |
| K | Fit for me | hunter | Strong / Possible / Weak / Not eligible |
| L | Why / gaps / info needed | hunter | One or two lines, quoting the profile |
| M | What the application needs | hunter | Essays, references, video, transcripts, fee |
| N | Prep days needed | hunter | Honest estimate |
| O | Start prep by | hunter | `= F - N` |
| P | Track? (type Y) | **user** | green |
| Q | Status | hunter | New / Watch / Preparing / Applied / Result / Closed / Skipped |
| R | My notes | **user** | green |
| S | First seen / Last checked | hunter | `2026-10-16 / 2026-10-29` |
| T | Source | hunter | Where it was found, e.g. "official site", "web search", "user added" |

### Hackathons & Challenges: columns A to W

ID (`HCK-001`), Challenge, Type (Hackathon / Prize challenge / Pitch competition / Bounty), Themes, Organizer, Link, Next deadline, Deadline note, Event / submission dates, Format / location, Team or solo, Prizes / funding / travel, Eligibility, Fit for me, Why / gaps / info needed, What the entry needs, Prep days needed, Start prep by, **Track? (type Y)**, Status, **My notes**, First seen / Last checked, Source.

### Jobs: columns A to S

ID (`JOB-001`), Role, Company, Link, Location / remote, Work rights needed, Seniority, Pay (if listed), Posted, Closes, Fit for me, Why / gaps, What to send, **Track? (type Y)**, Status (New / Preparing / Applied / Interview / Offer / Rejected / Closed / Skipped), **My notes**, First seen / Last checked, Source, Draft docs.

### Log

Date, Categories searched, Searches run, New added, Re-checked, Closed or past deadline, Errors, Digest sent (Y/N).

## 3. My Opportunity Profile (Google Doc)

Create it from `templates/profile-doc.md`. Headings become Heading 2, the hints stay as normal text, and every answer starts as `TBC`. If the user pasted details into the prompt or chat, put them under the right heading and leave the rest as TBC.

## 4. Calendar (only if the Setup value is Y)

For rows the user marked `Track? = Y`: one all-day event "Start prep: {name}" on Start prep by, and one event "DEADLINE: {name}" at the deadline in the home time zone, with the official link in the description. Never create events for untracked rows. Update the event if the deadline changes; delete only events this skill created.

## 5. No write access?

If the connectors cannot create files, do not stop. Produce, in chat:
1. one CSV header line per tab (copy from above), with the exact tab name above each,
2. the profile doc text,
3. five numbered steps: create the folder, a blank sheet, import each CSV as a new tab, create the doc, paste the links back into chat.
Then continue the hunt from what the user pastes back.
