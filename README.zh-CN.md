# 飞书办公自动化模板

> 基于 `lark-cli` 的可复用飞书 / Lark 办公自动化命令模板集合。

[English](README.md) · [贡献指南](CONTRIBUTING.md) · [许可证](LICENSE) · [版本说明](RELEASE-v0.1.0.md)

## 项目简介

本仓库用于沉淀可复用的飞书办公自动化模板，适合接入助手系统、命令路由器、内部自动化平台，以及需要稳定执行边界的 Agent 工作流。

它的目标不是单次脚本，而是一套能长期复用、可拆分、可扩展、可开源维护的模板资产。

## 核心亮点

- 提供覆盖常见办公场景的飞书模板
- 提供双语统一入口，适合办公指挥型路由
- 提供中文子命令模板，适合日常直接使用
- 默认遵循“先读后写、先预览后执行”
- 模板结构清晰，适合二次封装和团队内部复用

## 覆盖场景

- 联系人和人员检索
- 聊天消息起草与发送
- 日程查询与时间协调
- 文档、表格、知识库、云盘操作
- 任务与任务清单流转
- 办公自动化统一路由入口

## 模板索引

### 飞书基础模板

- `commands/lark/workspace.md`
- `commands/lark/message.md`
- `commands/lark/calendar.md`
- `commands/lark/document.md`
- `commands/lark/task.md`

### 办公路由模板

- `commands/office/workspace.md`
- `commands/office/workspace-zh.md`
- `commands/office/message-zh.md`
- `commands/office/calendar-zh.md`
- `commands/office/document-zh.md`
- `commands/office/task-zh.md`

## 仓库结构

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

## 设计原则

- 先读取状态，再执行变更
- 优先结构化输出，减少模糊解析
- 写操作默认先预览、先确认
- 路由不明确时先澄清平台和对象
- 同时提供中文入口与双语入口，兼顾团队落地与开源传播

## 快速开始

### 1. 准备飞书访问能力

建议先完成初始化：

```bash
lark-cli config init --new
lark-cli auth login --recommend
```

### 2. 选择模板入口

- 飞书单平台场景：使用 `commands/lark/*`
- 统一办公路由场景：使用 `commands/office/workspace.md`
- 中文办公入口场景：使用 `commands/office/*-zh.md`

### 3. 保持安全执行方式

- 先检查当前状态
- 先总结结论，再决定是否变更
- 写操作尽量保留预览或确认步骤

## 适用场景

- 为内部办公助手构建飞书能力包
- 统一团队的消息、日程、任务执行口径
- 在 Agent 框架中复用办公自动化提示模板
- 面向中文团队提供可直接执行的命令入口

## CLI 基础能力

本仓库模板默认依赖以下飞书命令：

- `lark-cli contact`
- `lark-cli im`
- `lark-cli calendar`
- `lark-cli docs`
- `lark-cli drive`
- `lark-cli wiki`
- `lark-cli sheets`
- `lark-cli task`

## 说明

- 本仓库不包含账号、租户 ID、密钥、组织专属配置。
- 如果你接入的是自定义助手环境，可以按需要调整模板的 frontmatter、说明文案和路由规则。

## 参与贡献

欢迎贡献，但建议保持以下约束：

- frontmatter 稳定
- 路由规则明确
- 写操作安全边界清晰
- 中英文文档同步维护

详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 许可证

本仓库使用 MIT License，见 [LICENSE](LICENSE)。
