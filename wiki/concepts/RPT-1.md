---
type: concept
title: RPT-1
aliases: [Relational Pretrained Transformers, 关系预训练Transformer]
defined_by: [[SAP]]
first_seen: 2026-04-26
sources:
  - [[summary-ai-builders-digest-2026-04-26]]
related:
  - [[AI Coding]]
  - [[Managed Agents]]
  - [[Generative UI]]
status: emerging
---

# RPT-1（Relational Pretrained Transformers）

SAP 发布的专门针对**表格/关系数据**预测的 Transformer 模型。

## 背景

LLM 在非结构化数据（文本、图像）上表现优异，但在企业核心需求——**结构化数据预测**上存在根本性局限：
- 需求预测（Demand Forecasting）
- 现金流预测
- 客户付款延迟分类/回归
- 时间序列分析

传统方案（XGBoost、AutoML）需要大量数据科学家，不可扩展。

## 核心创新

将 LLM 对非结构化世界的革命性影响，**复用到结构化/表格数据**上：
- 基于 Transformer 架构但设计不同
- 只需少量上下文 + 小量数据即可实现高精度预测
- 覆盖分类、回归、时间序列任务

## 应用场景

| 场景 | 输入 | 输出 |
|------|------|------|
| 需求预测 | 季节性因素 + 历史销售 | 各产品线未来需求 |
| 付款预测 | DSO + 客户分类 | 延迟天数（回归） |
| 供应链 | 大宗商品价格 | 重规划建议 |

## 意义

RPT-1 代表了 **"LLM 不是 AI 的全部"** 这一重要观点。在企业环境中，表格数据的预测价值远超文本生成，而 LLM 天然不适合这类任务。

来源：[[summary-ai-builders-digest-2026-04-26]] — SAP CTO Philipp Herzig on No Priors Podcast
