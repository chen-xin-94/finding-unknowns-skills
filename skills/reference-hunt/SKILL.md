---
name: reference-hunt
description: Use existing source code as the specification when the user can't describe what they want in words. Use when the user points at a library, module, folder, or site and says "like this", even if it's in a different language or stack. Phase - before implementation.
---

# References

Some requirements are too intricate or too tacit to write down, but working code somewhere already embodies them. The best reference is not a screenshot or a description — it's source code, because it gives the richest detail on structure and behavior. Your job is to read it like a spec, then reimplement the semantics, not the syntax. Point at the reference even if it's in a different language.

Before writing code, produce a short semantics summary — the behaviors and guarantees the reference implements, and anything that won't translate — and confirm it with the user. That's where misreadings get caught cheaply.

## Example prompt (the user's voice, verbatim from the field guide)

> "This Rust crate in vendor/rate-limiter implements the exact backoff behavior I want."

(Read it, then reimplement the same backoff semantics in the TypeScript API client.)

## Next step

Fold the confirmed semantics into `implementation-plan`. Part of the `finding-unknowns` workflow.
