---
name: ccbp-time-skill
description: Display the current time in Pakistan Standard Time (PKT, UTC+5). Use when the user asks for the current time, Pakistan time, or PKT.
user-invocable: true
triggers:
  - "ccbp-time-skill"
---

# Time Skill

This skill displays the current date and time in Pakistan Standard Time (PKT).

## Task

Display the current date and time in Pakistan Standard Time (UTC+5).

## Instructions

1. **Get Current Time**: Run the following bash command:
   ```
   TZ='Asia/Karachi' date '+%Y-%m-%d %H:%M:%S %Z'
   ```

2. **Display Result**: Show the time in this format:
   ```
   Current Time in Pakistan (PKT): YYYY-MM-DD HH:MM:SS PKT
   ```

## Requirements

- Always use the `Asia/Karachi` timezone (UTC+5)
- Use 24-hour format
- Include the date alongside the time
- Keep the output concise — no extra commentary

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
