# Hub Shell (pattern)
status: provisional | evidence: HIG widgets (430pt table), VAL-0008, VAL-0009 | provenance: derived, pending VAL-0011
## Rule
composed ONLY from tokens + existing patterns. New needs become gaps.
## Idiom
home-screen placement (owner decision pending visual check): the dashboard
grid mirrors the iOS home screen, not app-style full-width layout.
## Anatomy (compact, 430pt canvas)
- top: large-title "Hub" as content; floating chrome items per VAL-0009
  (no bar container)
- dashboard grid: 2 columns x --grid-col, gutter --grid-gutter, side
  placement margin --grid-margin; widget size classes small 170x170 /
  medium 364x170 / large 364x382; widget content margin 16 inside slots
- bottom: floating tab bar (patterns/tab-bar.md), content scrolls beneath
- scroll: grid scrolls under floating chrome + pill; body reserves
  tabbar height + offset
## Regular mode
DELIBERATELY UNSPECIFIED — pending macOS evidence (G19). Do not map
compact geometry onto regular; await toolbar validation.
## Gaps
G18 grid geometry provisional (HIG-derived; needs kit/device sighting)
G19 regular-mode hub navigation model (pending macOS validation)
## Validation status
Provisional. VAL-0011 (owner device check) required before stamp.
