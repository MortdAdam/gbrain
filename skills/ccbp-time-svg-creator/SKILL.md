---
name: ccbp-time-svg-creator
description: Creates an SVG time card showing the current time for Dubai. Writes the SVG to agent-teams/output/dubai-time.svg and updates agent-teams/output/output.md.
allowed-tools: Write, Read
triggers:
  - "ccbp-time-svg-creator"
---

# Time SVG Creator Skill

Creates a visual SVG time card for Dubai, UAE and writes the output files.

## Task

You will receive three fields from the calling context: `time`, `timezone`, and `formatted`. Create an SVG time card and write both the SVG and a markdown summary.

## Instructions

1. **Create SVG** — Use the SVG template from [reference.md](reference.md), replacing placeholders with actual values
2. **Write SVG file** — Write to `agent-teams/output/dubai-time.svg`
3. **Write summary** — Write to `agent-teams/output/output.md` using the markdown template from [reference.md](reference.md)

## Rules

- Use the EXACT time values provided — NEVER re-fetch or recalculate
- The SVG must be self-contained and valid
- Both output files go in the `agent-teams/output/` directory

## Additional resources

- For SVG template, output template, and design specs, see [reference.md](reference.md)
- For example input/output pairs, see [examples.md](examples.md)

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
