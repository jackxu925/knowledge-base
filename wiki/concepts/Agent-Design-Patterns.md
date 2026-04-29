---
type: concept
title: "Agent Design Patterns"
created: 2026-04-28
updated: 2026-04-28
related: [[AI Coding]], [[Claude Code]], [[GStack]], [[SOUL.md]]
aliases:
  - Agent 设计模式
  - AI Agent 架构
  - Agent 人格设计
defined_by: Multiple (Garry Tan, Guillermo Rauch, Peter Steinberger)
first_seen: 2026-04-27 (Garry Tan SOUL.md tweet)
sources:
  - raw/news/ai-builders-digest-2026-04-27.md
  - raw/news/ai-builders-digest-2026-04-28.md
status: active
confidence: high
---

# Agent Design Patterns

## 概述

AI Agent 的设计模式正在从简单的 system prompt 演进到**结构化的人格/操作框架**。核心洞察：**通用指令 → 通用输出**。要让 Agent 表现得像一个有个性、有判断力的"人"，需要精心设计的架构。

## Garry Tan 三文件法

YC CEO Garry Tan 公开了他打造有表现力 Agent 的三个核心文件：

### 1. SOUL.md — Agent 是谁

不是 system prompt，而是**宪法**。定义：
- 声音和语调（Voice）
- 价值观和运作原则
- 好输出和坏输出的标准
- 具体且有个性的规则示例

> Generic instructions → generic output（ChatGPT 式回答）
> Specific opinionated rules → alive output（有灵魂的输出）

**示例对比**：
| 普通 | 有表现力 |
|------|---------|
| "be helpful and concise" | "speak like a peer with taste, one sentence when one sentence works, uncomfortable truths welcome if actually true, language with voltage" |
| "be polite" | "brevity is mandatory; humor is mandatory; never open with 'Great question'; swearing is allowed when it lands" |

### 2. USER.md — 用户是谁

不是简历，而是**深度模型**：
- 思维方式如何工作
- 正在构建什么项目
- 优势和盲点
- 家庭和个人情况
- 性格和触发因素
- 关心什么

Garry Tan 的 USER.md 约 **4000 字**。核心原理：Agent 对用户了解越多，服务越好。

### 3. AGENTS.md — 操作规则

纯操作层：
- 每条消息检查什么
- 绝对不能做什么
- 如何处理失败
- 查找链 (Lookup chains)
- 路径规则
- Brain-first 协议

## Guillermo Rauch: 编码 Agent = 超级智能基础

Vercel CEO Rauch 提出编码 Agent 将成为所有超级智能的基础，关键论据：

### 编码能力 = 计算机熟练度

掌握 bash、文件系统、程序配置安装 → "proficiency with computers"

### 自我改进能力是关键差异化

Agent 可以：
- 检查自己的源代码、状态、技能、指令
- 提议修改自身（需人类监督 + 审计追踪）
- 直接自我变异

> "What I cannot create, I cannot understand." — Feynman（通过 Rauch 引用）

## 实际应用案例

### OpenClaw 的健康守则 (Peter Steinberger / Garry Tan)

Garry Tan 分享：他的 OpenClaw agent 知道他的完整日程和健康目标，并在**凌晨 12:30 后拒绝响应查询**。这展示了 Agent 设计中融入个人生活边界的可能性。

### MCP Server for Fitness App (Peter Yang)

Roblox 产品负责人 Peter Yang 为移动健身应用构建了 MCP 服务器，使 Claude/Codex 等工具可以获取健身数据和更新训练计划。这是 **Agent ↔ 现实世界应用集成** 的实际案例。

### birdclaw — 本地推文知识库 (Peter Steinberger)

OpenClaw 创始者 steipete 发布 birdclaw：导入 X 归档并备份到 GitHub，支持定时任务每日导入书签。这是为 Agent 构建**持久化个人知识库**的工具。

## 设计原则总结

1. **人格 > 功能**: 先定义 Agent "是谁"，再定义它 "做什么"
2. **深度用户模型**: 对用户的理解越深，Agent 服务越好
3. **操作与人格分离**: SOUL.md 定义身份，AGENTS.md 定义行为
4. **边界意识**: Agent 应该知道什么时候不行动（如深夜拒答）
5. **自我改进能力**: 编码 Agent 的终极优势是能审查和修改自己
