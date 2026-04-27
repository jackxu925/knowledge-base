---
type: concept
title: "Agentic Business"
created: 2026-04-27
updated: 2026-04-27
aliases:
  - Agent 化企业
  - Agentic Enterprise
  - AI Control Tower
defined_by: "ServiceNow / 行业实践"
first_seen: 2026-04
sources:
  - [[wiki/sources/summary-ai-builders-digest-2026-04-27]]
status: emerging
related:
  - [[SaaSpocalypse]]
  - [[Managed-Agents]]
  - [[AI-Native]]
confidence: medium
---

# Agentic Business（Agent 化企业）

## 定义

一种新兴的企业运营模式，将 AI agent 深度集成到业务流程中，使 agent 承担大量重复性、规则性工作，人类聚焦于创新、关系建立和关键决策。

## 核心架构：AI 控制塔（AI Control Tower）

Bill McDermott (ServiceNow CEO) 提出的框架：

```
                    ┌─────────────────┐
                    │   AI 控制塔      │
                    │  (ServiceNow)   │
                    └────────┬────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
   ┌────▼────┐         ┌────▼────┐         ┌────▼────┐
   │ 语言模型  │         │ 超大规模  │         │ 系统记录  │
   │ (LM)     │         │ 云商      │         │ (SoR)    │
   └──────────┘         └──────────┘         └──────────┘
```

**控制塔的职责：**
- 协调所有节点间的数据流和工作流
- 提供 zero-copy 数据共享（不移动数据，无风险）
- 实时业务流程修改（通过嵌入平台的 AI 工具）
- 统一管理 IT（信息技术）和 OT（运营技术）

## 当前状态数据

来自 ServiceNow 运营数据（McDermott 引用）：

| 指标 | 数值 |
|---|---|
| 平台上运行的工作流 | 850 亿+ |
| 平台交易量 | 7 万亿+ |
| 客服案例由 agent 处理比例 | **90%** |
| 大客户上线时间 | < 30 天 |

## 对就业的影响预测

### McDermott 的 5 年展望

| 变化 | 说明 |
|---|---|
| 净新增人数 | 大幅减少（agent 取代支持职能） |
| 人力资源投向 | 创新工程、关系管理、信任建设 |
| Agent 数量预测 | **22 亿** agent 进入劳动力市场 |
| Agent vs 人 | Agent 将比人多 |

### 与其他 Builder 观点的呼应

- **Amjad Masad**: "2025+ every company is a cybersecurity company" → agent 安全成为新基础需求
- **Nan Yu**: 采用最佳时机是"落后一两步" → 企业正在从实验阶段进入主流采用

## 关键区分

| 维度 | 传统企业 | Agent 化企业 |
|---|---|---|
| 支持职能 | 大量人力 | Agent 自动处理 |
| 决策模式 | 层级审批 | Agent 预处理 + 人工关键决策 |
| 流程修改 | 多月项目 | <30 天（AI 辅助） |
| 客服 | 人工为主 | 90%+ Agent 处理 |
| 增长方式 | 加人头 | 加 agent + 精英人才 |

## 来源

> [[wiki/sources/summary-ai-builders-digest-2026-04-27]] — No Priors: ServiceNow CEO Bill McDermott (2026-04-17)
