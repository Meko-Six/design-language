# Weather Widget (instance pattern)
status: active | evidence: INST-0001 (in progress) | provenance: composed from system parts

## Rule
composed ONLY from tokens + existing components. New needs become gaps (G-numbers),
never local values.

## Anatomy (compact)
card = group (surface-raised, radius-card, screen-margin placement)
header row: [city: body/label-primary + condition: sub/label-secondary]
            [temp: large-title/label-primary, right-aligned]
meta row:   H/L values: sub/label-primary + labels: caption/label-tertiary
strip:      horizontal hour cells: hour caption/tertiary · glyph placeholder ·
            temp sub/primary — "Now" cell hour label in accent

## Gaps raised by this instance
G14 stat primitive — large value + unit + label; v1 uses large-title token
  (decision: widget temp does NOT exceed system scale)
G15 icon set — weather condition glyphs; emoji placeholders, NOT canonical
G16 atmospheric gradient background — deferred, decoration not foundation

## Typography amendment (v0.1.7, device comparison)
List-derived roles alone are wrong for glanceable widgets. Widget context:
semibold weight variants of existing roles; temp uses stat token (~40, device
estimate, provisional). H/L = footnote semibold, primary values. Hour labels =
footnote semibold secondary. Hour temps = body semibold. No hairline above
strip. CORRECTION: H/L format uses colons ("L:7° H:14°") — earlier v2 note
was wrong; colon convention stands (matches VAL-0001 badges era).

## Layout amendment v2 (v0.1.8, device comparison)
Device arrangement: city top-left (semibold, + location arrow) · condition GLYPH
top-right, no condition text · temp LEFT beneath city (stat) · H/L right-aligned
same band, order L then H, colon format · strip full-width 3 rows, no Now label,
no hairline · tight space-4 padding. v1's split-header arrangement was wrong.
## Stamp amendment (v0.1.9, VAL-0010 device check)
Stat token weight corrected 700→400 (G14 promotion carried wrong weight;
device reads regular). Side padding 16→18px via --widget-pad-x (owner
override; off-scale → G17, needs 2nd sighting or owner promotion).
