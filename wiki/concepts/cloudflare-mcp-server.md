# Cloudflare MCP Server

**标签：** #MCP #Cloudflare #Code-Orchestration #Reference-Implementation

---

## 定义

Cloudflare MCP Server 是 MCP 代码编排模式的参考实现。它用 2 个工具覆盖约 2500 个 API 端点，将灵活性交给 Agent 的代码执行能力，而非用工具列表穷举所有可能。

## 核心设计

| 设计选择 | 传统方式 | Cloudflare 方式 |
|----------|----------|-----------------|
| 工具数量 | 2500+ 个（每个端点一个） | 2 个 |
| 工具描述大小 | 巨大 | ~1K tokens |
| 灵活性 | 受限于预定义工具 | Agent 写代码描述任意操作 |

## 两个工具

### 1. `search`
- Agent 搜索需要的 API
- 找到目标端点和参数

### 2. `execute`
- Agent 写一段简短脚本
- 通过 execute 在服务端沙箱里运行
- 只返回最终结果

## 工作流程

```
Agent 描述需求 → search 找到 API → 写脚本 → execute 在沙箱执行 → 返回结果
```

## 为什么这是最佳实践

### 1. 解决 Schema 膨胀
- 2500 个端点 × 每个工具定义 = 天文数字的 token
- 2 个工具 = ~1K tokens，可忽略不计

### 2. 保持灵活性
- 不限制 Agent 能做什么
- Agent 用代码描述任意操作序列
- 新 API 无需更新工具定义

### 3. 与 CLI 哲学一致
- CLI 的思路：命令 + 参数 + 管道组合
- Cloudflare MCP：search + execute + 代码编排
- Anthropic 评价："好的 MCP Server 应该像 CLI 一样设计"

## 对比

| 维度 | API 镜像模式 | 意图分组模式 | 代码编排模式 |
|------|-------------|-------------|-------------|
| 工具数量 | 多（按端点） | 中（按意图） | 极少（通用） |
| Token 开销 | 极高 | 中等 | 极低 |
| 灵活性 | 低 | 中 | 高 |
| 适用场景 | 小 API 面 | 中等 API 面 | 大 API 面 |
| 示例 | 小型服务 | GitHub MCP | Cloudflare MCP |

## 启示

1. **对于大 API 面平台**（AWS、K8s、Cloudflare）：代码编排是最佳方案
2. **对于中等 API 面平台**（GitHub、Slack）：意图分组更合适
3. **对于小 API 面平台**：直接镜像端点也可以接受

## 相关概念

- [[MCP]] — Model Context Protocol
- [[Programmatic Tool Calling]] — Client 端的代码编排优化
- [[Tool Search]] — 减少工具定义 token 的 client 优化
- [[Capability-Oriented Abstraction]] — 背后的架构思想
