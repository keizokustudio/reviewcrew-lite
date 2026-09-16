# ReviewCrew Lite

A free technical website check for Claude Code. One specialist critic reviews your site for code problems,
security and privacy basics, performance and accessibility. Claude verifies every finding, then gives you
a scorecard with ranked fixes. It reads everything and changes nothing.

**New to this? Open `QUICKSTART.pdf`** for install, a one-minute check and your first run.

## What you get
- `site-tech-check` skill: scopes the check, runs the critic, verifies findings, saves a scorecard and a log
- `site-tech-lead` agent: four areas, each scored 1 to 10 with proof for every finding
  - Code and robustness: console errors, broken links, forms, HTML basics
  - Security and privacy: exposed secrets, HTTPS, security headers, trackers, form data
  - Performance: page weight, images, fonts, render-blocking files
  - Accessibility: contrast, keyboard use, alt text, tap targets (WCAG 2.2 AA basics)
- `SCORING.md`: the 1 to 10 scale, severity levels and the "no evidence, no finding" rule
- `BLIND_SPOTS.md`: technical issues reviews miss again and again

## Install
**One project:** copy the `.claude` folder into the root of your project. Already have a `.claude` folder? Copy
`skills/site-tech-check` into its `skills` folder and `agents/site-tech-lead.md` into its `agents` folder.

**All projects:** copy `skills/site-tech-check` into `~/.claude/skills/` and `agents/site-tech-lead.md` into
`~/.claude/agents/`.

Start a new Claude Code session so they load.

## Use
- "Run a tech check on https://example.com, the goal is booking a call"
- "Check the site in ./site for security and performance before I launch"
- "Check the tech fixes again, we fixed items 1 to 3"

## Built-in rules
- Read-only: the critic can only read, search and fetch. File-editing tools are blocked for it
- No evidence, no finding: every finding has a location, proof, a fix and an effort estimate
- Claude verifies findings before you see them
- No invented numbers: load times and sizes are measured or marked as not measured
- Advice, not a security or accessibility compliance audit

## Want the whole crew?
This is one of the five critics from **ReviewCrew**. The full pack adds a design critic, a hands-on user tester
(phone and desktop), a growth and SEO critic and a business critic, runs all five in parallel and merges them
into one ranked scorecard. In a test on a demo site with 26 planted issues, one full round found all 26.

ReviewCrew on Gumroad: https://keizoku.gumroad.com/l/reviewcrew?utm_source=github&utm_medium=readme&utm_campaign=lite

## License
MIT, see `LICENSE`. The full ReviewCrew pack has its own license.
