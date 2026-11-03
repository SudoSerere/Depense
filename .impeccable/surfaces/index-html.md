---
version: 1
slug: "index-html"
primary_target: "index.html"
related_targets: []
---

## Scope & mode

Full-page redesign of `index.html` (the entire app, single surface). Mode: Operate.

## Audience, job, action, proof, constraints

Single personal user, desktop-first, checking their own monthly budget: salary in, expenses logged per category, what's paid vs. owed, savings left. No external audience, no sharing. Constraint: stays a single static HTML file, fully usable offline (localStorage), optional GitHub sync as an additive layer — never required.

## Direction contract

**THESIS:** This is the household ledger-and-wall-planner the French budgeting ritual already runs on, rebuilt as a screen — not another neutral SaaS dashboard with a lone accent color standing in for personality. It refuses the "grey cards, one accent" default (which is also, not coincidentally, what the current build already is) and refuses the warm-cream-serif AI-interface default too.

**OWN-WORLD:** Committed color strategy, one saturated ink carrying the shell: a deep postal/ballpoint blue (`#1C3F6E`-family) owns the header band, category dividers, borders, and primary numerals — not a thin accent line but a real structural color. Ground is crisp paper white (`#FCFBF8`-ish, cool, not the cream cliché), body ink is graphite (`#23262B`), ledger rule-lines in a muted blue-grey. Red (`#B4302A`-family) is reserved strictly for unpaid/due state — never decorative. Two type voices with a functional reason each: Inter for UI chrome, labels, and body (workhorse, already in place, no reason to swap for an Operate surface); IBM Plex Mono for every amount and numeral column, tabular-aligned like a real ledger's figure column — this is the one borrowed "point-of-view" face, justified by the ledger-column function, not decoration. Density: tighter row rhythm than a typical consumer app, ruled like account-book lines.

**STORY:** Visitor opens the page and reads, in order: what month/moment this is, the headline numbers (spent / reste à payer / épargne), then the ledger itself by category. Checking an expense "paid" reads like a ledger entry being settled — a stamped tick, not a flat checkbox. The unpaid total in red is the one number demanding action; everything else is calm structure.

**FIRST VIEWPORT:** A full-width ink-blue header band carries the product name and the current month in large tabular numerals (a "cahier de [Mois]" register line), not a generic page title. Below it, the summary strip (total / reste à payer / épargne / count) reads as a ledger's running totals row — ink-blue rules, mono figures, red only on what's owed. The sidebar (salary input, new-expense form, GitHub sync) sits as a left ledger margin/tab column; the category ledger occupies the dominant right region, each category a ruled page with a small corner tab bearing its name, rows as ledger lines with a stamp-style paid mark.

**FORM:** Candidate 7 of my ordered list of seven ("the household wall-calendar/ledger register"), assigned by the direction roll (degraded — roll service unreachable from this session, no network egress to impeccable.style permitted; proceeding on grounded candidates alone, confirmed with the user via the structured-question fallback in place of the decision page). seed: 7bc78737ef3d1fa4

**FINISH:** unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance.

## Unresolved decisions

None outstanding — user confirmed the assigned direction over the pick (Minitel) and the standing exit (generic dashboard).
