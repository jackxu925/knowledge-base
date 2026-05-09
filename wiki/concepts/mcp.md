---
type: concept
title: "MCP (Model Context Protocol)"
created: 2026-05-03
updated: 2026-05-03
confidence: medium
---

# MCP (Model Context Protocol)

**标签：** #MCP #Protocol #Agent #Anthropic #Standard

---

## 定义

MCP（Model Context Protocol）是 Anthropic 提出的开放标准协议，用于 AI Agent 与外部系统之间的标准化连接。它提供了一个"公共层"，将 M×N 的集成问题转化为 M+N 的标准化互操作。

## 核心问题：M×N 集成困境

| 方式 | 集成数量 | 问题 |
|------|----------|------|
| 直接 API | M agents × N services | 每对组合都需要独立认证、工具描述、错误处理 |
| MCP | M agents + N services | 各维护一个 MCP server/client，天然互操作 |

## 三条连接路径对比

| 路径 | 优点 | 限制 | 适用场景 |
|------|------|------|----------|
| **直接 API** | 简单直接 | 规模化后复杂度指数级膨胀 | 原型、简单场景 |
| **CLI** | 轻量、可复用工具链 | 无法触达云端/移动端/无容器平台 | 本地开发、沙箱 |
| **MCP** | 标准化、跨平台、远程认证 | 需要维护 server | 云端生产环境 |

## MCP 架构

```
Agent (Client) ←→ MCP Protocol ←→ MCP Server ←→ External System
```

- **Client：** 任何支持 MCP 的 Agent（Claude、ChatGPT、Cursor、VS Code）
- **Server：** 暴露外部系统能力的标准化接口
- **Protocol：** 认证、工具发现、语义描述的标准化

## 采用现状（2026-04）

- **MCP SDK 月下载量：** 3 亿（年初 1 亿，三个月翻三倍）
- **官方目录：** 200+ MCP Server
- **支撑产品：** Claude Cowork、Claude Managed Agents、Claude Code Channels
- **企业采用：** Cloudflare、Notion、Sentry、Canva

## MCP Server 设计模式

### 1. 远程优先
- 本地 server 仅用于开发调试
- 远程 server 才能在 Web、移动端、云托管 agent 运行

### 2. 意图分组
- 按"用户想完成什么"组织工具
- 非 API 端点映射
- 示例：`create_issue_from_thread` > `get_thread + parse_messages + create_issue`

### 3. 代码编排
- 暴露 `search` + `execute` 两个工具
- Agent 写脚本在沙箱执行
- **Cloudflare 案例：** 2 个工具覆盖 2500 端点，~1K tokens

### 4. 标准化认证
- CIMD（客户端 ID 元数据文档）用于客户端注册
- Vaults 托管 OAuth token 并自动刷新

### 5. MCP Apps + Elicitation
- MCP Apps：返回交互式界面（图表、表单、仪表盘）
- Elicitation：server 暂停执行向用户请求输入

## MCP Client 优化

### Tool Search（工具懒加载）
- 按需搜索工具，只加载匹配的定义
- **效果：** token 减少 85%+，准确率不变

### Programmatic Tool Calling（程序化调用）
- 在代码沙箱里处理工具调用
- 只返回最终结果到 context
- **效果：** token 减少 37%

## MCP vs Skills

| | MCP | Skills |
|--|-----|--------|
| 提供 | 工具连接能力 | 程序性知识 |
| 类比 | 手（能操作） | 脑（知道怎么操作） |
| 来源 | 外部系统 API | 领域专家经验 |
| 作用 | 让 Agent 能连上系统 | 让 Agent 知道怎么用系统 |

**组合模式：**
- Plugin 打包：Skills + MCP Server + Hooks + LSP
- Server 分发 Skills：`experimental-ext-skills` 扩展

## 社区争议

| 批评 | 回应 |
|------|------|
| 成本高（CLI 便宜 10-32x） | Tool Search + Programmatic Calling 大幅降本 |
| 上下文膨胀（72% 被占） | Tool Search 减 85% 工具定义 token |
| Schema 臃肿 | 代码编排模式（Cloudflare 2 工具覆盖 2500 端点） |

## 未来定位

> MCP 正在成为 Agent 的 TCP/IP。

| 环境 | 推荐方案 |
|------|----------|
| 本地开发 | CLI + Skills |
| 云端生产 | MCP + Skills |
| 简单场景 | 直连 API |

## 相关概念

- [[Agent Skill System]] — 与 MCP 互补的 skill 编排系统
- [[Capability-Oriented Abstraction]] — MCP 的架构抽象思想
- [[Cloudflare MCP Server]] — 代码编排模式的参考实现
