---
name: prioritize-features
description: "基于影响、工作量、风险与战略契合度对功能构想需求池进行优先级排序，给出前 5 名推荐。当需要排列功能需求池优先级、做范围决策，或给产品想法排名时使用。"
---

## 功能需求池优先级排序

评估并排列功能构想需求池，找出最值得推进的前 5 个。

### 背景

你在帮助为 **{user_input}** 排列功能优先级。

如果用户提供了文件（表格、需求池、机会评估等），直接读取并分析它们。

### 领域背景

框架选择指导见 `prioritization-frameworks` 技能。核心建议：

**机会分数（Opportunity Score）**（Dan Olsen《精益产品手册》（The Lean Product Playbook））推荐用于评估客户问题：机会分数 = 重要性 ×（1 − 满意度），归一化到 0-1。重要性高 + 满意度低 = 最佳机会。优先解决**问题（机会）**，而不是方案。

**ICE 评分**推荐用于快速给事项打分：影响（Impact，机会分数 × 客户数）× 信心（Confidence）× 易操作性（Ease）。**RICE 评分**则为较大团队额外增加了触达（Reach）作为独立因子。

### 操作说明

用户会描述产品目标、期望成果，并提供功能构想。按以下步骤推进：

1. **理解优先级**：确认产品目标与成功指标。

2. **从以下维度评估每个功能**：
   - **影响（Impact）**：它对期望成果有多大的推动作用？如有客户数据，可参考机会分数。
   - **工作量（Effort）**：需要多少开发、设计与协调投入？
   - **风险（Risk）**：存在多大不确定性？哪些假设需要验证？
   - **战略契合度（Strategic alignment）**：它与产品愿景和当前目标的匹配程度如何？

3. **推荐前 5 个功能**，并附上：
   - 清晰的排名（1-5）
   - 每项入选的简要理由
   - 权衡过的关键取舍
   - 哪些被降级了，为什么

4. **如有帮助，以优先级表格呈现**。

一步一步地思考。如果输出内容较多，以 Markdown 格式保存。

---

### 延伸阅读

- [Kano 模型：如何让客户惊喜，而不是沦为功能工厂](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [产品管理框架大全 + 模板](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [持续产品探索大师课（CPDM）](https://www.productcompass.pm/p/cpdm)（视频课程）
