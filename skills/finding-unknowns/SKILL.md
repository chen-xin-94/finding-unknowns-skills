---
name: finding-unknowns
description: Orchestrator for the full "finding your unknowns" workflow across before, during, and after implementation. Use to enter the whole method, or when the user is starting a non-trivial task and wants to surface what they don't know before it gets expensive. Routes to the right phase skill (blindspot-pass, brainstorm-prototypes, interview-me, reference-hunt, implementation-plan, implementation-notes, pitch-packager, change-quiz) based on where they are.
---

# Finding your unknowns

**The map is not the territory.** The map is the user's prompt, skills, and context; the territory is the codebase and the real world. The gap between them is *unknowns*, and with strong models the quality of the work is bottlenecked by how well the user clarifies them. Your job in this workflow is to surface unknowns — before, during, and after implementation — because every explainer, brainstorm, interview, prototype, and reference is a cheap way to find what the user didn't know before it becomes expensive to fix.

## The four kinds of unknowns

|  | **Known** | **Unknown** |
|---|---|---|
| **Known** | in the prompt already | the user knows they haven't figured it out |
| **Unknown** | so obvious they'd never write it down, but they'll recognize it on sight ("no, not like that") | not considered at all |

Move things out of the bottom row *before* implementation makes them expensive.

## The workflow, and how to route

Figure out where the user is and redirect to the matching skill. When one phase finishes, proactively suggest the next.

**Before implementation**
- Entering an unfamiliar area or domain, doesn't even know the questions → **blindspot-pass**
- "Know it when I see it" criteria (design, UX, tone) → **brainstorm-prototypes**
- Brainstormed, but ambiguity remains → **interview-me**
- Can't describe it, but working code somewhere does it → **reference-hunt**
- Ready to build, wants a plan to review → **implementation-plan**

**During implementation**
- Building against an agreed plan → **implementation-notes** (log deviations, keep going)

**After implementation**
- Needs buy-in / a shareable summary → **pitch-packager**
- Large or unfamiliar change, merging soon → **change-quiz** (merge only when you pass)

## How to detect the current step

Read the conversation for signal, don't interrogate: a fresh unfamiliar task → blindspot-pass; a settled plan and edits underway → implementation-notes; a finished diff and talk of merging/reviewing → pitch-packager or change-quiz. If genuinely unclear, ask one question: "Where are you — still scoping, mid-build, or wrapping up?" Then route.

Phases are not strictly linear — a discovery mid-build can send the user back to interview-me or implementation-plan. Follow the work, not the list.

## The loop

**What you learn becomes the map for next time.** What a quiz exposes, what a brainstorm rejected, what a deviation revealed — all of it sharpens the map for the next project. When a long task comes back wrong, the cause is usually undefined unknowns, not model capability: come back through this workflow rather than just retrying.

> Trivial (typo-level) tasks don't need this. Use judgment and skip the ceremony.
