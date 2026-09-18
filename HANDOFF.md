# Project Handoff — Apple-style Design Language (v0.1.10)

## What this is
A versioned design language (Apple iOS/macOS foundations, dark-only, two
densities: compact iPhone 16 Plus 430pt / regular Macs) in a structured repo
that AI code builders must follow to build a personal hub (weather, calendar,
RSS...). Playground = canonical visual reference.

## RESUMING IN A NEW CHAT — READ THIS FIRST (lessons from v0.1.9 session)
- Repo: github.com/Meko-Six/design-language, PUBLIC, branch main. Fetch via
  raw.githubusercontent.com/Meko-Six/design-language/main/<path> and
  api.github.com/repos/Meko-Six/design-language/...
- Chat environment has NO filesystem and NO repo-write. All changes ship as
  heredoc paste blocks; the OWNER runs them in Terminal and pushes. Assistant
  verifies writes by re-fetching from GitHub.
- Pitfall — fetch agents flake: they may claim "repo does not exist" (it
  exists), return API documentation instead of data, or 404 right after the
  repo goes public. Retry with api.github.com endpoints; ask owner to confirm
  the repo is public and the exact URL before concluding anything.
- Pitfall — raw fetch cache: raw.githubusercontent can serve stale content
  after a push. Verify file state via api.github.com (commits?path=<file>
  shows the real latest commit + blob SHA) or ask owner to run
  `git log --oneline -3` locally.
- Pitfall — suggestion cards: clickable cards under assistant replies just
  SEND their text as the owner's message. If the card contains [brackets],
  the owner must replace them with real values; a pasted template is not data.
- Pitfall — append blocks are run-once: re-running a `cat >>` block
  duplicates content (changelog v0.1.9 was doubled once; fixed by dedupe).
  Overwrite blocks (`cat >`) are safe to re-run.
- Pitfall — localhost dies with the session: the server is not running in a
  new chat. Serve with EITHER `cd playground && npm install && npm run dev`
  (Vite, package.json exists; open http://localhost:5173/hub.html) OR
  `python3 -m http.server 8000` from repo root
  (open http://localhost:8000/playground/hub.html). file:// also works.
- Pitfall — heredoc paste: paste each block as ONE unit into Terminal; if a
  `>` continuation prompt appears, press Return to submit the EOF.
- Working loop: evidence -> spec -> playground, every change = paste block +
  commit, push last, assistant verifies on the mirror after each batch.

## Architecture (layers, each references only lower)
principles/ · evidence/ (kits+screenshots+decisions) · tokens/ (yaml->css)
· primitives/ (empty) · components/ (button, text-input, list-row) ·
patterns/ (alert, sheet, weather-widget, tab-bar, hub-shell) · instances/ ·
playground/ (tokens, components, patterns pages, weather.html, hub.html)

## State at handoff (v0.1.10)
- tokens v0.1.10 (css): stat 400 40px (device-corrected), --font root,
  floating-pill tab bar tokens, chrome-item 44, --widget-pad-x 18 (G17),
  hub grid tokens (widget size classes 170/364x170/364x382; placement
  margin 33, gutter 24 — home-screen idiom, HIG-derived) — TOKENS.YAML SYNC
  PENDING (accent-tinted, stat, font, pill chrome, widget-pad-x, grid)
- 10 VAL records (VAL-0001..0010) · INST-0001 weather widget v2 STAMPED
  (VAL-0010: 5 SNAP / 2 AMEND / 0 GAP)
- Hub shell BUILT but PROVISIONAL: patterns/hub-shell.md +
  patterns/tab-bar.md + playground/hub.html exist; awaiting VAL-0011
  owner device check (hub.html vs iPhone home screen, dark) before stamp
- Open owner call: stat weight 400 applied (owner said "normal or medium");
  flip to 500 = one value in tokens.css
- Open gaps: G13 toggle metrics · G15 icon set (emoji placeholders) ·
  G16 gradient (deferred) · G17 off-scale spacing 18px widget pad
  (1 sighting) · G18 hub grid geometry provisional (needs device sighting)
  · G19 regular-mode hub navigation model (macOS evidence pending) ·
  regular-mode chrome UNVALIDATED (macOS toolbar)
- Deferred: glass/materials layer BY DESIGN · motion layer OPEN ·
  styles.css cleanup (raw hex .chip-text, undefined token refs)

## Decisions locked
#0B84FE accent (owner, not snapped) · dark-only · no window chrome ·
modal radius = container 16 · tab bar = floating pill (VAL-0008) ·
compact top chrome = floating items (VAL-0009) · H/L colon format ·
stat exceeds list scale, weight 400 · hub grid = home-screen idiom
(placement margin 33 / gutter 24, widget content margin stays 16)

## Workflow rules (the contract lives in README.md)
- git = source of truth; github.com = mirror only (never edit in browser)
- Machine switch: pull first, push last
- All changes as paste blocks with heredocs; commit after each; push last
- Screenshots/evidence: dark, 1x, frame named, kits in evidence/kits/exports/
- Validation: every check = SNAP / AMEND / GAP; gaps need 2-3 sightings
  to promote
- Playground is canonical: not in the gallery = doesn't exist
- Consume semantic tokens only; never raw hex/px outside token definitions;
  do not invent values — STOP and file an amendment request instead
- Evidence hierarchy: HIG published guidance > Apple UI kit exports >
  screenshots > owner decisions

## Next steps (in order)
1. VAL-0011: owner device check of playground/hub.html vs iPhone home
   screen (grid columns/spacing, pill position/height, title placement) —
   report SNAP/AMEND/GAP per item; then stamp hub shell
2. Calendar + RSS widgets as instances 2-3 (medium/large grid slots)
3. macOS toolbar validation for regular chrome (unblocks G19)
4. Icon layer (G15) — SF Symbols licensing research
5. tokens.yaml sync (all provisional css-only tokens above)
6. Then, and only then: glass layer, motion layer
