---
type: raw
url: https://mp.weixin.qq.com/s/q94y3egNYQPEWFWd6Na2xg
author: Capihom Capihom / 晚点再听LaterCast
date: 2026-04-27
title: "YC CEO：如何让 Claude 为你的 AI 工程团队编写代码？"
platform: 微信公众号（晚点再听LaterCast）
original: Y Combinator / Gary Tan
---

# YC CEO：如何让 Claude 为你的 AI 工程团队编写代码？

> 来源：微信公众号「晚点再听LaterCast」| 作者：Capihom Capihom | 日期：2026-04-27
> 原始视频："How to Make Claude Code Your AI Engineering Team" - Y Combinator / Gary Tan
> 视频链接：https://www.youtube.com/watch?v=wkv2ifxPpF8

---

## 元数据

- **来源**: 微信公众号「晚点再听LaterCast」
- **原创作者**: Capihom Capihom
- **日期**: 2026-04-27
- **原文链接**: https://mp.weixin.qq.com/s/q94y3egNYQPEWFWd6Na2xg
- **内容类型**: 播客解读 / 产品观察
- **原始播客**: Y Combinator - Gary Tan
- **原始视频**: https://www.youtube.com/watch?v=wkv2ifxPpF8
- **字数**: 约 3900 字

---

## 核心观点

> "我们正处在一个全新的构建软件时代，agent 时代。"
> "让 agent 做真正工作的方式，和人类作为团队工作的方式一样：角色、流程和评审。"
> "瓶颈不是模型的智能。只要把模型设置对，它们已经足够聪明。"

Gary Tan（YC 总裁兼 CEO）认为，今天的问题不是模型不够聪明，而是我们经常把模型丢进代码库，期待它自己知道该怎么工作。他把 Claude Code 的正确用法从"更强的单个助手"改写成"需要角色、流程和评审的工程团队"。

Gary 的体感：过去两个月，他写的代码比 2013 年一整年还多；而 Posterous 当年花了两年、上千万美元和十人团队才做出来的东西，如今他已经能用 agent 复刻出很大一部分。

---

## 正文

### 别把模型当实习生，要先给它团队结构

Gary 的核心判断：模型会游荡、会补全、会猜测；在真实项目里，这种"看起来很像"的产出最危险。真正稀缺的不是"再多一个提示词"，而是一套能让 agent 明确任务边界、知道何时停下、知道如何自检的生产流程。

**thin harness, fat skills**：外层框架尽量薄，真正的能力沉到可复用的专业技能里。

### Office Hours：先问"谁真的想要这个"

Gary 让 GStack 帮他想一个报税工具。普通 agent 会直接开始做 Gmail 搜索和 PDF 下载；Office Hours 先停下来问：
- 你凭什么知道有人真的要这个？
- TurboTax、H&R Block、Plaid 已经在做，为什么还没解决你的问题？

**价值**：把"我想做一个功能"提前改成"这个痛点有没有足够强的商业楔子"。

> "决定其他一切的问题是：你有什么最强证据证明真的有人想要这个？"

### 好 agent 不是照做，而是帮你改写问题

报税工具被重新塑造成浏览器自动化方案：用户自己登录 Gmail 和银行网站，AI 在可见浏览器里导航、寻找税务文档、下载 PDF，全程不需要把凭证交给云端。

> "它不是那种沿着轨道走的东西，更像是和你的模型的一场对话。"

### 计划不是文档，是降低返工的自动化流程

模型给出三条路径：
1. 小范围 Gmail 搜索
2. 完整的 Gmail + 浏览器自动化 + CPA 市场
3. 从 CPA 端反转 go-to-market

Gary 选了第二条，继续让系统做多步对抗性评审。评审发现缺口：没有失败处理、没有隐私章节、2FA 交接没有方案。

> "我们的设计文档经历了两轮对抗性评审，并自动发现和修复了 16 个问题。"

评分从 6 分提高到 8 分，剩下的问题被明确记录。agent 应该把能修的修掉，把还需要人类判断的部分显性化。

### AI 编程的关键，不是更会写代码，而是更会评审

Gary 写了围绕 Playwright 和 Chromium 的 CLI，让 agent 能截图、点击、填表、下载媒体、跑回归测试，甚至根据真实浏览器问题更新 CSS。

> "一旦 agent 开始做计划、设计和编码，我发现自己坐在那里做 QA。"

**新瓶颈**：当机器承担更多产出，人类最容易被困在验证环节。做 QA 可能是软件开发里最没意思的部分，所以必须自动化。

如果 agent 只会写代码，你得到的是更快的风险；如果它还能在真实浏览器里验证，你才开始接近可交付的软件工厂。

### 设计也可以并行，但人要做选择

**Design Shotgun**：系统一次生成三个设计方向（command center、friendly progress、split view），人负责判断哪一个更贴近用户。

> "如果你不喜欢它，可以输入反馈并重新生成；但这次我们选择 B 继续。"

AI 让草案变多，但品味和取舍仍然要回到用户场景。

### 多 agent 不是更多窗口，而是并行 PR 的工厂

Gary 把 GStack 能达到的状态称作接近 **"level 7 software factory"**。

他经常同时运行 **10 到 15 个 Claude Code 会话**，在不同项目、不同分支、不同功能上并行推进。每个想法、bug report、用户抱怨都可以变成一个独立 worktree。

> "我不再有待办清单了。每一个想法或 bug report，都会变成一个新的 work item。"

**并行的前提**：每条线都有清楚的边界和交付门槛（Office Hours → CEO review → 工程评审 → 对抗性评审 → 最终 review）。

### 最后一层护栏：安全和交付

Gary 对开源 PR 非常谨慎（供应链攻击风险）。GStack 里的 ship tool 是落到 main 之前的最后一步，负责确认 PR 是否真的准备好合并。

> "这是历史上最不可思议的软件构建时刻，构建门槛已经坍塌，剩下的问题是你要做什么。"

**前提**：你得有一套足够严格的流程，把想法、计划、设计、代码、浏览器验证、评审和发布连接起来。

---

## 写在最后

把 agent 当团队管理，而不是当魔法按钮使用。先问证据，再定计划，再做评审和验证。模型已经足够快，接下来真正拉开差距的，是你能不能把它放进一套稳定、可复用、能交付的流程里。
