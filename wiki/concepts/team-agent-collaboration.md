---
type: concept
title: 团队 Agent 协作
aliases: [Team Agent Collaboration, Multi-Agent Team, Agent Identity]
defined_by: []
first_seen: 2026-05-09
sources:
  - [[anthropic-ai-agent-rewriting-enterprise-workflow]]
related:
  - [[Managed-Agents]]
  - [[agent-primitives]]
  - [[mcp]]
confidence: high
status: active
updated: 2026-05-09
---

# 团队 Agent 协作（Team Agent Collaboration）

当 Agent 从个人工具走向团队常驻系统，协作形态发生根本变化：不再是聊天窗口里的提示词，而是需要**多人可见的会话、权限体系、审计轨迹**。

## 核心差异：Skill vs. 团队 Agent

| 维度 | Skill | 团队 Agent |
|------|-------|-------------|
| 运行环境 | 单次对话 | 独立会话、持久运行 |
| 多人访问 | 不支持 | 支持共享上下文、共同查看输出 |
| 权限 | 无 | 需要认证、权限层级、负责人 |
| 人工介入 | 即时 | 可配置触发条件（如法务审稿 Agent） |

## 组织形态变化

- 平台团队写底层系统
- 业务同事通过 Claude 改规则/配置，生成可 review 的 PR
- 不直接碰核心代码，但能调整 Agent 行为
- **人人都能改 Agent ≠ 人人都直接改核心系统**

## Anthropic 内部案例：法律审稿流程

1. 市场同事提交文案
2. 法律审稿 Agent 按规则做第一轮检查
3. 清楚的内容直接放行，拿不准的进入法务收件箱
4. Agent 接 MCP server 读外部上下文，用 skills 存规则
5. 通过小 app 让市场和法务共同查看结果

**Agent 没有取消人的判断，而是把重复的第一遍筛查前置。**

## 需要的基础设施

- 共享会话（谁都能看 Agent 的输出）
- 权限层级（谁能改、谁能看、谁负责）
- 审计轨迹（每次 Agent 动作可追溯）
- Agent identity（常驻 Slack 的 Agent 需要独立身份）

## 参考

- 来源：[[anthropic-ai-agent-rewriting-enterprise-workflow]]
- 关联：[[Managed-Agents]]、[[agent-primitives]]、[[mcp]]
