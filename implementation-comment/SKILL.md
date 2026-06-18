---
name: implementation-comment
description: Implement code at the location of a TODO/FIXME/NOTE comment. Reads 10 lines before and after the comment to understand the surrounding context, then generates and replaces the comment with a correct, working implementation.
user-invocable: true
arg-description: File path and line number of the comment (e.g. "src/utils.ts:42"), or just the file path to scan for all TODO comments
---

# Implementation Comment Skill

You are a senior developer. Your job is to implement code described by a snippet comment (e.g. `// TODO`, `// FIXME`, `// NOTE: implement this`, `// TODO: add validation here`).

## Steps

### 1. Locate the Comment

The user's argument is either:
- `<filepath>:<line>` — a specific file and line number containing the comment.
- `<filepath>` — scan the file for all TODO/FIXME/NOTE/HACK/XXX comments and implement each one.
- A plain description — search the active workspace for matching comments.

### 2. Read Context Window

For **each** target comment:
1. Open the file.
2. Read **10 lines before** the comment line (or from the file start if fewer than 10 lines exist).
3. Read the **comment line** itself.
4. Read **10 lines after** the comment line (or to the file end if fewer than 10 lines remain).
5. Understand:
   - What the comment is asking to be implemented.
   - The surrounding code's language, style, naming conventions, imports, and logic flow.
   - Any data types, variables, or functions already in scope.

### 3. Plan the Implementation

Before writing code, reason about:
- What the comment intends (parse the comment text carefully).
- What already exists in the surrounding ±10-line context.
- What imports or helpers are already available vs. need to be added.
- Edge cases and error handling consistent with the surrounding code style.

### 4. Generate the Implementation

Write the replacement code that:
- **Removes** the original comment line entirely.
- **Replaces** it with the correct, working implementation.
- Matches the indentation, style, and conventions of the surrounding code.
- Does **not** introduce unnecessary imports unless required (and if required, add them at the top of the file).
- Is minimal — implement only what the comment describes, nothing more.

### 5. Apply the Change

Use the file editing tools to apply the change in-place:
- Replace only the comment line (and any stub code immediately below it that the comment refers to).
- Do not reformat or alter unrelated code.

### 6. Verify

After applying:
- Re-read the modified region to confirm correctness.
- If the project has a build or lint command available (check `package.json`, `Makefile`, `pyproject.toml`, etc.), run it to validate no errors were introduced.
- Report to the user: what comment was found, what was implemented, and a brief rationale.

## Rules

- Never leave the TODO comment in place after implementing.
- If the comment is ambiguous or there is not enough context to implement safely, **ask the user for clarification** before making any changes.
- If multiple TODO comments are found in the same file, implement them **sequentially**, re-reading context for each one.
- Preserve all other existing comments and documentation unrelated to the target comment.
