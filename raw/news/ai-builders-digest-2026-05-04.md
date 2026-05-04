---
title: AI Builders Digest — 2026-05-04
date: 2026-05-04
type: source
source: follow-builders
---

# AI Builders Digest — 2026-05-04

## X / Twitter

**Greg Brockman (OpenAI President & Chairman)**
Greg Brockman discusses the future of AI compute and scaling laws. OpenAI continues to aggressively secure compute resources, as demand for intelligence remains essentially unlimited. The scaling laws continue to hold — there's no wall as more compute is poured into models. OpenAI is also investing heavily in new architectures beyond the transformer.
https://x.com/gdb/status/2050356789014568960

Greg Brockman 认为 AI 的扩展定律仍在持续发挥作用，投入更多计算资源模型能力就会相应提升，不存在所谓的"天花板"。OpenAI 正在积极研究超越 Transformer 的新架构。

---

**Sam Altman (OpenAI CEO)**
i keep thinking i want the models to be cheaper/faster more than i want them to be smarter
but it seems that just being smarter is still the most important thing
https://x.com/sama/status/2050671161915371998

Sam Altman 思考的问题是：我们应该更看重模型更便宜/更快，还是更智能？最终结果表明，更智能仍然是最重要的。

---

**Dan Shipper (Every CEO)**
Agent running continuously on the left, application that you + the agent use on the right.
https://x.com/danshipper/status/2050583747041640608

Dan Shipper 预测未来 10 年的工作模式：左侧是持续运行的 agent，右侧是你和 agent 共同使用的应用程序。

---

**Aditya Agarwal (SouthPk Commons GP)**
If you get out of the console and terminal, you will start to see that there is a lot of hard tech being built in America. It is deeply deeply inspiring and exciting.
https://x.com/adityaag/status/2050660894234059050

Aditya Agarwal 认为走出console和terminal，会看到美国有很多硬科技正在被构建，这非常令人鼓舞和兴奋。

---

**Aravind Rajeswaran (Google DeepMind)**
The best way to predict how a model will do on a test is to see how it does on a similar test. There's no free lunch — generalist post-training still matters a lot for specific tasks.
https://x.com/aravind_rajesh/status/2049987645996490752

Aravind Rajeswaran 关于泛化与专业化：预测模型在测试上的表现最好方式是看它在类似测试上的表现。没有免费的午餐——通用post-training对特定任务仍然很重要。

---

**Yi Ma (Microsoft Research)**
On the relationship between training and emergent abilities: There's no magic — emergent abilities arise from the interaction between the model's objective (loss function) and the training distribution. As you increase scale, these interactions become more complex and lead to unexpected capabilities.
https://x.com/yima org/status/2050427678167973888

Yi Ma 关于训练与涌现能力的关系：没有魔法——涌现能力来自模型目标（损失函数）与训练分布之间的交互。随着规模增加，这些交互变得更加复杂，产生意外的能力。

---

**Bob van Heuveln (Thoughtful AI)**
The key to building effective AI agents is to separate the "brain" (LLM + harness) from the "hands" (execution environment/tools). This decoupling allows each component to fail and be replaced independently.
https://x.com/bobvanHeuveln/status/2050519628547952640

Bob van Heuveln 的关键洞见：构建有效的 AI agents 需要将"大脑"（LLM + harness）与"手"（执行环境/工具）分离，这种解耦允许每个组件独立失败和替换。

---

**Justine Moore (a]6z)**
We're seeing a shift from API-first to agent-first architecture. The application layer is being rebuilt around continuous agent workflows rather than stateless API calls.
https://x.com/acrmn/status/2050245287874564096

Justine Moore 观察到从 API-first 到 agent-first 的架构转变。应用层正在围绕持续运行的 agent 工作流重建，而非无状态的 API 调用。

---

**Matt Garman (AWS CEO)**
GPU compute availability in 2026 rounds to zero. Everyone wants more, but supply can't keep up.
https://x.com/mattgarman/status/2050384729187565568

Matt Garman 表示 2026 年 GPU 计算可用性接近于零。每个人都想要更多，但供应跟不上。

---

**Anthropic Engineering**
Scaling Managed Agents: Decoupling the brain from the hands. How Anthropic built Managed Agents by virtualizing the components of an agent — session, harness, and sandbox — each as interfaces that make few assumptions about the others.
https://www.anthropic.com/engineering/managed-agents

Anthropic Engineering 分享了他们如何通过将 agent 的组件虚拟化来构建 Managed Agents——session、harness 和 sandbox 各自作为接口，减少相互之间的假设。

---

## Podcasts

**Training Data: OpenAI's Greg Brockman — Why Human Attention Is the New Bottleneck**

The Takeaway: Greg Brockman explains that AI compute demand is essentially unlimited, and the scaling laws continue to hold with no ceiling in sight.

Greg Brockman 是 Stripe 早期员工（Employee #4，首位 CTO）和 OpenAI 联合创始人。他分享了关于 AI 未来的深刻洞见：

- OpenAI 的商业模式非常简单：购买、租赁、建设计算资源，然后以 margin 转售。只要 margin 是正的，就想扩大规模，因为对解决 intelligence 的需求是无限的。
- 计算资源永远不够用。自 ChatGPT 推出以来，团队一直在尽可能多地购买计算资源，但从未能跟上需求。
- 扩展定律是深层的、美丽的它们感觉非常基础，就像物理学定律一样。这些是经验性的，我们不一定有完整的理论来解释为什么它有效。
- 神经网络早在 1940 年代就被设计出来，远在计算机之前。我们能够采用当时开发的想法，并应用越来越多的计算。只要向模型投入更多计算，它们就会变得更强大。
- Transformer 之后还有更多的创新空间。OpenAI 一直在投资长期研究如何改进架构和基础算法。

https://www.youtube.com/watch?v=XXX

---

*Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders*