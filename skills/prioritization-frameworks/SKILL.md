---
name: prioritization-frameworks
description: "9 种优先级排序框架的参考指南，含公式、使用时机与模板——RICE、ICE、Kano、MoSCoW、机会分数等。当需要选择优先级排序方法、比较 RICE 与 ICE 等框架，或了解不同排序方法的原理时使用。"
---

## 优先级排序框架参考

一份参考指南，帮你根据所处场景选择合适的优先级排序框架并加以应用。

### 核心原则

永远不要让客户来设计方案。要优先处理**问题（机会）**，而不是功能。

### 机会分数（Opportunity Score，Dan Olsen，*The Lean Product Playbook*）

推荐的客户问题优先级排序框架。

针对每个需求调研客户的**重要性**和**满意度**（归一化到 0-1 分）。

三个相关公式：
- **当前价值** = 重要性 × 满意度
- **机会分数** = 重要性 ×（1 − 满意度）
- **创造的客户价值** = 重要性 ×（S2 − S1），其中 S1 为改善前的满意度，S2 为改善后的满意度

重要性高 + 满意度低 = 机会分数最高 = 最好的机会。画在重要性-满意度图上——左上象限是甜点区。它优先排序的是客户问题，而不是解决方案。

### ICE 框架

适合给举措和想法排优先级。它不仅考虑价值，也考虑风险和经济因素。

- **I**（影响 Impact）= 机会分数 × 受影响的客户数
- **C**（信心 Confidence）= 我们有多大把握？（1-10）计入风险。
- **E**（容易度 Ease）= 实现起来有多容易？（1-10）计入经济因素。

**得分** = I × C × E。分数越高越优先。

### RICE 框架

把 ICE 的影响拆成两个独立因子。适合需要更细粒度的大型团队。

- **R**（触达 Reach）= 受影响的客户数
- **I**（影响 Impact）= 机会分数（每个客户的价值）
- **C**（信心 Confidence）= 我们有多大把握？（0-100%）
- **E**（工作量 Effort）= 实现需要多少工作量？（人月）

**得分** = (R × I × C) / E

### 9 种框架概览

| 框架 | 最适合 | 核心洞察 |
|------|--------|----------|
| 艾森豪威尔矩阵（Eisenhower Matrix） | 个人任务 | 紧急 vs 重要——用于个人产品经理的任务管理 |
| 影响 vs 工作量（Impact vs Effort） | 任务/举措 | 简单 2×2——快速分诊，不适合严谨的战略决策 |
| 风险 vs 回报（Risk vs Reward） | 举措 | 类似影响 vs 工作量，但计入了不确定性 |
| **机会分数（Opportunity Score）** | 客户问题 | **推荐。** 重要性 ×（1 − 满意度）。归一化到 0-1。 |
| Kano 模型 | 理解期望 | 必备型、期望型、魅力型、无差异型、反向型。用于理解，而非排序。 |
| 加权决策矩阵（Weighted Decision Matrix） | 多因子决策 | 给标准赋权，给每个选项打分。有助于争取相关方认同。 |
| **ICE** | 想法/举措 | 影响 × 信心 × 容易度。推荐用于快速排序。 |
| **RICE** | 规模化排想法 | （触达 × 影响 × 信心）/ 工作量。在 ICE 基础上加了触达。 |
| MoSCoW 法则 | 需求 | 必须/应该/可以/不做。注意：源自项目管理。 |

### 模板

- [机会分数介绍（PDF）](https://drive.google.com/file/d/1ENbYPmk1i1AKO7UnfyTuULL5GucTVufW/view)
- [重要性 vs 满意度模板 — Dan Olsen（Google 幻灯片）](https://docs.google.com/presentation/d/1jg-LuF_3QHsf6f1nE1f98i4C0aulnRNMOO1jftgti8M/edit#slide=id.g796641d975_0_3)
- [ICE 模板（Google 表格）](https://docs.google.com/spreadsheets/d/1LUfnsPolhZgm7X2oij-7EUe0CJT-Dwr-/edit?usp=share_link&ouid=111307342557889008106&rtpof=true&sd=true)
- [RICE 模板（Google 表格）](https://docs.google.com/spreadsheets/d/1S-6QpyOz5MCrV7B67LUWdZkAzn38Eahv/edit?usp=sharing&ouid=111307342557889008106&rtpof=true&sd=true)

---

### 延伸阅读

- [产品管理框架大全 + 模板（The Product Management Frameworks Compendium + Templates）](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Kano 模型：如何让客户满意而不沦为功能工厂](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [持续产品发现大师课（CPDM）](https://www.productcompass.pm/p/cpdm)（视频课程）
