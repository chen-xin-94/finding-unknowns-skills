---
name: blindspot-pass
description: Surface the user's unknown unknowns before work starts. Use when the user is entering an unfamiliar codebase area or an unfamiliar domain (design, video, infra), or says "blind spot pass" or asks to find their "unknown unknowns". Phase - before implementation.
disable-model-invocation: false
---

# Blind spot pass

The user is about to work in territory they don't know well. Your job is not to do the task yet — it's to find their unknown unknowns and explain them, so their next prompt is better. Ask for (or infer) who they are and what they already know; their starting point is usually what you need to collaborate well.

Explore the relevant territory yourself, then report the unknown unknowns: the potholes a newcomer here hits, the hidden context that constrains the work, what "good" looks like in this domain, and the questions an expert would ask before starting.

**Do not implement. Be a scout: search, inspect, compare, and explain where the risky assumptions are.**

## Example prompts (the user's voice, verbatim from the field guide)

> "I'm working on adding a new auth provider but I know nothing about the auth modules in this codebase. Can you do a blind spot pass to help me figure out my relevant unknown unknowns and help me prompt you better."

> "I don't know what color grading is but I need to grade this video. Can you teach me to understand my unknown unknowns about color grading, so that I can prompt better?"

## Next step

Once blind spots are surfaced, the natural next moves are `brainstorm-prototypes` (when the criteria are "know it when you see it") or `interview-me` (to resolve remaining ambiguity). Part of the `finding-unknowns` workflow.
