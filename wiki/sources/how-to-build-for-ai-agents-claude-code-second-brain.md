---
type: source
title: "How to Build for AI Agents and a Claude Code Second Brain"
url: https://creatoreconomy.so/p/how-to-build-for-ai-agents-and-a-claude-code-second-brain
author: Peter Yang (interviewer), Ryan Wiggins (Mercury VP of Product)
date: 2026-04-22
platform: Substack (Behind the Craft)
topics: [AI Agents, Claude Code, Second Brain, MCP, Product Strategy]
---

# How to Build for AI Agents and a Claude Code Second Brain

> Mercury's VP of Product on building for AI agents, his Claude Code second brain, and what Mercury data reveals about OpenAI vs. Anthropic

---

## TL;DR

Ryan Wiggins (Mercury VP of Product) 分享了他构建 Claude Code "second brain" 的 5 阶段方法论，以及关于 AI agent 时代产品建设的洞察。核心观点：APIs 和 MCPs 正在成为 AI agent 的主要接口，产品开发流程将被永久改变。

---

## 核心观点

### 1. AI Agent 时代的产品建设

- **APIs and MCPs are the primary interface** — AI agents 的首选接口正在从 GUI 转向 API 和 MCP
- **Agent-ready product** — 产品需要为 AI agent 访问而设计，不仅仅是为人类用户
- **MCP vs CLI trade-offs** — 在 MCP 和 CLI 之间做选择时需要考虑 cannibalization 等因素

### 2. Claude Code Second Brain (5 阶段方法论)

Ryan 构建了一个基于 5 年工作历史的 "second brain"，生产力提升 2x：

#### Phase 1: Create a profile
让 Claude 采访你，编写 `me.md` 捕捉角色、目标、工作风格和成长边界。

#### Phase 2: Build the knowledge base
保存关键文档（specs、retros、绩效评估）到本地，安装 QMD (Shopify CEO 的向量搜索工具) 供 Claude 引用。

#### Phase 3: Distill the data
生成摘要文件：
- `strategic-context.md` — 公司/团队的目标和原因
- `personal-growth.md` — 反馈模式、教练主题

#### Phase 4: Auto-context injection
创建 Claude Code hook，自动从上述文件提取上下文注入每个 prompt。

#### Phase 5: Learning loop
构建 `/learn` skill，会话后自动更新 `Claude.md`，加上 cron jobs 用于早间简报和月度回顾。

### 3. Mercury 数据洞察

- **OpenAI vs Anthropic**: Mercury 数据显示创业公司正在转向 Anthropic
- **Enterprise race**: 两家公司在企业市场的竞争态势

### 4. AI Coaching

- 使用 AI 在每次会议后进行教练和反思
- 将 AI 作为个人成长伙伴

---

## 关键引用

> "Ryan built a Claude Code 'second brain' trained on 5 years of work history that helped him 2x his productivity as a product leader."

> "The product development process will never be the same."

---

## 相关概念

- [[Claude Code Second Brain]] — 个人知识管理系统
- [[Agent-Ready Product]] — 为 AI agent 设计的产品
- [[MCP]] — Model Context Protocol
- [[AI Coaching]] — AI 驱动的个人教练
- [[QMD]] — Shopify CEO 的向量搜索工具

---

## 相关实体

- [[Ryan Wiggins]] — Mercury VP of Product
- [[Peter Yang]] — Behind the Craft 作者
- [[Mercury]] — 金融科技公司
- [[Anthropic]] — AI 公司
- [[OpenAI]] — AI 公司
- [[Claude Code]] — Anthropic 的 coding agent

---

## 来源

- 原始资料：[[raw/articles/how-to-build-for-ai-agents-claude-code-second-brain]]
- 播客：YouTube, Apple Podcasts, Spotify
