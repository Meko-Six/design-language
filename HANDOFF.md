# Project Handoff — Apple-style Design Language (v0.1.9)
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
- tokens v0.1.9 (css): stat 400 40px (weight device-corrected), --font root,
  floating-pill tab bar tokens, chrome-item 44, --widget-pad-x 18 (G17),
  accent-tinted provisional — TOKENS.YAML SYNC PENDING (accent-tinted, stat,
  font, pill chrome, widget-pad-x)
- 10 VAL records (VAL-0001..0010) · INST-0001 weather widget v2 STAMPED
  (VAL-0010: 5 SNAP / 2 AMEND / 0 GAP)
- Open owner call: stat weight 400 applied (owner said "normal or medium");
  flip to 500 = one value in tokens.css
- Open gaps: G13 toggle metrics · G15 icon set (emoji placeholders) ·
  G16 gradient (deferred) · G17 off-scale spacing 18px widget pad
  (1 sighting — needs 2nd sighting or owner promotion to scale) ·
  regular-mode chrome UNVALIDATED (macOS toolbar)
- Deferred: glass/materials layer BY DESIGN (foundations first) · motion
  layer OPEN · styles.css cleanup (raw hex .chip-text, undefined token refs)
## Decisions locked
#0B84FE accent (owner, not snapped) · dark-only · no window chrome ·
modal radius = container 16 · tab bar = floating pill (iOS 26/27 era) ·
compact top chrome = floating items · H/L colon format · stat exceeds
list scale, weight 400 (device-corrected v0.1.9)
## Workflow rules (the contract lives in README.md)
- git = source of truth; github.com = mirror only (never edit in browser)
- Machine switch: pull first, push last
- All changes as paste blocks with heredocs; commit after each
- Screenshots/evidence: dark, 1x, frame named, kits in evidence/kits/exports/
- Validation: every check = SNAP / AMEND / GAP; gaps need 2-3 sightings to promote
- Playground is canonical: not in the gallery = doesn't exist
- Playground serve: static — `python3 -m http.server 8000` from repo root,
  open /playground/<page>.html (no build step; file:// also works)
## Next steps (in order)
1. Hub shell: floating tab bar + dashboard grid (compact + regular)
2. Calendar + RSS widgets as instances 2-3
3. macOS toolbar validation for regular chrome
4. Icon layer (G15) — SF Symbols licensing research
5. Then, and only then: glass layer, motion layer
