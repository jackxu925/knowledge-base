---
type: concept
title: "Agent Architecture (Agent 架构)"
created: 2026-05-04
updated: 2026-05-04
related: [[Anthropic]], [[Managed-Agents]], [[Human-Middleware]], [[AI-Coding]]
confidence: high
aliases: [Agent架构, 智能体架构]
first_seen: "2024-01"
status: active
---

# Agent Architecture (Agent 架构)

## 核心定义

Agent 架构是指构建 AI Agent 系统的设计模式，特别是如何将 LLM（大脑）与执行环境（手）组织在一起。

## 2026 年关键范式转变

### 1. 从 API-first 到 Agent-first

**Justine Moore (a]6z)**:
> "我们正在看到从 API-first 到 agent-first 架构的转变。应用层正在围绕持续 agent 工作流重建，而非无状态的 API 调用。"

### 2. 大脑与手的解耦

**Bob van Heuveln (Thoughtful AI)**:
> "构建有效 AI agents 的关键是将'大脑'(LLM + harness)与'手'(执行环境/工具)分离。这种解耦允许每个组件独立失败和替换。"

### 3. Anthropic 的实践: Managed Agents

**Anthropic Engineering** 发布的 Managed Agents 架构：

- **Session**: 事件日志，作为持久化上下文存储在 LLM 上下文窗口之外
- **Harness**: 调用 LLM 并路由工具调用的循环
- **Sandbox**: LLM 执行代码和编辑文件的沙箱环境

核心创新：
- 接口设计不依赖于具体实现
- 容器变成"cattle"而非"pet"——失败后可重启
- 多个 brain 可以共享多个 hands

## 未来工作模式

**Dan Shipper (Every CEO)**:
> "未来 10 年的工作模式：左侧是持续运行的 agent，右侧是你和 agent 共同使用的应用程序。"

```
┌─────────────────────┐     ┌─────────────────────┐
│   Agent (left)     │     │  Application (right)│
│  Running           │ ←→  │  You + Agent        │
│  Continuously      │     │  Use Together       │
└─────────────────────┘     └─────────────────────┘
```

## 架构类型

| 类型 | 描述 | 代表 |
|------|------|------|
| Coupled | 大脑和手在同一个容器 | 早期实现 |
| Decoupled | 大脑和手分离，通过接口通信 | Anthropic Managed Agents |
| Multi-brain | 多个大脑协同工作 | Agent 编排系统 |
| Multi-hand | 一个大脑控制多个执行环境 | 复杂任务系统 |

## 相关实体

- [[Anthropic]] - Managed Agents 设计者
- [[Justine-Moore]] - 架构趋势观察者
- [[Bob-van-Heuveln]] - Agent 架构实践者

## 参考来源

- [[summary-ai-builders-digest-2026-05-04]]
- https://www.anthropic.com/engineering/managed-agents