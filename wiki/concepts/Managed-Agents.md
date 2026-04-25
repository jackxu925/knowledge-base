---
type: concept
title: Managed Agents
aliases: []
defined_by: [[Anthropic]]
first_seen: 2026-04-25
sources:
  - [[summary-ai-builders-digest-2026-04-25]]
related:
  - [[AI-Native]]
  - [[Software-Factory]]
  - [[Closed-Loop]]
status: emerging
---

# Managed Agents

Anthropic 提出的智能体架构范式，核心思想是将"大脑"与"手"解耦。

## 架构设计

| 组件 | 功能 | 对应 |
|------|------|------|
| **大脑** | Claude + Harness | 推理、规划、决策 |
| **手** | Sandboxes + Tools | 执行、操作、环境交互 |

## 设计原则

1. **解耦**：避免将整个系统变成需要维护的"宠物"
2. **容错**：单个手的故障不影响大脑
3. **扩展**：支持"多大脑、多手"的弹性架构

## 性能收益

- TTFT p50 降低约 60%
- TTFT p95 降低超过 90%

## 意义

Managed Agents 代表了从"单一智能体"向"分布式智能体系统"的架构演进，是 [[AI-Native]] 组织的基础设施层。
