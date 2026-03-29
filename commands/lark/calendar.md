---
name: lark:calendar
description: Check Feishu/Lark agenda, meetings, free-busy, or calendar events
argument-hint: "<date, person, or calendar request>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
---
Use `lark-cli` calendar commands with `--format json` to inspect agenda and event information.

Process:
1. Clarify date range, timezone, and target calendar if missing.
2. Fetch agenda or events.
3. Summarize meetings, conflicts, and free slots.
4. For mutations, confirm title, time, attendees, and calendar before execution.
