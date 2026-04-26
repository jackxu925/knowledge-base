# Agent Skill System

**标签：** #Agent #Skill #Workflow #Product-Management #Anthropic

---

## 定义

Agent Skill System 是将领域工作流、判断框架、数据来源和后续动作组织成一个稳定协议的系统。Skill 不是简单的 prompt，而是包含输入约束、输出结构、方法论护栏和工具连接的完整执行单元。

## 核心特征

### 1. 输入约束明确
- 明确说明使用时机
- 明确所需上下文
- 明确无上下文时的 fallback 策略

### 2. 输出结构稳定
- 定义产出的组织形式
- 说明下一步可执行的动作
- 便于 skill 之间串联

### 3. 方法论作为护栏
- 嵌入领域框架（MoSCoW、RICE、ICE、JTBD 等）
- 为模型提供判断边界
- 降低"泛化失控"概率

### 4. 双模式设计
- **有 connector**：自动调用工具拉取上下文
- **无 connector**：支持用户手动提供材料
- 优先保障任务可完成性

## Anthropic PM Skills 示例

| Skill | 作用 |
|-------|------|
| synthesize-research | 研究综合 |
| metrics-review | 指标复盘 |
| competitive-brief | 竞品简报 |
| product-brainstorming | 产品共创 |
| write-spec | 需求规格撰写 |
| roadmap-update | 路线图更新 |
| sprint-planning | 迭代规划 |
| stakeholder-update | 干系人同步 |

## 设计原则

1. **工作流完整**：覆盖从发现问题到推动落地的完整链路
2. **可复用**：同一 skill 可在不同场景重复使用
3. **可组合**：多个 skill 可串联成更复杂的工作流
4. **工具解耦**：通过 [[Capability-Oriented Abstraction]] 实现

## 高质量 Skill 的核心

> 把领域工作流、判断框架、数据来源和后续动作组织成一个稳定协议。

## 相关概念

- [[Capability-Oriented Abstraction]] — 工具解耦的架构思想
- [[MCP]] — Model Context Protocol，连接外部工具的协议
- [[Product Management Frameworks]] — PM 方法论集合
