# VAL-0007 — Alert stacked-button height (user-reported, 3 iterations)
Symptom: 19px content-height buttons instead of 44px; default font instead of headline.
Root causes: (1) flex:1 basis 0% overrode height on column flex axis ->
flex 1 1 auto; (2) font: shorthand without family value invalid -> composite
shorthands reasserted across density scopes.
Lessons (for codegen checklist): flex-basis beats height on main axis;
shorthands require complete values. Debugging path: eye -> grep -> DevTools
Computed -> curl served bytes. All probes now part of project toolkit.
