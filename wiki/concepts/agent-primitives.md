---
type: concept
title: Agent 平台原语
aliases: [Agent Primitives, Filesystem Primitive, Skills Primitive, Vaults]
defined_by: []
first_seen: 2026-05-09
sources:
  - [[anthropic-ai-agent-rewriting-enterprise-workflow]]
related:
  - [[Managed-Agents]]
  - [[agent-skill-system]]
  - [[mcp]]
confidence: high
status: active
updated: 2026-05-09
---

# Agent 平台原语（Agent Primitives）

Anthropic 在推进 Claude 平台时明确提出：平台会在一些地方保持 opinionated，让 Claude 使用文件系统、鼓励使用 skills，把这些原语和模型的工作方式绑得更紧。

## 核心原语

### 1. Filesystem（文件系统）
- 看似只是交互方式，实际会影响模型怎么读项目、怎么修改文件、怎么留下中间结果
- 模型通过文件系统持久化中间状态，使多步任务可恢复
- 与 stateful API 演进直接相关

### 2. Skills（技能）
- 把组织经验做成可调用的能力，让 Claude 在任务中复用
- 帮助 Agent 在新模型发布时快速升级
- 平台鼓励使用 skills，使其成为 Claude 的"工作手势"

### 3. Vaults（凭证原语）
- 更底层的认证/凭证管理能力
- 为 Agent identity、Slack 集成、一键部署等产品化入口打基础
- 解决"用户凭证放在哪里"的规模问题

## 平台设计含义

这些原语不是中立的——它们会影响模型擅长什么、产品怎么搭。Angela 承认这些选择像小注脚，时间拉长后会影响整个生态。

## 与 harness 的关系

原语是底层能力，harness 是编排方式。未来竞争发生在 Agent 配方层：模型、工具、记忆和执行环境怎么绑在一起。

## 参考

- 来源文章：[[anthropic-ai-agent-rewriting-enterprise-workflow]]
- 关联：[[Managed-Agents]]、[[agent-skill-system]]、[[mcp]]
