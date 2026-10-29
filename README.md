# Opportunity Maxing

**Your own opportunity hunter, living in your Google Workspace.**

Tell it what you're hunting (jobs, scholarships, fellowships, hackathons, competitions, accelerators, funded conferences, grants, courses, awards) and a little about yourself. It builds a tracker Sheet, a profile Doc and a Drive folder for you, then keeps finding opportunities, checking them on the official page, scoring how well they fit you, and emailing you a short digest. You mark what you want with a **Y**. It prepares; **you apply.**

It started as the tracker I use for my own hunt. This is the version anyone can set up.

---

## Two ways to use it

### 1. Prompt version (no code)

Open [`PROMPT.md`](PROMPT.md), copy the box into Claude, ChatGPT or Gemini (with Google Drive connected), fill in the blanks, send. That's it.

### 2. Developer version (Claude skill)

**Claude Code**

```
/plugin marketplace add DeliaRudy/opportunity-maxing
/plugin install opportunity-maxing@opportunity-maxing
```

Or copy `skills/opportunity-maxing/` into `~/.claude/skills/`.

**Claude.ai / Claude desktop**

Download `opportunity-maxing-skill.zip` from the latest release and upload it under Settings → Capabilities → Skills. Switch on the Google Drive, Gmail and Calendar connectors.

Then say:

```
/opportunity-maxing setup
```

| Command | What it does |
|---|---|
| `setup` | Asks what you're hunting and about you, builds the Drive folder, Sheet and profile Doc, runs a first hunt |
| `hunt` | Re-checks what you have, searches the categories you ticked, scores fit, emails a digest if something needs you |
| `prep OPP-004` | Makes a Plan doc for one opportunity: checklist, dates, which of your facts answer which question |
| `add <link>` | Adds one opportunity you found yourself |
| `status` | What's due in the next 14 days, in chat only |

If your Claude can run scheduled tasks, setup offers to run `hunt` every few days.

---

## What you get in Google Drive

```
Opportunity Maxing/
├── Opportunity Maxing Tracker   (Sheet)
│   ├── Start Here
│   ├── Setup                    ← what you're hunting, how often, where to email
│   ├── Opportunities            ← scholarships, fellowships, conferences, grants…
│   ├── Hackathons & Challenges
│   ├── Jobs
│   └── Log
├── My Opportunity Profile       (Doc you fill in over time)
├── Applications/                (a Plan doc per opportunity you track)
└── Documents/                   (CV, transcripts, certificates)
```

**Green columns are yours** (`Track?` and `My notes`). The hunter reads them every run and never writes in them.

Full layout: [`skills/opportunity-maxing/references/workspace-setup.md`](skills/opportunity-maxing/references/workspace-setup.md)

## Why Google Workspace

- It's where people already are: free, on every phone, nothing to install.
- A Sheet is the right shape for a tracker: filter by deadline, sort by fit, share with a mentor.
- Your data stays in your own Drive, not in a chat history or someone's app.
- It works with whichever AI you use, because the system is the files, not the chat.

## Rules it follows

- Never submits, pays, creates accounts or contacts anyone for you.
- Official pages only; deadlines converted to your time zone.
- Never invents experience. Unknown stays `TBC`.
- Doesn't write your essays unless you ask.
- Skips scams (fees for "scholarships", guaranteed visas).
- Never asks for passport, ID or bank numbers.

## Repository layout

```
opportunity-maxing/
├── PROMPT.md                         prompt version
├── .claude-plugin/                   plugin + marketplace manifest
└── skills/opportunity-maxing/
    ├── SKILL.md                      modes and rules
    ├── references/
    │   ├── workspace-setup.md        folder, tabs, columns, doc, calendar
    │   ├── hunting.md                how a hunt run works
    │   └── digest.md                 the email
    └── templates/
        └── profile-doc.md            "My Opportunity Profile"
```

## Contributing

Ideas for sources, categories or regions are welcome as issues or pull requests. Keep the rules section intact.

## Licence

MIT © 2026 Ruvimbo Delia Hakata. Inspired by [Career-Ops](https://github.com/santifer/career-ops).
