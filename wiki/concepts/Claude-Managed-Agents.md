---

type: concept
title: "Claude Managed Agents"
aliases: ["Managed Agents", "Anthropic Agents"]
defined_by: [[Anthropic]]
first_seen: "2026-05-06"
sources: [[AI-Builders-Digest-2026-05-24]]
status: active
confidence: high
updated: 2026-05-24
---


# Claude Managed Agents

Anthropic推出的托管 Agent 框架，提供企业级 AI Agent 能力。

## 2026年5月重大更新

### Dreaming (梦境)

- **功能**:  Scheduled process 回顾 agent 会话和记忆存储，提取模式，使 agent 能够自我改进
- **工作方式**: 可以自动更新记忆，或让用户审核变更后再落地
- **价值**: 发现单个 agent 看不到的模式，包括重复错误、工作流收敛、团队偏好
- **用例**: 长时运行任务和多 agent 编排尤其有用

### Outcomes (结果评估)

- **功能**: 编写成功标准 rubric，agent 朝着目标努力
- **评估器**: 独立的 grader 在自己的上下文中评估输出，不受 agent 推理影响
- **迭代**: 当输出不正确时，grader 指出需要更改的地方，agent 再次尝试

### 多 Agent 编排 (Multiagent Orchestration)

- **功能**: 领导 agent 将工作分成碎片，每个专家 agent 有自己的模型、prompt 和工具
- **工作方式**: 专家在共享文件系统上并行工作，为领导 agent 的整体上下文做出贡献
- **事件持久性**: 事件是持久的，每个 agent 都记住自己做了什么

## 性能提升

- 任务成功率提升高达 **10 分**
- docx 文件生成质量提升 **+8.4%**
- pptx 文件生成质量提升 **+10.1%**

## 实际案例

### Harvey (法律科技)

- 使用 Managed Agents 处理复杂法律工作如长形式起草和文档创建
- dreaming 让 agent 记住会话之间学到的内容（文件类型变通方法、工具特定模式）
- 完成率提升约 **6 倍**

### Netflix 平台团队

- 构建分析 agent 处理来自不同来源的数百个构建的日志
- 多 agent 编排让 agent 并行分析批次，只呈现值得采取行动的模式

### Spiral by Every

- 使用多 agent 编排和 outcomes 驱动写作 agent
- 领导 agent 运行在 Haiku 上，处理请求然后委托给运行在 Opus 上的 subagents
- 使用 outcomes 强制执行质量，每次起草根据评分标准评分

### Wisedocs

- 文档质量检查 agent，使用 outcomes 根据内部指南对每次审查进行评分
- 审查速度提升 **50%**，同时保持与团队标准的一致性

## 相关概念

- [[Agent-Architecture]] — Agent 架构
- [[Claude-Code]] — Claude Code
- [[AI-Coding]] — AI 编程

## 来源

- [[AI-Builders-Digest-2026-05-24]]
- Claude Blog: "New in Claude Managed Agents" (2026-05-06)