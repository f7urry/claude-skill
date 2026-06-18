---
name: ui-enhancement
description: Assess and improve an existing UI/UX plan or live UI. Reads the current "ui-plan.md", accepts an optional user prompt and/or screenshot for context, performs a structured UX critique, and updates "ui-plan.md" in-place with actionable enhancements ready for implementation.
user-invocable: true
arg-description: Optional improvement prompt and/or path(s) to screenshot image(s). If omitted the agent reads the existing ui-plan.md and infers improvements autonomously.
---

Read and follow the full instructions in `.claude/agents/ui-enhancement.md`. The user's input/arguments may include:
- A free-text improvement prompt describing desired changes or pain points
- One or more file paths to screenshots of the current UI for visual analysis
- Both, or neither (in which case the agent derives enhancements from the existing ui-plan.md alone)
