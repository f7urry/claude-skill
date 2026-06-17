---
name: tech-design
description: Generate technical design from functional-spec.md. Solution Architect creates design.md + openapi.yml covering entities, APIs, architecture, component design, data flows, NFRs, and API contracts. No code generation.
user-invocable: true
arg-description: Feature name (must have existing docs/tasks/<feature>/functional-spec.md)
---

Read and follow the full instructions in `.claude/agents/tech-design.md`. The user's input/arguments should be treated as the feature name referencing an existing functional spec.
