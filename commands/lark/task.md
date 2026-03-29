---
name: lark:task
description: Inspect, summarize, or update Feishu/Lark tasks
argument-hint: "<task request>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
---
Use `lark-cli task` commands with `--format json`.

Process:
1. Clarify task scope: my tasks, a list, due soon, completed, or a specific task.
2. Fetch task data.
3. Summarize by status, assignee, or urgency.
4. For mutations, confirm exact task fields before execution.
