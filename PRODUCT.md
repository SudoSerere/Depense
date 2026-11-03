# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS/JS (single `index.html` file, no framework, no build step). Hosted on GitHub Pages.

## Users

A single personal user (the repo owner) tracking their own monthly budget. No multi-user accounts, no sharing, no auth beyond an optional GitHub personal access token used purely for the owner's own cross-device sync.

## Product Purpose

A personal monthly expense tracker: log a net salary, log expenses against three categories, see at a glance what has been spent, what is still owed, and what is left over (savings). Used every month as a living budget sheet, not a one-off calculator.

## Positioning

A zero-install, zero-account, single-file budgeting sheet that lives in the user's own GitHub repo instead of a third-party finance app or spreadsheet — the user owns the data outright (localStorage + an optional JSON file they control), with no server, no signup, and no vendor lock-in.

## Operating Context

- Primary device: desktop (confirmed). Mobile is a real secondary use case already supported (stacked single-column layout) and must keep working, but desktop layout leads.
- Monthly ritual: enter salary once, add expenses as they occur through the month, check items off as paid, watch "reste à payer" shrink to zero.
- Cross-device: the owner may open the app from more than one browser/computer; GitHub sync (manual push/pull + optional auto-sync) exists specifically so figures match everywhere without re-entry.
- Data export: CSV export/import for backup or external use (e.g. spreadsheet review).

## Capabilities and Constraints

- Categories are fixed: Charges, Famille, Divers.
- Per-expense fields: description (editable in place), amount (editable in place), category, paid checkbox, a free-form color tag (green/red, no fixed meaning — the user assigns it as they like).
- Summary metrics: total spent, reste à payer (unpaid total + count), épargne (salary − total), expense count.
- GitHub sync is optional and additive: the app must work fully offline via localStorage with no token configured; sync is a convenience layer on top, not a requirement.
- No backend/server component exists or is planned; any future capability must stay deliverable as static files on GitHub Pages.

## Brand Commitments

None. No existing name/logo beyond the page title "Mes dépenses". No binding color, typography, or style constraint — full creative latitude confirmed for this redesign.

## Evidence on Hand

- Current working implementation: `index.html` (single file, current visual system: warm off-white background, terracotta/orange accent `#D4541A`, Inter font).
- No real financial figures are available to the agent (user's actual expenses live only in their own browser's localStorage) — do not fabricate sample amounts as if they were real; use clearly placeholder/demo values when illustrating.

## Product Principles

1. Monthly ritual over one-off entry: the interface should make "where do I stand right now" scannable in under a second, every time it's reopened.
2. Desktop-first, mobile-honest: optimize the primary desktop experience without breaking the already-working single-column mobile fallback.
3. Data ownership over convenience: never make GitHub sync, an account, or network access a requirement for the app to be fully usable.
4. Precision over decoration: this is an Operate-mode financial tool — clarity, correct hierarchy, and trustworthy numbers outrank visual flourish.
5. Personal, not generic: this is one person's budget sheet, not a multi-tenant SaaS product — avoid enterprise-dashboard tropes that don't serve a single user.

## Accessibility & Inclusion

No specific requirement established beyond ordinary good practice (readable contrast, legible numeric figures, usable checkbox/tag targets).
