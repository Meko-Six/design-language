# Changelog

## v0.1.0

Seeded: tokens, contract, decision records DR-0001..0003.

## v0.1.1
- ADDED color.scrim rgba(0,0,0,0.55) — promoted from VAL-0003/VAL-0004 (medium confidence)
- CLOSED G7 (modal radius = container 16); OPENED G12 (sheet grabber)
- PROMOTED to spec-ready: text-input (G8), button variants (G9)

## v0.1.2 — component gallery
- playground/components.html + src/components.css: reference implementations
  of button, text-input, list-row per components/*.md specs
- PROVISIONAL tokens in tokens.css: --accent-tinted rgba(11,132,254,0.15)
  (VAL-0001, single sighting — YAML sync pending), --hairline 1px
  (platform structural constant)
- G13 opened: toggle/stepper/badge exact metrics provisional, token-derived
- OPEN: regular-mode control sizing (gallery currently compact metrics)

## v0.1.3 — pattern demos
- playground/patterns.html + src/patterns.css: alert (row/stacked) + sheet per
  patterns/*.md; first real-context consumption of --scrim (G10 closed visually)
- PROVISIONAL: sheet side margins = space-2, grabber geometry (G12),
  alert width = screen-margin-derived
- Enter/exit animation deliberately absent — governed by motion layer (OPEN)

## v0.1.3a — VAL-0006 pattern findings (user-reported, confirmed vs kit)
- alert: max-width 270px added; stacked gap space-3 -> space-2
- button: pill scope extended to alert stacked actions (G11 amendment)

## v0.1.3b — VAL-0007 (user-reported)
- Sizing tokens reasserted with px units; alert stacked buttons had collapsed
  to content height (invalid/missing --touch-target). If tokens.yaml→css
  codegen skipped sizing before, this class can recur — codegen gets a
  checklist when it's built.

## v0.1.3c — VAL-0007b (user-reported, still broken after v0.1.3b)
- Root cause hypothesis: unitless sizing tokens in density-scoped blocks
  override :root via inheritance (compact pages only).
- Fix: px values asserted across :root AND both density scopes.

## v0.1.3d — VAL-0007c root causes found
- Stacked alert buttons: flex:1 basis 0% overrode height on column axis -> 19px.
  Fix: flex 1 1 auto + explicit height.
- Type tokens: if declared without a font family, font: shorthand is invalid
  and silently dropped. Composite shorthands (wgt size/lh family) reasserted.
- Lesson for codegen checklist: shorthands need complete values; flex-basis
  beats height on the main axis.

## v0.1.4 — VAL-0008 tab bar era amendment
- tab bar container model: full-width bar -> floating pill (inset 8, offset 10,
  radius = height/2, provisional, medium confidence, bezel framing)
- active tab = inset segment, darker fill, accent content; inactive = label-primary
- iPad frame in Tab Bars.png: out of device scope, skipped
- tab-bar component spec now writable

## v0.1.5 — VAL-0009 top chrome era amendment
- compact chrome: floating items (chrome-item 44), no bar container
- chrome-group: actions pill container (provisional geometry)
- topbar-h now regular-only; large-title placement convention recorded
