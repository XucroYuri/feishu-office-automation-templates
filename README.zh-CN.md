# 飞书办公自动化模板

基于 `lark-cli` 的可复用飞书/Lark 办公自动化命令模板集合。

English version: [README.md](README.md)

## 仓库范围

本仓库沉淀了以下场景的可复用模板：

- 联系人和人员检索
- 消息起草与发送
- 日程查询与时间协调
- 文档、表格、知识库、云盘操作
- 任务与任务清单流转
- 办公自动化统一路由入口

## 内置模板

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

## 目录结构

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

## 设计原则

- 先读后写
- 优先结构化输出
- 写操作默认先预览再执行
- 路由不明确时先澄清目标平台和对象
- 同时提供中文入口和双语入口

## CLI 基础能力

典型飞书能力依赖以下命令：

- `lark-cli contact`
- `lark-cli im`
- `lark-cli calendar`
- `lark-cli docs`
- `lark-cli drive`
- `lark-cli wiki`
- `lark-cli sheets`
- `lark-cli task`

## 使用建议

1. 先完成飞书配置与授权。
2. 按场景选用现成模板，必要时再复制修改。
3. 对消息、文档、任务等写操作，默认保留预览确认步骤。

## 说明

- 仓库不内置账号、凭据和组织配置。
- 建议初始化命令：
  - `lark-cli config init --new`
  - `lark-cli auth login --recommend`

## 许可证

本仓库使用 MIT License。
