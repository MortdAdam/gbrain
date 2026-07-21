---
name: ac-react-audit-grep-patterns
description: 'Provides the complete, verified grep scan command library for auditing React codebases before a React 18.3.1 or React 19 upgrade. Use this skill whenever running a migration audit - for both the react18-auditor and react19-auditor agents. Contains every grep pattern needed to find deprecated APIs, removed APIs, unsafe lifecycle methods, batching vulnerabilities, test file issues, dependency conflicts, and React 19 specific removals. Always use this skill when writing audit scan commands - do not rely on memory for grep syntax, especially for the multi-line async setState patterns which require context flags.'
triggers:
  - "ac-react-audit-grep-patterns"
---

# React Audit Grep Patterns

Complete scan command library for React 18.3.1 and React 19 migration audits.

## Usage

Read the relevant section for your target:
- **`references/react18-scans.md`** - all scans for React 16/17 → 18.3.1 audit
- **`references/react19-scans.md`** - all scans for React 18 → 19 audit
- **`references/test-scans.md`** - test file specific scans (used by both auditors)
- **`references/dep-scans.md`** - dependency and peer conflict scans

## Base Patterns Used Across All Scans

```bash
# Standard flags used throughout:
# -r = recursive
# -n = show line numbers
# -l = show filenames only (for counting affected files)
# --include="*.js" --include="*.jsx" = JS/JSX files only
# | grep -v "\.test\.\|\.spec\.\|__tests__" = exclude test files
# | grep -v "node_modules" = safety (usually handled by not scanning node_modules)
# 2>/dev/null = suppress "no files found" errors

# Source files only (exclude tests):
SRC_FLAGS='--include="*.js" --include="*.jsx"'
EXCLUDE_TESTS='grep -v "\.test\.\|\.spec\.\|__tests__"'

# Test files only:
TEST_FLAGS='--include="*.test.js" --include="*.test.jsx" --include="*.spec.js" --include="*.spec.jsx"'
```

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
