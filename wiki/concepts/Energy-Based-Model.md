---
type: concept
title: "Energy Based Model (EBM)"
created: 2026-04-28
updated: 2026-04-28
related: [[LLM]], [[AI Coding]], [[Formal Verification]], [[Logical Intelligence]]
aliases:
  - 能量模型
  - EBM
  - Energy-Based Reasoning Model
defined_by: Logical Intelligence (Eve, CEO)
first_seen: 2026-04-28 (AI & I by Every podcast)
sources:
  - raw/news/ai-builders-digest-2026-04-28.md
status: emerging
confidence: high
---

# Energy Based Model (EBM)

## 定义

Energy Based Model（能量基模型）是一种**非自回归、无 Token** 的 AI 架构范式。与 LLM 通过逐 Token 预测生成输出不同，EBM 通过构建**能量景观 (Energy Landscape)** 并使用能量最小化原理来导航和推理。

核心思想来自物理学：正如物理系统通过最小化能量找到稳定态（如球滚到山谷底部），EBM 将数据映射到能量结构中，系统自然收敛到最可能（最低能量）的状态。

## 与 LLM 的根本区别

| 维度 | LLM | EBM |
|------|-----|-----|
| **生成方式** | 自回归，逐 Token 预测 | 非自回归，全局能量最小化 |
| **Token** | 依赖 Token 序列 | 无 Token（Token-free） |
| **可解释性** | 黑盒，训练完成后才能检查 | 可在训练过程中实时检查内部状态 |
| **导航能力** | 隧道视野，一次选一个方向，不能回退 | 鸟瞰视角，可见所有可能路径 |
| **语言依赖性** | 智力依赖于语言空间 | 不依赖语言，可直接处理数据 |
| **稀疏数据处理** | 需要大量训练数据 | 擅长处理稀疏/不完整数据 |
| **约束满足** | 无法被形式化强制遵循规则 | 可以被正式证明遵循约束 |

## 关键技术组件

### 1. Latent Variables（潜变量）

存储关于数据的"规则理解"，而非仅模式匹配。类似人脑中的世界观——知道厨房用来做饭、沙发用来坐。当环境变化时（如换了新沙发），仍能基于已有规则推断如何行动。

### 2. Internal Self-Alignment

EBM 架构天然支持内部验证。模型在处理信息时可自我对齐，无需等待完整输出生成后才能检查。

### 3. Double Verification

- **内部**: EBM 自身架构提供自对齐
- **外部**: 可附加 Lean4 等形式化证明语言作为外部验证器

## 适用场景

- **关键任务系统**: 汽车、飞机控制（毫秒/微秒级决策）
- **形式化验证**: 芯片设计、代码正确性证明
- **数据分析**: 金融、医疗、基因等非语言密集型领域
- **电网/能源分配**: 实时优化和预测
- **隐私敏感的 B2B 场景**: 企业不需要共享数据到中心化大模型

## 行业动态

### 投资锁定问题

Eve 指出 LLM 面临**沉没成本锁定**：
- 数十亿美元投入数据中心
- LLM 公司 ↔ 硬件商 ↔ 云服务商之间的循环交易生态
- 大科技公司确实有内部 EBM 研究（视为积极信号）
- 但激进替代方案获得的资金占比远低于增量式 LLM 改进

### 兼容策略

Logical Intelligence 的定位：**不做 LLM 替代品**，而是做兼容层。
> "We could actually try experiments to reduce the cost for your LLM portfolio companies."

EBM 处理 LLM 不擅长的任务（空间推理、数据分析、形式化验证），同时保留所有现有 LLM 投资。

## 与 Vibe Coding 的关系

Eve 提出 EBM 可能实现从 "vibe coding in one specific language" 到 **coding in natural language with formally verified output** 的跃迁：
- AI 用自然语言编写规格说明
- 形式化验证替代人工代码审查
- AI 以自然语言告知逻辑不兼容的具体位置和修复建议

## 引用来源

> "Intelligence which is language dependent... my thought processes don't really depend on any language. When you're driving a car, how much language do you actually use?" — Eve, Logical Intelligence CEO

> "EBM gonna have the bird view all the time. So if you see there's a hole, you're gonna choose a different route." — Eve, AI & I podcast

> "You have for verification tasks, this notion of self alignment because of the EBM architecture and absence of token makes it cheap." — Eve, AI & I podcast
