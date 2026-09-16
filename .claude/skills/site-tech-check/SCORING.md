# Scoring rules

The same scale, severity levels and evidence rule as the full ReviewCrew pack, so scores compare across rounds
(and with the other four critics if you add them later).

## The scale (per dimension, whole numbers)
| Score | Meaning |
|---|---|
| 1-3 | Broken. Blocks the goal, or creates legal, security or data risk |
| 4-5 | Works, but loses a large share of visitors or trust |
| 6-7 | Decent, with clear leaks that cost conversions |
| 8 | Solid. Nothing important missing. This is the bar for "ready" |
| 9 | Excellent. Better than most competitors in this market |
| 10 | Best in class. Rare. Needs a specific reason |

- Total per critic = average of that critic's dimensions, 1 decimal.
- Overall = average of the critic totals that ran, 1 decimal. A quick round says so next to the overall score.
- Every dimension below 8 gets a line **"To reach 8:"** with concrete, doable steps.
- A score without a reason does not count. One sentence per score is enough.

## Dimensions per critic
| Critic | Dimensions |
|---|---|
| site-tech-lead | Code and robustness, Security and privacy, Performance, Accessibility |

## Severity (per finding)
- **CRITICAL**: blocks the goal, breaks on a main device, loses data, creates legal or security exposure, or
  contradicts a promise (price, delivery, refund) between pages
- **IMPORTANT**: a measurable leak in conversions, trust or findability
- **MINOR**: polish

## Evidence rule (no evidence, no finding)
Every finding includes:
- **Where**: URL plus selector, visible text, or file and line number
- **Proof**: a quote of the exact text, the command and its output, or what you saw at which viewport width
- **Why it matters** for this site's goal, in one sentence
- **Fix**: concrete enough to act on, plus the owner: tech, design, copy, or owner (only the site owner can do it)
- **Effort**: S (under an hour), M (a few hours), L (a day or more)

## Honesty rules
- Never invent numbers: search volumes, conversion rates, market sizes, load times. Measure it, cite the
  source, or label it clearly as an estimate.
- Say explicitly what works and must stay, so the next round of changes does not break it.
- Do not re-report items the brief lists as fixed, unless you can show they are still broken.
- Stay in your own area. If you notice something in another critic's area, add it in one line under
  "For other critics" instead of scoring it.

## Report skeleton (every critic)
```
<CRITIC NAME> REVIEW: <site>
SUMMARY: <2 sentences>
FIX CHECK (re-review only): per fixed item: fixed / partly / not fixed / broke something else, with proof
SCORES: <dimension: score, reason> ... TOTAL: x.x
WORKS (keep): 2-5 points
FINDINGS: ranked, CRITICAL first, each with Where / Proof / Why / Fix / Owner / Effort
TO REACH 8: per dimension below 8
FOR OTHER CRITICS: optional, one line each
ASSUMPTIONS: anything you assumed because data was missing
```
