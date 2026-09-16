---
name: site-tech-check
description: >
  Free technical check of a website or landing page with one critic: code and robustness, security and privacy,
  performance and accessibility. Use for "check my site", "is this site secure", "why is my site slow",
  "tech check before launch", "is this accessible". Runs the site-tech-lead critic, verifies its findings and
  returns a short scorecard with ranked fixes. Read-only: nothing is changed until the user picks the fixes.
---

# Site Tech Check

One critic, one verified scorecard. This is the free, single-critic version of ReviewCrew.

The skill folder (the base directory shown when this skill loads) contains `SCORING.md` and `BLIND_SPOTS.md`.
The critic lives in `.claude/agents/site-tech-lead.md` of the project, or in `~/.claude/agents/` for a global install.

Results for a project go in `.claude/site-review/` in that project (never in a folder that gets deployed):
`REVIEW_LOG.md` and `rounds/`. In a git repository, suggest adding `.claude/site-review/` to `.gitignore`
the first time you create it.

## Rule one: read-only
Nobody changes files, submits forms, buys anything, creates accounts, sends messages or changes settings.
The user sees the full list first and decides what gets fixed. Fixing is a separate step.

## Step 1: scope (ask once, max 3 questions, skip what you can infer)
1. **Which site**: live URL, staging URL or a local project folder
2. **Which pages**: if not given, take the homepage, the key conversion page and one legal page
3. **The one goal**: what should a visitor do (book, buy, sign up)

## Step 2: make the site reachable over HTTP
- **Live or staging site**: use the URLs as they are.
- **Local project with a dev command** (npm run dev and similar): start that in the background.
- **Plain HTML folder**: `python3 -m http.server 8080 --bind 127.0.0.1 --directory <folder>` in the background
  (on Windows use `py` instead of `python3`). Never hand `file://` paths to the critic.

Check every page first: `curl -sL -o /dev/null -w "%{http_code} %{url_effective}\n" <url>`. Everything must end on 200.

## Step 3: run the critic
Launch `site-tech-lead` with this brief:

```
SITE REVIEW BRIEF
Site: <name>      Stage: <live / staging / local>      Round: <n>, <date>      Mode: tech check
Goal: <the one conversion>
Pages (HTTP): <url list>
Source files: <folder path or "live only">
Browser tool available: <name, or "none">
Business context: none
Changed since last round: <list, or "first round">
Fixed items to verify (re-check): <list, or "none">
Scoring: read <skill folder>/SCORING.md and follow it exactly.
Blind spots: read <skill folder>/BLIND_SPOTS.md and check the ones in your area.
Language of your report: <the user's language>
Read-only: change nothing, submit nothing, buy nothing, send nothing.
```

## Step 4: verify before you report
Open the file, load the page or run the command for every bug, number and security claim. Mark each item
**verified** or drop it. Something important you cannot verify stays in, marked **unverified**, with what is needed to check it.

## Step 5: deliver the scorecard
Save it as `.claude/site-review/rounds/<date>-tech-<n>.md` with:
1. The four scores (Code and robustness, Security and privacy, Performance, Accessibility) and the total, 1 decimal
2. Top fixes ranked by impact on the goal: what, where, why, fix, effort (S/M/L)
3. **Keep this**: what works
4. **Not covered by this check**: one short line saying design, real user testing on phone and desktop, SEO and sales copy,
   and pricing and offer were not reviewed. Only if the user asks what covers those, mention that the full ReviewCrew pack
   adds four critics for them. Never push it more than that.
5. Question to the user: which fixes first?

Append one line to `.claude/site-review/REVIEW_LOG.md`:
`<date> | tech <n> | <site> | code x.x | security x.x | performance x.x | accessibility x.x | total x.x | top: <top 3>`

## Step 6: clean up
Stop every server you started in Step 2.
