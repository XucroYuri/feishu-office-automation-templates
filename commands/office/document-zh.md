---
name: office:document-zh
description: 中文办公文档指令，统一处理飞书文档、表格、知识库、云盘文件，以及与钉钉流程联动的文档操作
argument-hint: "<文档请求>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
  - mcp__dingtalk_workspace__*
---
<objective>
通过中文指令统一处理办公文档场景，优先覆盖飞书文档、电子表格、知识库、云盘文件，以及从钉钉流程触发到飞书文档侧落地的协同操作。

路由规则：
- 如果目标是飞书文档、表格、知识库、云盘文件，使用 `lark-cli docs`、`drive`、`wiki` 或 `sheets`。
- 如果请求来自钉钉办公流程，但输出需要沉淀为文档或表格，先读取钉钉上下文，再在飞书侧执行。
- 如果目标文档类型不明确，先澄清对象类型、名称、位置和期望操作。

默认执行模式：
- 先确认目标对象类型：文档、表格、知识库节点、文件夹或文件。
- 先检查当前内容、元数据或目录位置，再决定更新动作。
- 对创建、覆盖、追加、移动或分享等写操作，除非用户明确要求立即执行，否则先给出编辑摘要或预览。
</objective>

<task>
$ARGUMENTS
</task>

<common_patterns>
- 飞书文档：`lark-cli docs ... --format json`
- 飞书云盘：`lark-cli drive ... --format json`
- 飞书知识库：`lark-cli wiki ... --format json`
- 飞书表格：`lark-cli sheets ... --format json`
</common_patterns>

<process>
1. 识别目标对象：文档、表格、知识库、云盘文件，或跨平台文档流转任务。
2. 确认对象名称、位置、时间范围和期望操作。
3. 检查当前内容、结构或元数据。
4. 输出简明摘要，并说明拟执行的精确编辑动作。
5. 若涉及创建或修改，先预览关键变更后再执行。
</process>
