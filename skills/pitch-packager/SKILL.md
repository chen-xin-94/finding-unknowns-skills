---
name: pitch-packager
description: Package a finished piece of work (spec, prototype, implementation notes) into a single document that gets reviewers to understanding and approval fast. Use when the user needs buy-in, a review, or a shareable summary of what was built and why. Phase - after implementation.
---

# Pitches and explainers

Shipping requires buy-in and approvals. Reviewers start with the same unknowns the user started with, plus one more: whether the user accounted for the failure points an expert would probe. Your job is to build a pitch/explainer doc that kills both in one read — it helps reviewers who share the original unknowns understand faster, and helps experts approve when they see the common failure points were handled.

Collect the artifacts (spec/plan, prototype/demo, implementation notes, diff) and lead with the demo — a GIF or screenshot beats prose. Then the problem and the bet, then the 3-5 hard questions an expert in this domain would ask, each answered honestly (including "not handled, and here's why that's acceptable for now"), then deviations lifted from the notes, then what's explicitly out of scope. Keep it to one page; match the medium to the venue.

## Example prompt (the user's voice, verbatim from the field guide)

> "Package the prototype, the spec, and the implementation notes into a single doc I can drop in Slack"

(Lead with the demo GIF.)

## Next step

Pair with `change-quiz` to confirm you actually understand the change before merging. Part of the `finding-unknowns` workflow.
