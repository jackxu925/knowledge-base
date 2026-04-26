# Anthropic PM Skills 全景解析

**类型：** 技术博客 / 产品管理方法论
**来源：** 微信公众号「AIML实验室 / 进击的肖恩」
**链接：** https://mp.weixin.qq.com/s/VQ88jCdpbNvkBeXY_FEO0g
**日期：** 2026-04-16
**标签：** #Agent-Skills #Product-Management #Anthropic #MCP #Connector

---

## 一句话总结

Anthropic 官方 knowledge-work-plugins 中的 PM skills 是一套将产品经理工作流结构化、可复用、可组合的 skill 系统，通过 connector 抽象实现工具解耦，覆盖从研究到沟通的完整链路。

## 核心观点

1. **Skill 的核心价值**：把工作流、方法论和工具连接方式拧成同一个稳定协议，而非绑定具体 SaaS 产品
2. **Connector 抽象**：采用 capability-oriented abstraction，声明能力类别而非具体工具品牌
3. **双模式设计**：有 connector 时自动拉取上下文，无 connector 时支持手动输入，保障任务可完成性
4. **方法论作为护栏**：MoSCoW、RICE、ICE、JTBD、HMW 等框架为模型提供判断边界

## 8 个 Skills 工作流

| 阶段 | Skills | 作用 |
|------|--------|------|
| 证据输入 | synthesize-research, metrics-review, competitive-brief | 整理用户信号、数据变化、竞争环境 |
| 思考扩展 | product-brainstorming | 拉开问题空间、方案空间、关键假设 |
| 结构化定义 | write-spec | 收束成目标、非目标、需求分层、指标 |
| 资源规划 | roadmap-update, sprint-planning | 优先级、依赖、时间窗口、迭代范围 |
| 验证沟通 | metrics-review, stakeholder-update | 结果判断、状态同步 |

## 典型使用链路

```
synthesize-research / metrics-review / competitive-brief
    ↓
product-brainstorming
    ↓
write-spec
    ↓
roadmap-update → sprint-planning
    ↓
metrics-review → stakeholder-update
```

## 为什么这套设计成立

1. **输入约束明确**：每个 skill 都说明使用时机、所需上下文、无上下文时的 fallback
2. **输出结构稳定**：定义产出组织形式和后续动作，便于串联
3. **方法论护栏**：PM 框架为模型提供判断边界，降低泛化失控概率

## 相关概念

- [[Capability-Oriented Abstraction]] — connector 的架构抽象思想
- [[MCP]] — Model Context Protocol，skill 与外部工具的实际连接方式
- [[Product Management Frameworks]] — MoSCoW, RICE, ICE, JTBD 等

## 后续拆解计划

本系列后续将依次拆解：
1. `synthesize-research`（研究综合）
2. `metrics-review`（指标复盘）
3. `competitive-brief`（竞品简报）
4. `product-brainstorming`（产品共创）
5. `write-spec`（需求规格撰写）
6. `roadmap-update`（路线图更新）
7. `sprint-planning`（迭代规划）
8. `stakeholder-update`（干系人同步）
