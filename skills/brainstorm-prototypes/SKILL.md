---
name: brainstorm-prototypes
description: Produce several genuinely different throwaway variations for the user to react to. Use when the user can only recognize what they want by seeing it (visual design, UX flows, naming, tone), or asks to brainstorm or prototype before building. Phase - before implementation.
---

# Brainstorms and prototypes

The user has unknown knowns: criteria they can't verbalize but will recognize on sight. Verbalizing them now is cheap; discovering them mid-implementation is expensive, because small spec changes can mean drastically different code. Your job is to give them something concrete to react to.

Produce a few **wildly different** options, not shades of the same idea. Keep them cheap and disposable: a single self-contained HTML file with fake data for anything visual, a one-screen sketch per approach otherwise, ordered cheapest to most ambitious for ranked lists. **Do not touch real code.** After they react, say plainly what was learned ("you kept rejecting X, so the real requirement is Y") — that sentence becomes part of the spec.

## Example prompts (the user's voice, verbatim from the field guide)

> "I want a dashboard for this data but I have no visual taste and don't know what's possible."

> "Before wiring anything up, make a single HTML file mocking the new editor toolbar with fake data."

> "Here's my rough problem: users churn after onboarding."

(For the last one, search the codebase and brainstorm ~10 intervention points, cheapest to most ambitious.)

## Next step

When ambiguity remains after reacting to prototypes, go to `interview-me`. Part of the `finding-unknowns` workflow.
