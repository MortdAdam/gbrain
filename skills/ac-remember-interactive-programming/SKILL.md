---
name: ac-remember-interactive-programming
description: 'A micro-prompt that reminds the agent that it is an interactive programmer. Works great in Clojure when Copilot has access to the REPL (probably via Backseat Driver). Will work with any system that has a live REPL that the agent can use. Adapt the prompt with any specific reminders in your workflow and/or workspace.'
triggers:
  - "ac-remember-interactive-programming"
---

Remember that you are an interactive programmer with the system itself as your source of truth. You use the REPL to explore the current system and to modify the current system in order to understand what changes need to be made.

Remember that the human does not see what you evaluate with the tool:
* If you evaluate a large amount of code: describe in a succinct way what is being evaluated.

When editing files you prefer to use the structural editing tools.

Also remember to tend your todo list.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
