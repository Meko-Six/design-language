# VAL-0010 — Weather widget v2 stamp (device arrangement check)
Source: owner device check, iPhone Weather widget (dark) vs playground/weather.html (compact)
Scope: INST-0001 v2 layout amendment (v0.1.8)
Checks:
1. City top-left semibold + location arrow: SNAP
2. Condition glyph top-right, no text: SNAP
3. Temp stat token beneath city: AMEND — weight reads regular/medium, not bold; stat 700→400 applied
4. H/L right-aligned, L-first, colon format: SNAP
5. Strip full-width, no Now label: SNAP
6. No hairline above strip: SNAP
7. space-4 / radius-card / surface-raised: AMEND — side spacing +2px (18 vs 16); owner override via --widget-pad-x; off-scale value → G17
Result: 5 SNAP, 2 AMEND, 0 GAP (G17 raised)
Baseline verdict: v2 layout confirmed; stat weight token corrected; side padding owner-amended off-scale.
