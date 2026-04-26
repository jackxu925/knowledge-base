---
type: concept
title: Agent Mining
aliases: [代理挖掘]
defined_by: [[SAP]]
first_seen: 2026-04-26
sources:
  - [[summary-ai-builders-digest-2026-04-26]]
related:
  - [[Managed Agents]]
  - [[RPT-1]]
  - [[AI-Native]]
status: emerging
---

# Agent Mining（代理挖掘）

SAP CTO Philipp Herzig 提出的新概念：**Process Mining（流程挖掘）的 AI Agent 时代演进版**。

## 核心思想

传统 Process Mining 记录人类在固定流程中的操作轨迹。Agent Mining 则记录 **AI Agent 的所有决策轨迹和用户输入**，捕获：

- 存在于人脑中的"部落知识"（tribal knowledge）
- Slack/Teams/电话中的非结构化讨论
- Agent 向人类的提问和人类的回答

## 数据飞轮

```
Agent 决策轨迹 + 用户输入
    ↓
记录到 Session / Observability
    ↓
发现异常 → 纠正 OR 发现优化 → 升级为新 SOP
    ↓
产出新的 Eval 数据集
    ↓
优化 Agent 行为
```

## 两种用途

| 类型 | 说明 | 举例 |
|------|------|------|
| 异常检测 | 偏离标准操作流程的行为 | 英国团队做了不该做的操作 |
| 流程优化 | 发现更好的工作方式 | 澳大利亚的创新做法推广到全球 |

## 与 Eval 的关系

Agent Mining 的输出直接成为 **Eval 数据集**的来源：
- 经过验证的决策 = 正确的期望输出
- 用这些数据训练/优化 Agent

来源：[[summary-ai-builders-digest-2026-04-26]] — SAP CTO on No Priors Podcast
