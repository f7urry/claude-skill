---
name: test-plan
description: Generate test plan + CSV test cases from functional-spec.md and design.md. QA runs it. TDD — no implementation code.
user-invocable: true
arg-description: Feature name (must have existing docs/tasks/<feature>/functional-spec.md and design.md)
---

Read and follow the full instructions in `.claude/agents/test-plan.md`. The user's input/arguments should be treated as the feature name referencing an existing functional spec and design.
