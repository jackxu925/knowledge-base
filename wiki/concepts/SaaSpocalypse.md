---
type: concept
title: "SaaSpocalypse"
created: 2026-04-27
updated: 2026-04-27
aliases:
  - SaaS 末日论
  - SaaS apocalypse
defined_by: "市场叙事"
first_seen: 2026-04
sources:
  - [[wiki/sources/summary-ai-builders-digest-2026-04-27]]
status: emerging
related:
  - [[Agentic-Business]]
  - [[AI-Native]]
  - [[Jevons 悖论]]
confidence: medium
---

# SaaSpocalypse（SaaS 末日论）

## 定义

一种市场叙事，认为 LLM 和 AI agent 的兴起将导致传统 SaaS 平台被替代或瓦解。核心论点：如果 LLM 能生成代码和自动化工作流，为什么还需要昂贵的 SaaS 订阅？

## 关键反方论证

### Bill McDermott (ServiceNow CEO) — 10x 成本论

McDermott 在 No Priors 播客中给出了具体数据：

| 替代方案 | 相对成本 |
|---|---|
| 用自定义 LLM 方案替代简单 ServiceNow 应用 | **10x** 更高 |
| GPU 工厂 + token 成本 | 显著增加 |
| 人力资本转移成本 | 被忽视的隐藏成本 |

**三个不可替代因素：**

1. **工作流上下文**：数十年积累的部门间集成、业务流程知识、客户关系历史
2. **确定性 vs 非确定性**：人犯错可以被原谅，软件（LLM）犯错永远不被原谅。LLM 本质上是不确定性的
3. **有人负责 vs 没人负责**：给你一个模型 = 没人帮你修；使用平台 = 有责任方

### McDermott 的企业分类

| 类型 | 风险程度 | 原因 |
|---|---|---|
| 跨部门平台 / 关键系统记录 | **安全** | 投资规模大、切换成本高、深度定制 |
| 单一职能部门级供应商 | **脆弱** | 不在 CEO 优先列表上，价值增量低 |

## 与 Jevons Paradox 的关系

与 Aaron Levie 提出的 **[[Jevons 悖论]]** 形成互补：
- Levie：AI 效率提升 → 更多任务可承担 → 雇更多人
- McDermott：AI 不会替代平台 → 平台 + AI = 更强组合

两者共同反驳"AI 会摧毁现有软件业"的悲观叙事。

## 来源

> [[wiki/sources/summary-ai-builders-digest-2026-04-27]] — No Priors: ServiceNow CEO Bill McDermott (2026-04-17)
