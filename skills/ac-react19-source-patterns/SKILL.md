---
name: ac-react19-source-patterns
description: 'Reference for React 19 source-file migration patterns, including API changes, ref handling, and context updates.'
triggers:
  - "ac-react19-source-patterns"
---

# React 19 Source Migration Patterns

Reference for every source-file migration required for React 19.

## Quick Reference Table

| Pattern | Action | Reference |
|---|---|---|
| `ReactDOM.render(...)` | → `createRoot().render()` | See references/api-migrations.md |
| `ReactDOM.hydrate(...)` | → `hydrateRoot(...)` | See references/api-migrations.md |
| `unmountComponentAtNode` | → `root.unmount()` | Inline fix |
| `ReactDOM.findDOMNode` | → direct ref | Inline fix |
| `forwardRef(...)` wrapper | → ref as direct prop | See references/api-migrations.md |
| `Component.defaultProps = {}` | → ES6 default params | See references/api-migrations.md |
| `useRef()` no arg | → `useRef(null)` | Inline fix  add `null` |
| Legacy Context | → `createContext` | [→ api-migrations.md#legacy-context](references/api-migrations.md#legacy-context) |
| String refs `this.refs.x` | → `createRef()` | [→ api-migrations.md#string-refs](references/api-migrations.md#string-refs) |
| `import React from 'react'` (unused) | Remove | Only if no `React.` usage in file |

## PropTypes Rule

Do **not** remove `.propTypes` assignments. The `prop-types` package still works as a standalone validator. React 19 only removes the built-in runtime checking from the React package  the package itself remains valid.

Add this comment above any `.propTypes` block:
```jsx
// NOTE: React 19 no longer runs propTypes validation at runtime.
// PropTypes kept for documentation and IDE tooling only.
```

## Read the Reference

For full before/after code for each migration, read **`references/api-migrations.md`**. It contains the complete patterns including edge cases for `forwardRef` with `useImperativeHandle`, `defaultProps` null vs undefined behavior, and legacy context provider/consumer cross-file migrations.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
