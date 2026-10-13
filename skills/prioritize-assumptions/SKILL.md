---
name: prioritize-assumptions
slug: prioritize-assumptions
version: "1.0.0"
displayName: 假设优先级排序
category: 产品发现
description: "用影响力 × 风险矩阵为假设排优先级，并为每个假设建议验证实验。当需要梳理一堆假设、决定先测什么或应用假设优先级画布时使用。"
---

## 假设优先级排序（Prioritize Assumptions）

用影响力 × 风险矩阵给假设分诊，并建议针对性实验。

### 背景

你正在帮 **{user_input}** 给假设排优先级。

如果用户提供了包含假设或研究数据的文件，先读这些文件。

### 领域背景

**ICE** 很适合假设优先级排序：影响力（机会分 × 客户数）× 信心度（1-10）× 易行度（1-10）。机会分 = 重要性 ×（1 − 满意度），归一化到 0-1（Dan Olsen 提出）。**RICE** 则把影响力拆成触达 × 影响两项分别打分：(R × I × C) / E。完整公式和模板见 `prioritization-frameworks` 技能。

### 操作说明

用户会给出待排序的假设清单。应用以下框架：

1. **对每个假设**，评估两个维度：
   - **影响力**：验证该假设能创造的价值，以及受影响的客户数量（ICE 中：影响力 = 机会分 × 客户数）
   - **风险**：定义为（1 − 信心度）× 工作量

2. **用影响力 × 风险矩阵归类每个假设**：
   - **低影响力、低风险** → 推迟测试，等更高优先级的假设处理完再说
   - **高影响力、低风险** → 直接进入实现（低风险、高回报）
   - **低影响力、高风险** → 否决这个想法（不值得投入）
   - **高影响力、高风险** → 设计一个实验来验证它

3. **对每个需要测试的假设**，建议一个实验，要求：
   - 用最小工作量换取最多被验证的认知
   - 度量真实行为，而不是口头意见
   - 有清晰的成功指标和阈值

4. **以排好优先级的矩阵或表格呈现结果**。

逐步思考。如果输出内容较多，保存为 Markdown。

---

### 延伸阅读

- [Assumption Prioritization Canvas: How to Identify And Test The Right Assumptions](https://www.productcompass.pm/p/assumption-prioritization-canvas)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm)（视频课程）
