---
name: Mes dépenses
description: Carnet de comptes personnel mensuel — le cahier de ménage français rebâti comme écran, pas un dashboard SaaS de plus.
colors:
  postal-ink:
    value: "#1C3F6E"
  postal-ink-deep:
    value: "#142C4E"
  ledger-red:
    value: "#A8352A"
  stamp-green:
    value: "#1D5B3A"
  stamp-green-label:
    value: "#2C6B47"
  stamp-green-tint:
    value: "#E5F0E9"
  ledger-red-tint:
    value: "#FAEAE7"
  ledger-red-label:
    value: "#8A2E22"
  paper-white:
    value: "#FFFFFF"
  desk-grey:
    value: "#EEF0F0"
  graphite-ink:
    value: "#20242B"
  slate:
    value: "#566070"
  faint-slate:
    value: "#66707F"
  rule-line:
    value: "#CCD4DE"
  input-fill:
    value: "#EDF0F5"
typography:
  body:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: "0em"
  label:
    fontFamily: "Inter, system-ui, -apple-system, sans-serif"
    fontSize: "11px"
    fontWeight: 600
    letterSpacing: "0.08em"
  figure:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "19px"
    fontWeight: 600
    letterSpacing: "0em"
rounded:
  sm: "2px"
  md: "3px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "16px"
  lg: "22px"
components:
  button-primary:
    backgroundColor: "{colors.postal-ink}"
    textColor: "{colors.paper-white}"
    rounded: "{rounded.md}"
    padding: "9px 18px"
  button-primary-hover:
    backgroundColor: "{colors.postal-ink-deep}"
  button-secondary:
    backgroundColor: "{colors.input-fill}"
    textColor: "{colors.slate}"
    rounded: "{rounded.md}"
    padding: "5px 10px"
  button-secondary-hover:
    backgroundColor: "{colors.postal-ink}"
    textColor: "{colors.paper-white}"
  category-tab:
    backgroundColor: "{colors.postal-ink}"
    textColor: "{colors.paper-white}"
    rounded: "{rounded.sm}"
    padding: "4px 9px"
---

# Design System: Mes dépenses

## Overview

**Creative North Star: "Le Cahier du Mois"**

This is the French household ledger-and-wall-register the budgeting ritual already runs on, rebuilt as a screen — not another neutral SaaS dashboard wearing a single accent color as personality. Every month the page opens on its own register line ("Cahier de Novembre 2026"), and the body reads like an account book: a committed postal-ink blue owns the shell and the category tabs, figures run in a tabular monospace like a real ledger's number column, and red is spent on exactly one thing — what is still owed. Nothing here performs warmth through cream paper and a display serif; the palette is cool, structural, and built to be scanned in under a second by the one person who uses it every month.

The system refuses two defaults at once: the "grey cards, one thin accent" dashboard rut (which is also, not coincidentally, what this app's own first version was), and the warm-cream-serif rut that most AI-generated interfaces reach for when given a free hand. Postal-ink blue is a real structural color, not a decoration — it owns the masthead band and every category tab at full saturation, 30–60% commitment, not a hairline.

**Key Characteristics:**
- Ink-on-paper palette: postal-ink blue as the only structural color, ledger red and stamp green reserved strictly for meaning (due / settled), never decoration.
- Two type voices with a functional split: Inter carries every word, IBM Plex Mono carries every number.
- Flat, ruled surfaces — no card-grid cliché, no rounded pill shapes, no soft decorative shadows except the one real "paper lifted off the desk" lift under the ledger itself.
- Desktop-led, mobile-honest: the same ruled-ledger language collapses to a single stacked column on narrow viewports without losing any figure.

## Colors

A committed, cool ink-on-paper palette: one structural blue, two meaning-bearing signal colors, and a quiet slate-neutral scale. Nothing here is warm; the ground is deliberately not the cream/beige default.

### Primary
- **Postal Ink** (`#1C3F6E`): the shell color. Owns the masthead band (full-bleed), every category tab, primary buttons, the focus ring, text-selection fill, and the bottom-rule under category ledger pages. Never used at low opacity as a tint — it is either full-strength or absent.
- **Postal Ink, Deep** (`#142C4E`): hover/active state for primary-blue surfaces only (masthead gradient foot, primary button hover). Never a standalone token for new elements.

### Secondary
- **Ledger Red** (`#A8352A`): reserved exclusively for "reste à payer" > 0 and épargne-negative. **The One Red Rule. Red appears on at most one live figure at a time — the amount still owed. A page with two red numbers has stopped meaning anything.**
- **Stamp Green** (`#1D5B3A`): the settled/paid state — the checkbox's stamped fill, "reste à payer = 0", and positive épargne. Paired with **Stamp Green Tint** (`#E5F0E9`) as the épargne card's background wash when positive, and **Stamp Green Label** (`#2C6B47`) for that card's label text.

### Neutral
- **Paper White** (`#FFFFFF`): every card and ledger-page ground.
- **Desk Grey** (`#EEF0F0`): the page ground behind the cards — cool, not cream, reads as a desk under the paper rather than a tinted page.
- **Graphite Ink** (`#20242B`): primary body text and figures.
- **Slate** (`#566070`): secondary text — field labels, the total row's "TOTAL" caption.
- **Faint Slate** (`#66707F`): muted/placeholder text. Fixed at 5.0:1 contrast on white; the earlier `#8891A0` (3.2:1) failed WCAG AA and is retired.
- **Rule Line** (`#CCD4DE`): every structural divider — card borders, row separators, the summary strip's internal rules.
- **Input Fill** (`#EDF0F5`): the only non-white surface fill, used solely for the `<select>` control and inline amount/description edit fields.

### Named Rules
**The One Voice Rule.** Postal ink blue is the system's only decorative color. Everything else on the page is either structural neutral (paper/graphite/slate/rule-line) or strictly meaning-bearing (ledger red, stamp green). A third decorative color is a system violation, not a variant.

## Typography

**Body Font:** Inter (with system-ui, -apple-system, sans-serif fallback)
**Label/Mono Font:** IBM Plex Mono (with ui-monospace, SFMono-Regular, Menlo fallback)

**Character:** A workhorse grotesque for everything read as language, paired with a true tabular monospace for everything read as a number. The pairing exists for one functional reason — a ledger's figure column must align — never as a "technical" costume.

### Hierarchy
- **Title** (600, 17px, masthead wordmark): the product name in the masthead band only.
- **Figure** (600, 19px / 22px for the salary input, tabular-nums, `font-family: mono`): every amount, total, and the salary input. The system's most distinctive typographic move — no other UI in this register ever sets a number in the body font.
- **Body** (400, 13–14px): expense descriptions, buttons, hint text.
- **Label** (600, 11–12px, uppercase, 0.08em tracking): section headers (`card-title`), field labels, category tabs, the masthead month line.

### Named Rules
**The Ledger-Column Rule.** Any value that is a sum of money is set in IBM Plex Mono with `font-variant-numeric: tabular-nums`, full stop — never the body font, never proportional figures.

## Layout

Two-column shell above 680px: a fixed ~300px left margin (salary, summary, new-expense form, GitHub sync) beside a fluid right region (the ledger itself). Below 680px both collapse to a single stacked column, masthead padding tightens, and nothing in the left margin is lost — it simply reads first, top to bottom.

Category ledger pages lay out as CSS Grid, `repeat(auto-fit, minmax(240px, 1fr))`: as many categories as fit the viewport share the width evenly; a lone category caps at 420px rather than stretching the full row. On mobile this collapses to one column per category, stacked — the page's own vertical scroll, never a horizontal swipe.

Spacing rhythm observed in the implementation: 4px (inline icon/label gaps), 8px (row and field gaps), 16px (card internal padding, section-to-section gaps), 22px (gutter between category ledger pages).

## Elevation & Depth

Flat by default. The only shadow in the system sits under the right-hand ledger card (`.right .card`): `0 1px 2px rgba(20, 44, 78, 0.05), 0 6px 16px -4px rgba(20, 44, 78, 0.08)`, tinted from postal ink rather than neutral black, read as paper lifted an inch off the desk. Every other surface — the left-margin form cards, buttons, inputs — is flat, bordered by a single `rule-line` stroke, no shadow at all.

### Named Rules
**The One Lift Rule.** Exactly one region of the page gets a shadow: the ledger itself. A shadow anywhere else (a button, a form card, a chip) is decoration creeping back in.

## Shapes

Sharp-cornered, ledger-like: `2px` on inline controls (checkbox, tag dot outline, inline edit inputs), `3px` on containers (cards, buttons, the category select). Nothing in the system uses a pill or fully-rounded shape except the native circular tag-dot and the stamped checkbox's own check glyph. No card, button, or input exceeds 3px of radius — this is a deliberate rejection of the soft, bubbly 8–10px radius the app's first version used.

## Components

### Buttons
- **Shape:** 3px radius, flat.
- **Primary** (`.add-btn`, "Connecter"): postal-ink fill, white text, 9px/18px padding, icon + label in a row.
- **Hover/Focus:** primary darkens to postal-ink-deep on hover; every focusable control gets a themed `2px solid postal-ink` outline at `2px` offset on `:focus-visible` (never on mouse click) — the system's one universal keyboard-focus rule.
- **Secondary** (`.export-btn` — Importer/Exporter CSV, sync actions): input-fill background, slate text, inverts to solid postal-ink on hover. Disabled state drops to 45% opacity, no color change.

### Chips / Tabs
- **Category tab** (`.cat-label-name`): solid postal-ink fill, white uppercase label, rounded only at the top corners (`2px 2px 0`), sitting flush on the category's bottom rule — reads as a tab attached to the ledger page below it, not a floating pill.
- **Tag dot** (`.tag-dot`): an 11px circle, not a chip — deliberately circular to stay visually distinct from the square paid-checkbox beside it. Three states: outline-only (no tag), filled stamp-green, filled ledger-red. User-assigned, no fixed meaning.

### Cards / Containers
- **Corner Style:** 3px.
- **Background:** paper-white on desk-grey.
- **Shadow Strategy:** none, except the right-hand ledger card (see Elevation & Depth).
- **Border:** 1px rule-line, uniform.
- **Internal Padding:** 16px (1rem/1.125rem).

### Inputs / Fields
- **Text/number inputs:** no box — transparent background, a single 1.5px `rule-line` bottom border, sharpening to postal-ink on focus. This is the system's other signature move: a field you "write into," not a box you click.
- **Select:** the one exception — full bordered box (input-fill background, rule-line border, 3px radius), since a native `<select>` can't take the bottom-rule treatment without losing its affordance.
- **Checkbox (paid state):** a 16px square, `appearance: none`, rule-line border; on check, fills stamp-green and draws a white check mark with a brief 160ms "stamp" pop-in — the one authored motion moment in the system, tied directly to the product's own ritual (settling a ledger line).
- **Salary input:** no border at rest; a 1.5px bottom rule appears only on `:focus-within`, since this is the only input large enough (22px mono figures) to read clearly without one.

### Masthead
- Full-bleed postal-ink band (gradient to postal-ink-deep, top to bottom), white wordmark + a simple open-ledger line icon on the left, the live "Cahier de [Mois Année]" register line in tracked uppercase mono on the right. The system's only persistent full-width color field.

## Do's and Don'ts

### Do:
- **Do** keep red to exactly one live meaning: money still owed (`reste à payer`, negative épargne). Never use it for anything else, including error states — those get slate/graphite, not red.
- **Do** set every currency figure in IBM Plex Mono with tabular numerals, never the body font.
- **Do** keep every icon as an authored inline SVG in one consistent stroke (1.4–1.8px, round caps) — never a unicode glyph or emoji standing in for one.
- **Do** theme focus rings, selection color, and the checkbox's check mark from the postal-ink/stamp-green palette — never leave a browser default un-themed.

### Don't:
- **Don't** introduce a third decorative color beyond postal-ink. Ledger red and stamp green are signal colors, not a palette to pick from.
- **Don't** round a corner past 3px. The sharp ledger-page edge is a deliberate rejection of the previous bubbly 8–10px radius.
- **Don't** add a shadow anywhere but the right-hand ledger card. Flat is the default; the one lift is earned, not habitual.
- **Don't** reach for a boxed/bordered input style for text or number fields — the bottom-rule treatment is the system's signature, and a full box on every field would just be the category default again.
