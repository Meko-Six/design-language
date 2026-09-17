# Project Handoff — Apple-style Design Language (v0.1.8)

## What this is
A versioned design language (Apple iOS/macOS foundations, dark-only, two
densities: compact iPhone 16 Plus / regular Macs) in a structured repo that
AI code builders must follow to build a personal hub (weather, calendar,
RSS...). Web-based, Vite vanilla playground = canonical visual reference.

## Architecture (layers, each references only lower)
principles/ · evidence/ (kits+screenshots+decisions) · tokens/ (yaml->css)
· primitives/ (empty) · components/ (button, text-input, list-row) ·
patterns/ (alert, sheet, weather-widget) · instances/ · playground/
(tokens, components, patterns pages + weather.html)

## State at handoff
- tokens v0.1.8: dark palette, compact/regular type scales, spacing, radii,
  sizing, scrim, stat, accent-tinted, hairline, --font, tabbar pill tokens
- 9 VAL records + INST-0001 (weather widget v2, stamped pending final look)
- Open gaps: G13 toggle metrics · G15 icon set (emoji placeholders) ·
  G16 gradient (deferred) · regular-mode chrome UNVALIDATED (macOS toolbar)
- Deferred: glass/materials layer BY DESIGN (foundations first) · motion
  layer OPEN · styles.css cleanup (raw hex .chip-text, undefined token refs)

## Decisions locked
#0B84FE accent (owner, not snapped) · dark-only · no window chrome ·
modal radius = container 16 · tab bar = floating pill (iOS 26/27 era) ·
compact top chrome = floating items · H/L colon format · stat exceeds list scale

## Workflow rules (the contract lives in README.md)
- git = source of truth; github.com = mirror only (never edit in browser)
- Machine switch: pull first, push last
- All changes as paste blocks with heredocs; commit after each
- Screenshots/evidence: dark, 1x, frame named, kits in evidence/kits/exports/
- Validation: every check = SNAP / AMEND / GAP; gaps need 2-3 sightings to promote
- Playground is canonical: not in the gallery = doesn't exist

## Next steps (in order)
1. Stamp INST-0001 v2 (device-arrangement check)
2. Hub shell: floating tab bar + dashboard grid (compact + regular)
3. Calendar + RSS widgets as instances 2-3
4. macOS toolbar validation for regular chrome
5. Icon layer (G15) — SF Symbols licensing research
6. Then, and only then: glass layer, motion layer
