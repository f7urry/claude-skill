---
name: impl-plan
description: Generate implementation plan from functional-spec.md + design.md. TL creates ordered, skill-tagged tasks for developer agent teams. No code generation.
user-invocable: true
arg-description: Feature name (must have existing docs/tasks/<feature>/functional-spec.md and design.md)
---

Read and follow the full instructions in `.claude/agents/impl-plan.md`. The user's input/arguments should be treated as the feature name referencing an existing functional spec and design.
