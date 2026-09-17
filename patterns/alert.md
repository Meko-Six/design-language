# Alert
status: active | evidence: VAL-0002, VAL-0003 | provenance: HIG + kit, dark, compact

## Anatomy
title (headline, 600) · message (footnote, label-secondary) ·
optional text field (text-input:in-alert) · action zone

## Layout rules
width: narrower than screen, centered horizontally
surface: surface-overlay, radius-container (G7 ruling)
scrim: --scrim over the presenting view
actions horizontal when <= 2, stacked otherwise, separated by --space-3

## Action emphasis (the hierarchy rule)
exactly one default: filled, label-primary
destructive: system-red LABEL on fill-subtle — never a red fill
cancel: fill-subtle, label-primary

## Content conventions
title/message: sentence case, short · button labels: Title Case

## Amendment 1 (v0.1.3a, VAL-0006)
stacked action gap = space-2 (8), not space-3. max-width 270px (kit proportion),
provisional until regular-mode pass.
