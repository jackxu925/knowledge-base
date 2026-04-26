# Building agents that reach production systems with MCP

**来源：** Anthropic 官方博客 (claude.com/blog)
**链接：** https://claude.com/blog/building-agents-that-reach-production-systems-with-mcp
**日期：** 2026-04-22

---

## 摘要

Anthropic 系统阐述了 agent 连接外部系统的三条路径（直接 API、CLI、MCP），以及为什么生产级 agent 最终都会走向 MCP。文章分享了 200+ MCP Server 的实战经验，提炼出 5 个 server 设计模式和 2 个 client 优化策略，并明确了 MCP 与 Skills 的互补关系。

**关键数据：** MCP SDK 月下载量从年初 1 亿涨至 3 亿，三个月翻三倍。

---

## 01 Agent 连接外部系统的三条路

### 直接 API 调用
- Agent 直接发 HTTP 请求
- 适合一对一简单场景
- **问题：** M 个 agent × N 个服务 = M×N 集成问题，复杂度指数级膨胀

### CLI（命令行）
- Agent 跑 shell 命令
- 本地开发快、轻量、可复用
- **问题：** 无法触达没有暴露容器的平台（移动端、Web、云端），认证依赖本地 credential 文件

### MCP（Model Context Protocol）
- 标准化连接层，远程 server 通吃所有客户端
- 解决 M×N 问题 → 变成 M+N 问题
- **适用：** 云端生产环境、需要标准化认证、跨平台复用

**Anthropic 判断：** 生产 agent 越来越多跑在云上，MCP 是唯一的通用解。

---

## 02 MCP 的采用现状

- **MCP SDK 月下载量：** 3 亿（年初仅 1 亿）
- **支撑产品线：** Claude Cowork、Claude Managed Agents、Claude Code Channels
- **官方目录：** 200+ MCP Server，每天数百万人使用

---

## 03 构建优秀 MCP Server 的 5 个模式

### ① 构建远程 Server
- 本地 server 仅用于开发调试
- 远程 server 才能在 Web、移动端、云托管 agent 里运行

### ② 按意图分组工具
- **不要**按 API 端点映射（工具数量多、颗粒度细）
- **要**按"用户想完成什么"组织工具
- 示例：`create_issue_from_thread` 比 `get_thread + parse_messages + create_issue + link_attachment` 更好

### ③ 大面积 API 暴露代码执行接口
- 适用于 Cloudflare、AWS、K8s 等上千端点的平台
- **Cloudflare 案例：** 2 个工具（search + execute）覆盖 2500 个端点，工具描述仅占 ~1K tokens
- Agent 写小段脚本，server 在沙箱里执行

### ④ 标准化认证（CIMD + Vaults）
- CIMD（客户端 ID 元数据文档）用于客户端注册
- Vaults 托管 OAuth token 并自动刷新

### ⑤ MCP Apps + Elicitation
- MCP Apps：工具返回交互式界面（图表、表单、仪表盘）
- Elicitation：server 暂停执行向用户请求输入（确认操作、OAuth 授权）

---

## 04 MCP Client 优化：两把利器

### Tool Search（工具懒加载）
- **问题：** 58 个工具定义吃掉 ~55K tokens
- **解法：** 按需搜索，只加载匹配的工具
- **效果：** token 使用量减少 85%+，工具选择准确率基本不变

### Programmatic Tool Calling（程序化工具调用）
- **问题：** 多步工作流中每次原始输出都进入 context
- **解法：** 在代码沙箱里处理工具调用，只返回最终结果
- **效果：** token 使用量减少约 37%

---

## 05 MCP 与 Skills 的关系

**不是竞争，是互补。**

| 维度 | MCP | Skills |
|------|-----|--------|
| 提供什么 | 工具连接能力 | 程序性知识（怎么做） |
| 类比 | 手（能操作） | 脑（知道怎么操作） |
| 来源 | 外部系统 API | 领域专家经验 |

**组合模式：**
1. **Plugin 打包：** Skills + MCP Server + Hooks + LSP + Subagent（如 Data Plugin：10 Skills + 8 MCP Server）
2. **Server 直接分发 Skills：** `experimental-ext-skills` 扩展，装 MCP Server 自动获得使用指南

**已有实践：** Canva、Notion、Sentry 已在发布 MCP Server 时附带 Skills。

---

## 06 关键启示

1. **Cloudflare 案例：** 把灵活性交给 agent 的代码执行能力，而非用工具列表穷举
2. **85% token 节省：** "在对的时候让模型看到对的工具"比"塞满所有工具"更优
3. **生态效应：** 每个 MCP 集成都在强化整个生态，减少边界情况和定制维护
4. **MCP 正在成为 Agent 的 TCP/IP**

---

## 社区争议与 Anthropic 的回应

此前社区对 MCP 的三大批评：
- **成本高：** CLI 比 MCP 便宜 10-32 倍
- **上下文膨胀：** 72% 的上下文窗口被 MCP 占掉
- **Schema 臃肿：** 43 个工具定义占 55K tokens

**Anthropic 的回应：**
- Tool Search 解决 schema 臃肿（减 85%）
- Programmatic Calling 解决不可组合（减 37%）
- 代码编排模式解决 token 贵（Cloudflare 2 个工具覆盖 2500 端点）

**结论：** MCP 和 CLI 不是对立的，好的 MCP Server 应该像 CLI 一样设计。

---

## 未来图景

| 场景 | 推荐方案 |
|------|----------|
| 本地开发环境 | CLI + Skills |
| 云端生产环境 | MCP + Skills |
| 简单场景 | 直连 API |

MCP 正在成为云端 Agent 的标准化接入层，Skills 是差异化竞争的关键。
