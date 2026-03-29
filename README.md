# Feishu Office Automation Templates

Reusable Feishu/Lark command templates built on top of `lark-cli`.

中文说明见 [README.zh-CN.md](README.zh-CN.md)。

## Scope

This repository packages reusable command templates for:

- contacts and people lookup
- messages and chat delivery
- calendar and agenda coordination
- documents, sheets, wiki, and drive operations
- tasks and task-list workflows
- workspace-level routing for common office automation tasks

## Included Templates

- `commands/lark/workspace.md`
- `commands/lark/message.md`
- `commands/lark/calendar.md`
- `commands/lark/document.md`
- `commands/lark/task.md`
- `commands/office/workspace.md`
- `commands/office/workspace-zh.md`
- `commands/office/message-zh.md`
- `commands/office/calendar-zh.md`
- `commands/office/document-zh.md`
- `commands/office/task-zh.md`

## Repository Layout

```text
commands/
  lark/
  office/
README.md
README.zh-CN.md
CONTRIBUTING.md
LICENSE
.gitignore
```

## Design Principles

- read state first, mutate second
- prefer structured output with `--format json`
- preview or restate write actions before execution
- keep routing explicit when a request is ambiguous
- make Chinese and bilingual command entry points available for daily use

## CLI Baseline

Typical Feishu operations are expected to use:

- `lark-cli contact`
- `lark-cli im`
- `lark-cli calendar`
- `lark-cli docs`
- `lark-cli drive`
- `lark-cli wiki`
- `lark-cli sheets`
- `lark-cli task`

## Suggested Usage

1. Configure Feishu access.
2. Copy or adapt the templates you need.
3. Keep write operations preview-first unless the scenario requires immediate execution.

## Notes

- Feishu authentication and configuration are intentionally not hardcoded here.
- Suggested bootstrapping commands:
  - `lark-cli config init --new`
  - `lark-cli auth login --recommend`

## License

This repository is released under the MIT License.
