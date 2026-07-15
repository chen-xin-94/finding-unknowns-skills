---
name: implementation-plan
description: Write an implementation plan that leads with the decisions the user is most likely to change and buries the mechanical work at the bottom. Use when planning is requested before a build, especially after a blindspot pass, brainstorm, or interview. Phase - before implementation.
---

# Implementation plans

When you're ready to implement, write a plan for the user to review — but order it by likelihood-of-tweaking, not build order. Lead with the parts most likely to change: data model changes, new type interfaces, user-facing behavior. This surfaces the things the user may need to alter while changing them is still free. Bury the mechanical refactoring at the bottom — the user trusts you there and reviewing it wastes their attention.

Leave room to improvise: over-specified plans fail exactly where the territory disagrees with the map. Where ambiguity remains, state the default you'll take and the signal that would trigger a pivot.

## Example prompt (the user's voice, verbatim from the field guide)

> "Write an implementation plan in HTML, but lead with the decisions I'm most likely to tweak with"

(Data model changes, new type interfaces, user-facing items up top; mechanical refactoring at the bottom.)

## Next step

Once the plan is approved, start a fresh session and move to `implementation-notes` for the build. Part of the `finding-unknowns` workflow.
