# Methodology Guardrails（方法论护栏）

**定义**：将成熟的产品方法论和协作框架嵌入智能体工作流，为模型推理提供判断边界，防止泛化、堆砌或跳步。

---

## 为什么需要护栏

模型擅长生成，但如果没有边界：
- 容易**泛化**：脱离具体语境做泛泛而谈
- 容易**堆砌**：罗列大量信息但缺乏判断
- 容易**跳步**：跳过关键推理环节直接给结论

---

## Anthropic PM Skills 中使用的框架

| 框架 | 用途 | 出现在 |
|------|------|--------|
| Jobs-to-be-Done | 需求定义 | write-spec |
| How Might We | 问题扩展 | product-brainstorming |
| Opportunity Solution Tree | 方案探索 | product-brainstorming |
| MoSCoW | 优先级排序 | roadmap-update |
| RICE 评分 | 优先级量化 | roadmap-update |
| ICE 评分 | 优先级量化 | roadmap-update |
| OKR | 目标对齐 | roadmap-update |
| ROAM | 风险管理 | sprint-planning |
| ADR | 架构决策 | write-spec |

---

## 护栏的作用机制

1. **提供判断边界**：模型知道"到这里该用哪种思考方式"
2. **强制结构化**：不能随意跳过某个评估维度
3. **可解释性**：结论可以追溯到你用的哪个框架、哪个维度

---

## 关键洞察

> "这些框架的价值，不只在于让输出看起来更专业，更关键的是它们为模型提供了判断边界。"

框架不是用来"装饰"的，是用来"约束推理过程"的。

---

## 使用建议

- 不要为用框架而用框架
- 选择与当前阶段匹配的框架（证据整理阶段用 JTBD，优先级阶段用 RICE）
- 团队可以有自己的框架，关键是"有边界"而非"用哪个"

---

## 来源

- [[anthropic-pm-skills-summary]]
