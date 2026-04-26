# Programmatic Tool Calling

**标签：** #MCP #Optimization #Token-Efficiency #Code-Execution #Agent

---

## 定义

Programmatic Tool Calling（程序化工具调用）是 MCP Client 端的优化策略：不在自然语言层面串联工具调用，而是让 Agent 写一段代码在沙箱里编排所有工具调用，只把最终结果返回到上下文。

## 解决的问题

**传统方式的痛点：**
- Agent 调一次工具 → 结果回 context → 推理 → 再调一次 → 循环
- 每次推理都需要一个完整的 inference pass
- 多步工作流中，中间结果全部进入 context，迅速膨胀

## 工作原理

```
传统方式：
Agent → 调用工具 A → 结果 A 进 context → 推理 → 调用工具 B → 结果 B 进 context → ...

Programmatic 方式：
Agent → 写 Python 代码 → 在沙箱里执行（循环、过滤、聚合）→ 只返回最终结果到 context
```

## 实测效果

| 指标 | 结果 |
|------|------|
| Token 消耗 | 减少约 37% |
| 适用场景 | 复杂多步工作流 |
| 典型案例 | Claude for Excel（处理数千行表格数据）|

## 与 Tool Search 的关系

| 优化策略 | 解决什么问题 | 优化对象 |
|----------|-------------|----------|
| **Tool Search** | 工具定义过多 | 进入 context 的工具描述 |
| **Programmatic Calling** | 工具结果过多 | 进入 context 的工具返回 |

**两者叠加效果：**
- Context 更精简
- 往返次数更少
- 响应更快
- 成本更低

## 代码编排模式

这是 Programmatic Calling 在 MCP Server 端的对应实现：

**Cloudflare 案例：**
- 暴露 2 个工具：`search` + `execute`
- Agent 写脚本 → server 在沙箱执行 → 只返回结果
- 2 个工具覆盖 2500 个端点，~1K tokens

**设计哲学：**
> 与其用工具名称集合约束 agent 的动作空间，不如给 agent 一个沙箱，让代码去描述任意可能的操作序列。

## 与 CLI 的关系

Programmatic Calling 的思路与 CLI + Skills 一脉相承：
- **CLI 模式：** Skill 告诉 Agent "怎么干"，CLI 提供 "用什么干"，Agent 写代码调用
- **MCP 模式：** 同样的代码编排思想，但通过 MCP 协议运行在云端

**Anthropic 的观点：** 好的 MCP Server 应该像 CLI 一样设计。

## 相关概念

- [[MCP]] — Programmatic Calling 是 MCP Client 的优化策略
- [[Tool Search]] — 互补的 client 端优化
- [[Cloudflare MCP Server]] — 代码编排模式的参考实现
- [[Agent Skill System]] — 上层 skill 编排架构
