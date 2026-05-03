---
type: concept
title: Managed Agents
aliases: []
defined_by: [[Anthropic]]
first_seen: 2026-04-25
sources:
  - [[summary-ai-builders-digest-2026-04-25]]
  - [[summary-ai-builders-digest-2026-04-26]]
  - [[summary-ai-builders-digest-2026-05-03]]
related:
  - [[AI-Native]]
  - [[Software-Factory]]
  - [[Closed-Loop]]
  - [[Post-Prompting World]]
status: active
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

## 2026-04-26 更新

Anthropic 工程博客进一步阐述了设计哲学：
- **Session 不是 Claude 的 context window**：长任务超出上下文窗口时，session 作为持久化的事件日志，通过 `getEvents()` 接口支持灵活的上下文查询
- **安全边界**：凭证永远不进入 sandbox——Git token 在初始化时绑定，MCP OAuth 存于外部 vault
- **多大脑多手**：每个大脑可连接多个执行环境，大脑间还可传递手
- **核心隐喻**：如 OS 虚拟化硬件般虚拟化 Agent 组件，为"尚未构想出的程序"设计系统

来源：[[summary-ai-builders-digest-2026-04-26]]

## 2026-05-03 更新：内置记忆功能

Claude 宣布为 Managed Agents 推出**内置记忆功能**：

- **跨会话学习**：Agent 可以从每个会话中学习
- **可导出文件**：开发者可以导出和管理记忆
- **API 完全控制**：通过 API 完全控制

### 企业应用案例

| 公司 | 应用 | 效果 |
|------|------|------|
| Netflix | 跨会话传递洞察 | 复杂洞察可持续传递 |
| Rakuten | 任务型 Agent 错误减少 | 首轮错误降低 **97%** |
| Wisedocs | 文档验证管道 | 加速 30% |

来源：[[summary-ai-builders-digest-2026-05-03]]
