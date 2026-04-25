---
type: concept
title: Queryable
aliases: [可查询的, Legible, 可读的]
defined_by: YC / Diana Hu
first_seen: 2026-04-25
sources:
  - [[yc-ai-native-team-guide]]
related:
  - [[AI Native]]
  - [[闭环系统]]
  - [[Artifact]]
status: stable
---

# Queryable / Legible（可查询的 / 可读的）

## 定义

让公司所有信息与状态对 AI **可读、可检索、可分析**。组织的信息与流程对 AI 透明、无歧义，使 AI 能够像人类员工一样获取上下文并做出判断。

## 为什么重要

要构建 [[闭环系统]]，必须让整个组织对 AI 是 Legible 的。如果 AI 无法读取公司的信息，就无法参与决策和自我改进。

## 具体要求

1. **用 AI 笔记工具记录会议**，减少私信和邮件
2. **在所有沟通渠道中嵌入 AI Agent**（Slack、邮件、项目管理工具）
3. **为各部门建立定制化仪表板**：
   - 收入与销售
   - 工程进度
   - 招聘状态
   - 运营指标

## 工程管理示例

如果 AI Agent 能访问：
- Linear tickets
- Slack 工程频道
- 客户反馈（邮件 / Pylon）
- GitHub 仓库
- Notion / Google Doc 中的高层计划
- 销售电话录音
- 每日站会记录

它就能分析：
- 上个 Sprint 实际交付了什么
- 是否满足客户真实需求
- 提出更准确的未来 Sprint 计划

## 核心原则

> 为模型提供与给员工同样多的上下文。

## 转变

公司将从：
- 信息碎片化、需人工解释的 [[开环系统]]

变成：
- 始终拥有最新视图、知道实际发生了什么的 [[闭环系统]]
