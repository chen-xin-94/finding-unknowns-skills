---
name: implementation-notes
description: Keep a running implementation-notes.md during a build, logging every deviation from the plan and every discovered edge case. Use whenever implementing against an agreed plan or spec, especially in long autonomous sessions. Phase - during implementation.
---

# Implementation notes

No amount of planning removes every unknown; some only appear once the code is open, and the agent may hit an edge case that forces a different tack. When the territory disagrees with the plan, don't stop and don't silently improvise — take the conservative (most reversible) option, write it down, and keep going. The notes file is how the next attempt learns from this one.

Keep a temporary `implementation-notes.md` with a **Deviations** section. For each deviation, log what the plan said, what you did instead, and why. Also log edge cases you discover, even ones handled cleanly — they're exactly the unknowns the next plan should account for. Keep entries to a couple of lines; this is working memory, not documentation.

## Example prompt (the user's voice, verbatim from the field guide)

> "Keep an implementation-notes.md file."

(If an edge case forces a deviation, pick the conservative option, log it under "Deviations", and keep going.)

## Next step

When the build is done, move to `pitch-packager` (for buy-in) and `change-quiz` (to verify your own understanding before merge). Part of the `finding-unknowns` workflow.
