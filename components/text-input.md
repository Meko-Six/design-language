# Text Input
status: active | evidence: VAL-0002, VAL-0005 (3 sightings) | provenance: kit exports, dark, compact

## Anatomy
container (inset card) · value text (required) · placeholder (empty state) ·
clear affordance (optional) · separators between stacked fields

## Variants
single:     one field, full-width inside grouped card
stacked:    multiple fields in one card, separators between, each row 44
in-alert:   compact field inside alert container (VAL-0002 form)

## States
placeholder:   label-tertiary text
empty-focused: caret = accent (the focus convention), no outline, no glow
filled:        label-primary text
filled+clear:  clear X-circle affordance, label-tertiary

## Container
fill: surface-raised · radius: radius-card · separators: --separator

## Tokens
--surface-raised, --radius-card, --separator, --label-primary,
--label-tertiary, --accent

## Forbidden
raw hex/px · focus rings or glows in any color other than accent ·
borders on the field card (elevation = surface step, not outline)

## Open questions
web-specific: autofill styling, keyboard avoidance on iPhone — defer to
instance layer, do not solve per-component
