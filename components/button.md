# Button
status: active | evidence: VAL-0001, VAL-0002, VAL-0003, VAL-0004 (4 sightings)
provenance: HIG Buttons + kit exports, dark, compact

## Anatomy
label (required) · optional icon · height 44 · padding-h 16 (medium confidence)

## Variants
filled:       accent fill, white label          — primary action, one per view
tinted:       accent ~15% fill, accent label    — secondary emphasis
gray:         fill-subtle, label-primary        — neutral actions
plain:        no fill, accent label             — inline/tertiary actions
destructive:  fill-subtle, system-red LABEL     — color carries meaning, never red fill
pill:         any variant at radius-full        — sheet/action contexts only
icon-button:  icon only, circular fill          — toolbars, sheet headers (X, check)

## States
default · pressed (fill-prominent) · disabled (fill-subtle + label-tertiary)
focus: accent treatment (convention from VAL-0005 caret)

## Tokens
--accent, --fill-subtle, --fill-prominent, --label-primary,
--label-tertiary, --sys-red, --radius-control, --touch-target

## Forbidden
raw hex/px · custom heights · more than one filled button per view ·
red fill for destructive (label color only)

## Open questions
pressed-state tint unverified (motion layer OPEN)
