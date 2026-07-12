---
name: interview-me
description: Interview the user one question at a time to resolve remaining ambiguity before implementation. Use when planning or brainstorming is done but unknowns remain, or when the user asks to be interviewed about a task or spec. Phase - before implementation.
disable-model-invocation: false
---

# Interviews

Brainstorming is over and gaps remain between the user's map and the territory. Your job is to close them by interviewing the user, one question at a time, starting with the questions whose answers would change the most.

Read everything already established first, so you don't ask what's answered. Sort the open ambiguities by blast radius: architecture-changers first, then behavior/edge cases, and skip trivia — propose and move on. Ask exactly one question per turn, give the context that makes it matter, and offer your recommended answer. **Never ask a question the codebase can answer — go look instead.**

## Example prompt (the user's voice, verbatim from the field guide)

> "Interview me one question at a time about anything ambiguous"

(Prioritize the questions where the user's answer would change the architecture.)

## Next step

When the remaining unknowns are cheaper to discover during implementation than to ask about, stop and hand the decision list to `implementation-plan`. Part of the `finding-unknowns` workflow.
