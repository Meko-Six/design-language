# List Row
status: active | evidence: VAL-0001 (multiple sightings, inset-grouped + plain + indexed)
provenance: HIG Lists + kit exports, dark, compact

## Anatomy
leading slot (icon/image/checkbox, optional) · title (required) ·
subtitle (optional) · trailing slot (accessory) · separator (bottom)

## Variants — by trailing accessory
plain:      no accessory
chevron:    disclosure arrow, label-tertiary     — row navigates somewhere
value:      trailing text (Detail), label-secondary
button:     trailing text action, accent label    — one action, no navigation
badges:     1-2 pills (date/time), fill-subtle    — badge primitive
toggle:     switch control                        — setting rows
stepper:    -/+ control                           — quantity rows
menu:       Pop-up button                         — choice rows (kit sighting)

## Variants — by leading content
basic:      text only
thumbnail:  square image ~29, radius-control

## Separators
inset from leading text edge (aligns with title, not card edge) ·
--separator color · never edge-to-edge inside grouped cards ·
omit on last row of a group

## Grouping (context)
rows live inside grouped cards: surface-raised, radius-card,
16 screen-margin (compact), 8-12 vertical gap between groups

## States
default · selected (fill-subtle row wash) · pressed (unverified — motion OPEN)
disabled: label-tertiary content

## Tokens
--surface-raised, --radius-card, --separator, --label-primary,
--label-secondary, --label-tertiary, --accent, --fill-subtle,
--space-* scale, --row-height

## Forbidden
raw hex/px · edge-to-edge separators inside cards · chevron on non-navigating
rows (accessory must match behavior) · custom row heights ·
new accessory types (extend via amendment, not improvisation)

## Open questions
pressed state tint · hover behavior in regular mode (deferred to motion/
desktop passes) · multi-line subtitle wrapping rules
