# Feishu Office Automation Templates

> Reusable Feishu/Lark office automation templates built on top of `lark-cli`.

[![Release](https://img.shields.io/github/v/release/XucroYuri/feishu-office-automation-templates)](https://github.com/XucroYuri/feishu-office-automation-templates/releases)
[![License](https://img.shields.io/github/license/XucroYuri/feishu-office-automation-templates)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/XucroYuri/feishu-office-automation-templates)](https://github.com/XucroYuri/feishu-office-automation-templates/commits/main)

[中文文档](README.zh-CN.md) · [Contributing](CONTRIBUTING.md) · [License](LICENSE) · [Release Notes](RELEASE-v0.1.0.md)

## Overview

This repository packages reusable command templates for building Feishu/Lark-powered office automation workflows.

It is designed for assistant environments, prompt routers, internal automation tools, and command-based agent systems that need predictable Feishu operations with clear execution boundaries.

## Highlights

- ready-to-reuse command templates for common Feishu/Lark workflows
- bilingual entry point for office-wide routing
- Chinese command templates for daily operational use
- explicit read-first and preview-first execution model
- template structure suitable for internal reuse or open-source extension

## What This Repository Covers

- contact and people lookup
- chat and message drafting
- calendar and agenda coordination
- docs, sheets, wiki, and drive operations
- task workflows and list-based task management
- workspace-level routing for office automation requests

## Template Index

### Core Feishu Templates

- `commands/lark/workspace.md`
- `commands/lark/message.md`
- `commands/lark/calendar.md`
- `commands/lark/document.md`
- `commands/lark/task.md`

### Office Routing Templates

- `commands/office/workspace.md`
- `commands/office/workspace-zh.md`
- `commands/office/message-zh.md`
- `commands/office/calendar-zh.md`
- `commands/office/document-zh.md`
- `commands/office/task-zh.md`

## Repository Structure

```text
.
|-- commands/
|   |-- lark/
|   `-- office/
|-- CHANGELOG.md
|-- CONTRIBUTING.md
|-- LICENSE
|-- README.md
|-- README.zh-CN.md
`-- RELEASE-v0.1.0.md
```

## Design Principles

- Read first, mutate second.
- Prefer structured output with `--format json`.
- Preview write actions before execution whenever possible.
- Keep platform routing explicit when a request is ambiguous.
- Make Chinese and bilingual command entry points available for operational teams.

## Quick Start

### 1. Prepare Feishu access

Suggested bootstrap commands:

```bash
lark-cli config init --new
lark-cli auth login --recommend
```

### 2. Pick a template

- Use `commands/lark/*` for Feishu-only workflows.
- Use `commands/office/workspace.md` for bilingual routing.
- Use `commands/office/*-zh.md` for Chinese operational entry points.

### 3. Keep execution safe

- inspect current state first
- summarize findings before mutation
- preview or restate write actions before execution

## Example Entry Points

### Feishu-only Workspace Routing

```text
Use commands/lark/workspace.md to inspect a user's tasks due this week and summarize by urgency.
```

### Chinese Office Routing

```text
使用 commands/office/task-zh.md 汇总我的飞书任务，并按截止时间输出待办优先级。
```

## Typical Usage Scenarios

- building a Feishu command pack for an internal assistant
- standardizing message, calendar, and task flows across a team
- reusing office automation prompts in agent frameworks
- offering Chinese-friendly operational commands without losing structured behavior

## Who This Is For

- teams building internal Feishu assistants
- developers packaging reusable prompt or command assets
- operators who need Chinese command entry points with safer execution defaults
- automation builders who want structured command templates instead of ad-hoc prompts

## Who This Is Not For

- projects that need direct SDK code rather than template assets
- one-off scripts with no reuse requirements
- environments that do not use `lark-cli` at all

## CLI Baseline

Typical Feishu operations in these templates rely on:

- `lark-cli contact`
- `lark-cli im`
- `lark-cli calendar`
- `lark-cli docs`
- `lark-cli drive`
- `lark-cli wiki`
- `lark-cli sheets`
- `lark-cli task`

## Notes

- This repository does not include credentials, tenant IDs, or environment-specific configuration.
- You are expected to adapt template wording and routing details to your own assistant runtime when needed.

## Contributing

Contributions are welcome if they preserve:

- stable frontmatter
- explicit routing logic
- safe write behavior
- alignment between English and Chinese documentation

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## Security

If you discover a security issue or a template misuse risk, see [SECURITY.md](SECURITY.md).

## License

Released under the MIT License. See [LICENSE](LICENSE).
