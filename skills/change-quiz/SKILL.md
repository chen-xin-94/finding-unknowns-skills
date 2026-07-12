---
name: change-quiz
description: After a working session, produce a report on what changed plus a quiz the user must pass before merging. Use when the user asks "what did we actually do", wants to review a large change, or invokes a quiz before merge. Phase - after implementation.
disable-model-invocation: false
---

# Quizzes

After a long session you may have done more than the user realizes, and a diff gives only light understanding — much of the behavior depends on how the change interacts with existing code paths. The user should merge only what they can pass a quiz on. Your job is to give them the context, then test it.

Build a short report first: the context (what problem this solved), what changed grouped by intent, how it interacts with existing code paths (including behavior that changed in files the diff doesn't show), and the 2-3 mental-model updates to walk away with. For long sessions, offer it as a single self-contained HTML page with the quiz at the bottom. Then quiz: 5-8 questions weighted toward deviations, edge cases, and interaction effects — not trivia. Grade honestly. **Pass = merge-ready; don't soften the bar.**

## Example prompt (the user's voice, verbatim from the field guide)

> "I want to make sure I understand everything that's happened in this change."

(Produce an HTML report with context and intuition, plus a quiz at the bottom the user must pass.)

## Loop back

What the quiz reveals — a gap in understanding, or a change that's too clever — feeds the next project's map. That's the closing idea of `finding-unknowns`: what you learn becomes the map for next time.
