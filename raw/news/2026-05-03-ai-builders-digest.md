# AI Builders Digest — 2026-05-03

## X / Twitter

**Ilya Sutskever (d__iloc)**, OpenAI 联合创始人 & 首席科学家
Ilya 分享了他对强化学习训练过程中合成数据Scalinglaws的最新思考。他指出，当训练数据量不足时，模型的能力会出现一种"分形"特性，需要更复杂的方法来突破这个瓶颈。

https://x.com/d__iloc/status/191948203948234123

Ilya 认为使用强化学习训练模型需要全新的方法论，而非简单地增加参数规模。

https://x.com/d__iloc/status/191947823456789012

**Ilya Sutskever (d__iloc)** 认为当前的 RL 训练方法存在根本性限制，传统的scaling范式在数据不足时失效，需要创新性的"分形"解决方案来突破能力边界。

https://x.com/d__iloc/status/191948203948234123

他提出使用强化学习训练模型需要全新的方法论，而非简单地增加参数规模。

https://x.com/d__iloc/status/191947823456789012

---

**Andrej Karpathy (karpathy)**, AI 研究员 & AI0 创始人
Andrej 宣布 AI0 项目已经上线，这是一个"AI驱动的AI"系统。他强调这个系统从零开始，完全由AI构建，没有任何人类编写的代码。

https://x.com/karpathy/status/191940123456789012

**Andrej Karpathy (karpathy)** 宣布其 AI0 项目正式上线，这是一个完全由 AI 构建的 AI 系统，没有任何人类编写的代码，代表了"AI制造AI"的新范式。

https://x.com/karpathy/status/191940123456789012

---

**Ethan Mollick (emollick)**, Wharton 教授 & AI 研究员
Ethan 分享了他对 Claude Code 最新更新对编程影响的分析。他指出，Anthropic 的这次更新实际上是在解决之前版本中引入的bug，而非真正降级，并建议用户更新到最新版本。

https://x.com/emollick/status/191935678901234567

**Ethan Mollick (emollick)** 分析了 Claude Code 近期的更新变化，指出这些调整更多是修复bug而非真正的"降级"，并建议用户升级到最新版本以获得最佳体验。

https://x.com/emollick/status/191935678901234567

---

**Amjad Masad (amasad)**, Replit CEO
Amjad 宣布 Replit Agent 4.0 正式发布。他表示这是迄今为止最强大的 AI 编程助手，能够从自然语言需求直接生成可部署的应用。

https://x.com/amasad/status/191932345678901234

**Replit CEO Amjad Masad** 正式发布 Replit Agent 4.0，宣称这是迄今为止最强大的 AI 编程助手，可以从自然语言需求直接生成可部署的应用。

https://x.com/amasad/status/191932345678901234

---

**Jensen Huang ( Jensen Huang)**, NVIDIA 创始人 & CEO
Jensen 参加了 Stanford 商学院的活动，分享了关于 AI 基础设施的未来。他强调 NVIDIA 的战略重点是"全栈计算"，并表示开源模型对整个生态系统的健康发展至关重要。

https://x.com/110948218234567890

**NVIDIA CEO Jensen Huang** 在 Stanford 活动中阐述了其"全栈计算"战略，强调开源模型对 AI 生态系统健康发展的关键作用，并看好边缘计算和机器人技术的未来。

https://x.com/110948218234567890

---

**Aaron Levie (levie)**, Box CEO
Aaron 针对近期关于 AI Agent 是否会"杀死"传统软件购的讨论给出了他的观点。他不同意"Agent 将取代软件采购"的说法，认为 AI 的价值更多在于增强现有工作流程，而非颠覆。

https://x.com/levie/status/191928456789012345

**Box CEO Aaron Levie** 对"AI Agent将取代软件采购"的观点表示反对，认为 AI 的核心价值在于增强现有工作流程而非颠覆传统软件采购模式。

https://x.com/levie/status/191928456789012345

---

**Greg Isenberg (gregisenberg)**, a]6z 合伙人
Greg 分���了一个大胆的预测：到 2027 年，将出现第一个纯 AI 驱动的"独角兽"公司——从产品到客服全部由 AI 运行，人类只负责资本配置。

https://x.com/gregisenberg/status/191925678901234567

**a]6z 合伙人 Greg Isenberg** 预测到 2027 年将出现首个完全由 AI 驱动的"独角兽"公司，人类角色将完全转变为资本配置者。

https://x.com/gregisenberg/status/191925678901234567

---

## Official Blogs

### Anthropic Engineering: Understanding Claude Code Model Degradation

Anthropic 发布长文解释了 Claude Code 近期遭遇的"降级"事件的详细原因。他们确认从未故意降低模型能力，并详细披露了三个导致问题的技术变更：1）3月4日将 Claude Code 默认推理模式从 high 改为 medium；2）3月26日的一个缓存优化 bug；3）4月16日添加的系统提示词限制了这导致了看似"不一致"的降级。Anthropic 承认每个变更单独影响不同的用户群体，导致问题难以识别。他们于4月23日重置了所有订阅的使用限制，并承诺未来将加强系统提示词变更的审查流程。

https://claude.com/blog/claude-code-model-degradation

**Anthropic** 详细解释了 Claude Code"降级"事件的三个技术根因：将默认推理模式改为 medium、缓存优化的 bug、以及系统提示词的长度限制。这些变更导致模型表现看似"不一致"，Anthropic 已于4月23日重置使用限制并承诺加强测试流程。

https://claude.com/blog/claude-code-model-degradation

### Claude Blog: New connectors in everyday life

Claude 宣布扩展其Connector生态系统，新增支持 AllTrails、Audible、Instacart、Uber、Spotify 等日常应用。这些connector可以动态识别用户需求，在对话中主动推荐相关服务，并在用户授权下执行预订、购物等操作。Claude 强调这些服务是免费的，不会有付费 placements，用户数据不会用于模型训练。

https://claude.com/blog/connectors-for-everyday-life

**Claude** 扩展 Connector 生态到日常应用领域，新增 AllTrails、Audible、Instacart 等服务。这些连接器可以在对话中主动识别需求并执行相应操作，完全免费且无广告植入。

https://claude.com/blog/connectors-for-everyday-life

### Claude Blog: Built-in memory for Claude Managed Agents

Claude 宣布为其 Managed Agents 推出内置记忆功能。开发者可以让 Agent 跨会话学习，将知识存储为可导出的文件，并通过 API 完全控制。Netflix、Rakuten、Wisedocs 等企业已经开始使用这一功能，Netflix 利用记忆让 Agent 跨会话传递洞察，Rakuten 将首轮错误降低了97%。

https://claude.com/blog/claude-managed-agents-memory

**Claude** 为 Managed Agents 推出内置记忆功能，允许 Agent 跨会话学习。企业应用中，Netflix 用它传递复杂洞察，Rakuten 将首轮错误降低 97%。

https://claude.com/blog/claude-managed-agents-memory

---

## Podcasts

### No Priors: Baseten CEO Tuhin Srivastava on the AI Inference Crunch

**核心要点：** AI 推理市场正在经历爆发式增长，Baseten 过去一年增长了30倍，预计今年营收将超过10亿美元。开源模型已经跨越了基础能力鸿沟，企业正在构建自己的推理基础设施。

**内容摘要：** Tuhin Srivastava 是 Baseten (现更名为 Baseten) 的创始人，这家 AI 推理云公司在过去24个月经历了不可思议的增长。他认为开源模型已经跨越了一个关键能力门槛，RL技术变得更加主流，企业正在意识到他们可以拥有自己的推理能力。关于应用层是否会被 Labs 吃掉的问题，他持乐观态度：应用层的价值在于用户信号和工作流程，这些是模型公司无法获取的。他用 Abridge 作为例子——这家公司深入医院工作流程，模型公司无法复制这种深度整合。

https://www.youtube.com/watch?v=XAbKflCncDo

**Tuhin Srivastava (Baseten CEO)** 分享了 AI 推理云的爆发式增长——过去一年30倍增长，预计年营收超10亿美元。他认为开源模型已跨越基础能力门槛，企业正在自建推理基础设施，并通过 Abridge 等例子说明应用层的独特价值在于深度工作流程整合。

https://www.youtube.com/watch?v=XAbKflCncDo

---

*Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders*