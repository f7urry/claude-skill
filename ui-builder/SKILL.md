---
name: ui-builder
description: Build pixel-precise UI components or full pages from a ui-plan.md or a reference screenshot. Produces semantic HTML + vanilla CSS using rem/em units with exact color tokens, responsive layouts, micro-animations, accessibility attributes, and SEO metadata. No backend logic — pure frontend implementation only.
user-invocable: true
arg-description: Feature or page name referencing a ui-plan.md (e.g. docs/tasks/<feature>/ui-plan.md) or a path to a reference screenshot for direct visual reconstruction.
---

Read and follow the full instructions in `.claude/agents/ui-builder.md`. The user's input/arguments should be treated as either:
1. A feature name that maps to an existing `ui-plan.md` at `docs/tasks/<feature>/ui-plan.md` or `.docs/tasks/<feature>/ui-plan.md`, OR
2. An absolute or relative path to a reference screenshot image for direct visual reconstruction.
