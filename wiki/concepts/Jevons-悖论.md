---

type: concept
title: Jevons 悖论
aliases: [杰文斯悖论]
defined_by: [[Aaron Levie]]
first_seen: 2026-04-25
sources:
  - [[summary-ai-builders-digest-2026-04-25]]
  - [[summary-ai-builders-digest-2026-04-26]]
  - [[summary-ai-builders-digest-2026-04-27]]
  - [[summary-ai-builders-digest-2026-04-28]]
  - [[summary-ai-builders-digest-2026-04-30]]
related:
  - [[AI-Native]]
  - [[10x-Engineer]]
  - [[Token-Maxing]]
status: stable
updated: 2026-05-03
---


# Jevons 悖论（杰文斯悖论）

经济学概念在 AI 时代的重新诠释：技术效率提升不会减少资源消耗，反而会增加总需求。

## 原始定义

19 世纪经济学家威廉·杰文斯观察到：蒸汽机效率提升后，煤炭总消耗量反而增加。

## AI 时代的版本

Aaron Levie（Box CEO）提出：

> AI 越擅长完成任务，公司就越会雇佣更多支持人员。

### 机制

| 场景 | 旧约束 | 新现实 |
|------|--------|--------|
| 小企业工程 | 负担不起工程师 | 雇佣 5-10x 效率的工程师 |
| 销售团队 |  Outreach 能力有限 | 自动化带来更多线索 → 雇佣更多销售 |

## 反直觉结论

AI 进步 → 更多招聘，而非更少。

这与"AI 将取代人类工作"的流行叙事形成直接矛盾。

## 2026-04-26 更新

Aaron Levie 进一步阐述了 Jevons Paradox 的更多应用场景：
- 营销团队做更高端视频 → 需要雇佣视频编辑
- 小企业终于能负担工程师投资工程
- **趋势随 AI 能力提升而增强**——AI 越好，能承担的任务越多，配套工作越多

SAP CTO Philipp Herzig 也从企业软件角度佐证了类似观点：**AI 不会削减岗位，而是将每个人提升一个层级**（如财务人员从数据收集转向战略分析）。

来源：[[summary-ai-builders-digest-2026-04-26]]

## 2026-04-27 更新

### Aaron Levie — AI 杠杆效应（续）

Levie 进一步扩展 Jevons Paradox 到个人职业层面：

> AI 提供前所未有的杠杆 → 有野心+核心技能的人可以克服历史经验要求
> 新人现在能完成比几年前多得多的工作
> 公司应识别这些"来自未来"的人才并安排到关键位置

### Bill McDermott — 企业级视角

ServiceNow CEO 从企业平台角度补充：
- **企业不会因为 AI 而裁员**，而是将人力投资从支持职能（agent 可做）转向创新和关系建立
- 预测 **22 亿 agent 进入劳动力市场**——agent 比人多，但人类角色升级而非消失
- 与 Jevons Paradox 一致：AI 效率提升 → 人类承担更高价值的工作

来源：[[wiki/sources/summary-ai-builders-digest-2026-04-27]]

## 2026-04-28 更新

### Aaron Levie — Agent 过度劳动论（Jevons Paradox 的微观版）

Levie 提出 AI Agent 时代导致个人**过度工作**的两个结构性因素：

**因素一：杠杆率感知变化**
- AI 大幅提升增量投入的杠杆率
- 使用 AI 工具的人最先感受到这种复利效应
- 感觉类似团队管理者——浪费团队成员时间是最糟糕的事
- 现在 IC（个人贡献者）通过管理 Agent 获得类似的"浪费时间"敏感度
- **优先级管理和任务拆分能力成为关键技能**

**因素二：90%-10% 陷阱**
- AI 让启动新项目变得太容易
- 快速达到 90% 方案，但最后 10% 消耗大部分时间
- 启动更多项目 → 总工时增加
- Levie 原话: "I regularly start a project at 9PM that I think will be quick, and find myself at midnight still completing the work"

**就业创造机制**：
- 这种实验最终推动就业创造——因为团队/公司决定将实验升级为生产流程
- **没有 AI 就不会启动这些实验**

### Gell-Mann Amnesia for AI Job Displacement

Levie 提出一个重要认知偏差框架：**人们用 AI 做自己的工作时能看到所有复杂性**（数据访问、上下文需求、输出审核、业务流程集成），但看别人工作时却认为 AI 会立即取代对方。

> "We all have a much deeper appreciation for the nuances and complexities of the work that we do every day."
> "We tend to dramatically underestimate the work that goes into making the AI work just as effectively in those jobs."

这是对失业理论保持怀疑的理由——理论来自自动化单个任务，而不理解完整工作的全部内容。

来源：[[wiki/sources/summary-ai-builders-digest-2026-04-28]]

## 2026-04-30 更新

### Aaron Levie — 100X 软件爆发论（Jevons Paradox 宏观版）

Levie 在本轮发表其最完整的 Jevons Paradox 论述：

**核心命题：软件岗位不会消失，Agent 将创造 100 倍于现有规模的软件量**

六大驱动因素：
1. **存量优化**: 大量现有应用需要变得更好
2. **上云迁移**: 遗留本地系统必须重新平台化
3. **SMB 首次开发**: 中小企业以前雇不起开发者
4. **安全补丁**: 即将被发现的大量安全问题需要修补
5. **IT 自动化**: 从前无法自动化的工作流即将被自动化
6. **数据连接**: 大部分组织的数据即将被处理和连接

**关键限定**:
- "100X more software" != "everyone rolling their own"
- Agentic coding 适合: 开发者提效、IT 内部构建、领域专家自动化、学习编程者
- Agentic coding 不适合: casually 构建需长期维护的复杂系统
- 升级、维护、安全更新等"税负"是多数知识工作者未准备的

**与 Jevons Paradox 的关系**: 这是对该悖论的终极验证 — AI 效率提升不会减少软件开发需求，而是通过降低准入门槛和开辟新场景，使总需求暴增。

来源：[[wiki/sources/summary-ai-builders-digest-2026-04-30]]

## 与知识库概念的关系

- [[Token-Maxing]]：用 API 成本替代人力成本的逻辑在宏观层面被 Jevons 悖论修正
- [[10x-Engineer]]：个体效率提升带来团队规模扩张
- [[AI-Native]]：组织设计的核心假设需要重新评估
