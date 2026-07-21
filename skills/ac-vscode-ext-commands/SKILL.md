---
name: ac-vscode-ext-commands
description: 'Guidelines for contributing commands in VS Code extensions. Indicates naming convention, visibility, localization and other relevant attributes, following VS Code extension development guidelines, libraries and good practices'
triggers:
  - "ac-vscode-ext-commands"
---

# VS Code extension command contribution

This skill helps you to contribute commands in VS Code extensions

## When to use this skill

Use this skill when you need to:
- Add or update commands to your VS Code extension

# Instructions

VS Code commands must always define a `title`, independent of its category, visibility or location. We use a few patterns for each "kind" of command, with some characteristics, described below:

* Regular commands: By default, all commands should be accessible in the Command Palette, must define a `category`, and don't need an `icon`, unless the command will be used in the Side Bar.

* Side Bar commands: Its name follows a special pattern, starting with underscore (`_`) and suffixed with `#sideBar`, like `_extensionId.someCommand#sideBar` for instance. Must define an `icon`, and may or may not have some rule for `enablement`. Side Bar exclusive commands should not be visible in the Command Palette. Contributing it to the `view/title` or `view/item/context`, we must inform _order/position_ that it will be displayed, and we can use terms "relative to other command/button" in order to you identify the correct `group` to be used. Also, it's a good practice to define the condition (`when`) for the new command is visible.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
