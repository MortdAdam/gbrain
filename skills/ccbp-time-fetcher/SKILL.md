---
name: ccbp-time-fetcher
description: Instructions for fetching current Dubai time via bash command
user-invocable: false
triggers:
  - "ccbp-time-fetcher"
---

## Dubai Time Fetcher

### Command

```bash
TZ='Asia/Dubai' date '+%Y-%m-%d %H:%M:%S %Z'
```

### Expected Output Format

`YYYY-MM-DD HH:MM:SS +04` (Gulf Standard Time)

### Timezone Details

- Timezone: Asia/Dubai
- Offset: UTC+4
- Abbreviation: GST (Gulf Standard Time)
- Dubai does not observe daylight saving time

### Return Format

Provide the following fields:
- `time`: Just the time portion (HH:MM:SS)
- `timezone`: "GST (UTC+4)"
- `formatted`: The full output string from the command

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
