# VAL-0003 — Action Sheet (iOS 27 kit, geometry-only)
Source: evidence/kits/exports/iOS-27/Action Sheet.png
DEFECT: sheet component rendered in light mode (variable mode did not propagate
to nested component). Color checks on sheet VOID; geometry valid (mode affects
color bindings only). Background/nav checks valid.
Result: 7 checks SNAP. G7 CLOSED — modal surfaces = radius-container:16, no new
token (alert ~14 noted as within medium-confidence tolerance). G11 opened (pill
button variant). G9 2nd sighting. G10 upgraded: scrim ~black 55%, provisional.
