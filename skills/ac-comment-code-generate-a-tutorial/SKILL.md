---
name: ac-comment-code-generate-a-tutorial
description: 'Transform this Python script into a polished, beginner-friendly project by refactoring the code, adding clear instructional comments, and generating a complete markdown tutorial.'
triggers:
  - "ac-comment-code-generate-a-tutorial"
---

Transform this Python script into a polished, beginner-friendly project by refactoring the code, adding clear instructional comments, and generating a complete markdown tutorial.

1. **Refactor the code**  
   - Apply standard Python best practices  
   - Ensure code follows the PEP 8 style guide  
   - Rename unclear variables and functions if needed for clarity

1. **Add comments throughout the code**  
   - Use a beginner-friendly, instructional tone  
   - Explain what each part of the code is doing and why it's important  
   - Focus on the logic and reasoning, not just syntax  
   - Avoid redundant or superficial comments

1. **Generate a tutorial as a `README.md` file**  
   Include the following sections:
   - **Project Overview:** What the script does and why it's useful  
   - **Setup Instructions:** Prerequisites, dependencies, and how to run the script  
   - **How It Works:** A breakdown of the code logic based on the comments  
   - **Example Usage:** A code snippet showing how to use it  
   - **Sample Output:** (Optional) Include if the script returns visible results  
   - Use clear, readable Markdown formatting

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
