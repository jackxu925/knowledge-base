# 产品经理如何把 Claude 变成自己的工作系统丨Aakash

- **来源**: 晚点再听 LaterCast（公众号）
- **原视频**: https://www.youtube.com/watch?v=bITUsUsrxjM&t=1259s（Complete Course: Claude for PMs, Aakash Gupta）
- **微信链接**: https://mp.weixin.qq.com/s/RfkVvnc1_kB4lhvXWXjiGg
- **摄取日期**: 2026-05-20
- **主讲人**: Pawel（欧洲 AI PM 作者，LinkedIn 20万+，Newsletter 10万+，PM skills marketplace GitHub 1万star）

---

## 核心金句

> "最大的错误，是每次从零开始提示。"
>
> "CLAUDE.md 应该负责路由，不是堆知识。"
>
> "PM 要会调度多个 agents。"

---

## 一、Anthropic 的速度，来自重写流程

Aakash 抛出数字：Anthropic 在 **52 天里发布了 74 次**。

Pawel 的核心观察：很多公司正在围绕 AI 能做到的事，**重新设计流程**，而非只用 AI 替换原来的步骤。

- 产品经理、产品营销、设计师、工程师的边界正在靠近
- 原型、测试、release notes、基于设计系统生成界面，开始被自动化
- 过去 PM 把需求交给设计和工程，今天更常见的动作是**自己先用 Claude 做出初版材料、原型或分析**，再带着更具体的证据进入协作

Pawel 对 PM 的判断：产品经理不能只会访谈用户、往 backlog 里写条目，需要：
- 理解技术，熟悉 terminal 等工程师工具
- 理解策略、收入、业务目标和产品战略的连接

Aakash 将未来 PM 称为 **super PM 或 super individual contributor**：带着 PM 的重心，同时懂营销、战略、技术、产品和客户沟通。

---

## 二、聊天框已经装不下 PM 的工作

Pawel 几乎不用普通 chat，原因：

- PM 开始任务时，往往不知道后面会需要什么
- 普通聊天框会让上下文断在一个窗口里
- 无法在手机上接着跑
- 无法将讨论内容生成 HTML 再导出成 infographic 放进邮件
- 中途涉及代码时无法处理

> "已经没有什么好理由，只通过普通网页聊天框和 Claude 对话了。"

Pawel 更愿意从 **Cowork、Dispatch 或 Claude Code** 开始。

**Aakash 的 AI 产品案例**：他的 job search OS 有 **16 个 agents**，用户反馈出现 hallucination 或选错工具。后来发现问题不在提示词，而在没有逐步观察 agent 做了什么。接入 tracing 后：
- 能看到每次 tool call、每个决策
- 让 Claude Code 反过来建议 eval 指标
- 一个简历反馈 agent 曾把招聘信息里的 Python 误读成 React
- eval 跑出来同类错误约 **12%**，修完后降到 **2% 以下**

---

## 三、Cowork 做的是文件和流程

**演示案例**：Pawel 拿一个桌面文件夹（两个月收集来的发票，含 PDF、图片、重复文件）做演示：

1. 让 Cowork 分析发票
2. 按月份创建 January、February、March、April 文件夹
3. 识别重复项
4. 把文件移动进去

Claude 执行步骤：提取发票日期 → 识别重复 → 创建月份目录 → 移动文件 → 验证。几分钟后文件整理完毕，连图片里的**波兰语燃油发票**也读出来了。

**Gmail connector 功能**：
- 可以看未回复邮件，草拟回复
- 默认不会自动发送，由人确认后发出

**Slack 功能**：可以让 Claude 起草答复，再由人点击发送，省掉查资料时间，保留人类确认。

Pawel 把 **MCP 叫作 agent 的 USB**：Google Drive、Gmail、Slack、本地服务都可以通过 connector 接进来。

---

## 四、PM 迟早要学 Claude Code

Aakash 替非技术 PM 提问：Code 看起来吓人，能不能跳过？

**Pawel 的答案：不能。**

> "作为一个和工程师一起工作的产品经理，你终究必须和代码打交道。"

**Cowork vs Claude Code 对比**：

| 维度 | Cowork | Claude Code |
|------|--------|-------------|
| 适用场景 | 个人生产力、文件整理、知识库 | 代码库、工程任务 |
| 功能特点 | 友好的文件体验、动态分派 | explorer view、hooks、subagents、本地命令 |
| 角色结构 | 动态分派，无固定角色 | 可定义固定 subagents（researcher、tester、release notes writer） |

**建议路径**：先从 Cowork 学会和 agent 合作（组织知识、定义流程、给反馈），等系统长到几十个文件，或涉及前端、数据库、debug、release notes、代码审查，再进入 Code。

两者可在同一个 repo 里同时使用，读的是同一套 **CLAUDE.md** 和项目文件。

---

## 五、Skills 是最高 ROI 的投资

**Skills 的工作机制**：
- Cowork 会根据任务动态加载对应 skill
- 先看 skill 的名字和描述，判断是否匹配当前任务
- 再读取详细步骤（Anthropic 称之为 **progressive disclosure**）
- 可以有几十个、上百个 skills，但 Claude 不会一开始把所有说明塞进上下文

> "Skills 会根据当前任务被激活；Claude 只有在描述匹配时，才读取详细说明。"

**Pawel 的 PM skills marketplace** 围绕此思路构建，建议：
1. 先用 marketplace 里的基线 skill
2. 再用真实反馈迭代 5~6 轮
3. 让 Claude 根据错误从第一性原理重写流程

**目标**：每次执行后，系统把反馈写回规则里，下一轮自动变好（而非每次复制粘贴 prompt）。

**数据佐证**：PM skills repo **72 小时拿到 1300 个 star**，后来达到 **1 万 star**。

---

## 六、知识库要能自我改进

**最大的错误**：每次都从零开始 prompt，没有让系统从错误中学习。

**知识分三类**：

| 类型 | 说明 |
|------|------|
| **Rules（规则）** | 已经确认、默认执行的内容 |
| **Hypotheses（假设）** | 带证据、需要继续观察的内容 |
| **Rejected Patterns（否定模式）** | 被否定过、避免下次再试的内容 |

**三行自我改进提示词**：
1. 开始前先 review rules
2. 执行时应用 confirmed rules
3. 收到反馈后更新知识

**CLAUDE.md 的正确角色**：不该塞满全部领域知识，而应**负责路由**，告诉 agent 去哪里读项目结构、规则、假设和历史反馈。

> "PM 的复利不在 prompt 收藏夹里，而在一套会吸收反馈的工作系统里。"

---

## 七、Dispatch 把工作搬到手机上

**Dispatch 的定位**：像一个 walkie-talkie，一个聊天入口，可以启动多个后台任务。

**使用场景示例**：
- 让一个任务做 Anthropic 风格 infographic
- 让另一个任务检查最近两小时邮件数量
- 让第三个任务分析 Aakash 的帖子
- 任务完成后分别回报状态

Pawel 会在**购物、陪孩子**的时候派发任务，十分钟后看结果，再给下一轮文字反馈。

**复杂工作**切到 **code web sessions**（类似云端 Visual Studio Code），可连接 GitHub 里的项目，即使本地电脑不在线也能继续。

> "你在散步、开会、参加活动时，agents 也能为你跑着。"

**Vercel 的 Agent Browser**：
- Chrome MCP 会频繁截图，复杂任务可能烧掉大量 token
- Agent Browser 用 headless 浏览器把页面结构给 agent
- 适合 LinkedIn、老 CRM、SAP 这类没有顺手 API 的系统

---

## 八、生产自动化还要硬规则

**个人自动化和生产自动化要分开。**

**必须有硬规则的生产场景**：

> "在生产环境里，凡是不需要自主的部分，就不该交给自主 agent。"

硬边界举例：
- Anthropic API 失败，要重试三次
- 发邮件前必须验证客户邮箱存在
- 客户不能访问另一个客户的数据
- 1GB 文件不能被随便复制
- 某些数据 agent 甚至不该看

**Agent 的三种形态**：

| 形态 | 说明 |
|------|------|
| 代码主导 | 大部分流程由代码控制，中间只有一次 LLM 调用 |
| 混合模式 | 代码和 agent 混合 |
| 完全自主 | 完全由 agent 决策 |

> 越接近生产，越要把可确定的环节收回到代码里。

---

## 核心行动路径

1. 选一个高频任务，写清规则、输入、输出、反馈记录
2. 让 Claude 下次从已有经验出发
3. 等 Cowork 跑顺，再把项目放进 GitHub
4. 用 Claude Code 和 Dispatch 接上真实工作
