---
type: concept
title: "PM Work OS（产品经理工作操作系统）"
created: 2026-05-20
updated: 2026-05-20
aliases:
  - PM Claude OS
  - PM 工作系统
  - 产品经理工作操作系统
defined_by: "Pawel（PM skills marketplace）"
first_seen: 2026-05-20
sources:
  - [[summary-latercast-pm-claude-work-system-2026-05-20]]
related:
  - [[Founder-OS]]
  - [[Agent-Skill-System]]
  - [[Claude-Code]]
  - [[DRRI]]
  - [[Closed-Loop]]
status: emerging
confidence: high
---

# PM Work OS（产品经理工作操作系统）

## 定义

由 Pawel 提出的完整 PM + Claude 工作框架：将产品经理从**反应式任务执行者**转变为**工作流调度者（Dispatcher）**，以 Skills 积累 workflow、知识三分法驱动系统自我迭代为核心。

## 核心组件

### 1. 工具矩阵

| 工具 | 定位 | 典型场景 |
|------|------|---------|
| **Claude Cowork** | 文件与流程处理 | 发票整理、Gmail/Slack 草稿、文档协作 |
| **Claude Code** | 代码库与工程任务 | debug、release notes、代码审查、subagents |
| **Claude Dispatch** | 移动端多任务调度 | 购物途中派发任务、并行后台 agents |

> "已经没有什么好理由，只通过普通网页聊天框和 Claude 对话了。"

### 2. Skills 机制

- **Progressive Disclosure**：Cowork 先读 skill 名称/描述判断匹配，再加载详细步骤
- **可扩展**：可维护几十甚至上百个 skill，不会撑爆上下文
- **迭代路径**：基线 skill → 真实反馈迭代 5~6 轮 → Claude 从第一性原理重写

> "Skills 是最高 ROI 的投资。"

### 3. 知识三分法（自我改进核心）

| 类型 | 定义 | 处理方式 |
|------|------|---------|
| **Rules（规则）** | 已确认、默认执行 | 直接应用 |
| **Hypotheses（假设）** | 带证据、继续观察 | 积累验证 |
| **Rejected Patterns（否定模式）** | 已被否定 | 避免重试 |

**三行自我改进 prompt**：
1. 开始前 review rules
2. 执行时应用 confirmed rules
3. 收到反馈后更新知识

### 4. CLAUDE.md 路由原则

- **不堆知识**：不塞满领域知识
- **只做路由**：指向项目结构、规则、假设、历史反馈

> "CLAUDE.md 应该负责路由，不是堆知识。"

## 能力跃升路径（PM 建议）

```
初级：普通聊天框（一次性 prompt）
  ↓
中级：Cowork（文件整理、知识库、MCP connector）
  ↓
高级：Claude Code（代码库、subagents）+ Dispatch（移动调度）
  ↓
进阶：Skills 自迭代 + 知识三分法 + 生产级硬规则
```

## 生产环境警告

> "在生产环境里，凡是不需要自主的部分，就不该交给自主 agent。"

**Agent 三种形态**：
- 代码主导：大部分由代码控制，中间一次 LLM 调用
- 混合模式：代码 + agent 混合
- 完全自主：全由 agent 决策（仅适用于低风险个人任务）

## 与 Founder OS 对比

| 维度 | Founder OS | PM Work OS |
|------|-----------|-----------|
| 目标用户 | 创始人 | 产品经理 |
| 核心转变 | 个人贡献者→Orchestrator | 任务执行者→Dispatcher |
| 产品矩阵 | Claude Chat/Cowork/Code | Cowork/Code/Dispatch |
| 知识管理 | 四阶段框架 | 三分法自迭代 |

## 相关概念

- [[Founder-OS]] — 创始人视角的同类框架
- [[Agent-Skill-System]] — Skills 机制详解
- [[Claude-Dispatch]] — 移动端任务调度组件
- [[CLAUDE-md路由]] — CLAUDE.md 的正确使用方式
