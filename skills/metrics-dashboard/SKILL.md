---
name: metrics-dashboard
slug: metrics-dashboard
version: "1.0.0"
displayName: 指标仪表盘设计
category: 产品发现
description: "定义并设计产品指标仪表盘，涵盖关键指标、数据来源、可视化类型和告警阈值。当需要创建指标仪表盘、定义 KPI、搭建产品分析体系或制定数据监控方案时使用。"
---

## 产品指标仪表盘

用对的指标、可视化和告警阈值，设计一套完整的产品指标仪表盘。

### 背景

你正在为 **{user_input}** 设计指标仪表盘。

如果用户提供了文件（现有仪表盘、分析数据、OKR 或战略文档），先读这些文件。

### 领域背景

**指标 vs KPI vs 北极星指标（NSM）**：指标 = 所有可度量的东西。KPI = 少数几个长期跟踪的关键量化指标。北极星指标 = 单一以客户为核心的 KPI，是业务成功的先行指标。

**好指标的 4 条标准**（Ben Yoskovitz，《精益数据分析》（Lean Analytics））：(1) 易懂——能形成共同语言。(2) 可比——看时间趋势，不是看快照。(3) 比率或速率——比绝对数字更有揭示性。(4) 能改变行为——黄金法则：「如果一个指标不会改变你的行为，它就是个坏指标。」

**8 类指标**：虚荣指标 vs 可行动指标（只有可行动指标能改变行为），定性 vs 定量（是什么 vs 为什么——两者都要；永远不要停止和客户交流），探索型 vs 报表型（探索数据以发现意外洞察），滞后指标 vs 先行指标（先行指标让学习循环更快，例如客户投诉预示流失）。

**5 个行动步骤**：(1) 按 4 条好指标标准审计现有指标。(2) 更新仪表盘——确保所有关键指标都是好指标。(3) 识别虚荣指标——谨慎使用。(4) 区分先行与滞后指标。(5) 挑一个问题，深挖数据。

案例与更多细节参见 Ben Yoskovitz 的 [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)

### 操作说明

1. **确定指标框架** —— 把指标分层组织：

   **北极星指标**：最能体现核心价值交付的单一指标

   **输入指标**（3-5 个）：驱动北极星的杠杆

   **健康度指标**：保障产品整体健康的护栏

   **业务指标**：收入、成本和单位经济模型

2. **为每个指标定义**：

   | 指标 | 定义 | 数据来源 | 可视化 | 目标值 | 告警阈值 |
   |---|---|---|---|---|---|
   | ［名称］ | ［精确计算：分子/分母、时间窗口］ | ［数据从哪里来］ | ［折线图 / 柱状图 / 数字卡 / 漏斗］ | ［目标数值］ | ［何时触发告警］ |

3. **设计仪表盘布局**：

   ```
   ┌─────────────────────────────────────────────┐
   │  北极星：［指标］ — ［当前值］                │
   │  趋势：［↑/↓ 较上期 X%］                     │
   ├──────────────────┬──────────────────────────┤
   │  输入指标 1      │  输入指标 2              │
   │  ［迷你趋势图］  │  ［迷你趋势图］          │
   ├──────────────────┼──────────────────────────┤
   │  输入指标 3      │  输入指标 4              │
   │  ［迷你趋势图］  │  ［迷你趋势图］          │
   ├──────────────────┴──────────────────────────┤
   │  健康度：［延迟］［错误率］［NPS］            │
   ├─────────────────────────────────────────────┤
   │  业务：［MRR］［CAC］［LTV］［流失率］        │
   └─────────────────────────────────────────────┘
   ```

4. **设定复盘节奏**：
   - **每日**：运营健康度（错误、延迟、关键流程）
   - **每周**：输入指标与活跃趋势
   - **每月**：北极星、业务指标、OKR 进度
   - **每季度**：战略复盘与指标校准

5. **定义告警**：
   - 什么阈值触发排查？
   - 告警发给谁、通过什么渠道？
   - 期望的响应时间是多久？

6. **根据用户场景推荐工具**：
   - Amplitude、Mixpanel、PostHog 做产品分析
   - Looker、Metabase、Mode 做 SQL 类仪表盘
   - Datadog、Grafana 做运营健康度监控

逐步思考。把仪表盘规格保存为 Markdown 文档。

---

### 延伸阅读

- [The Ultimate List of Product Metrics](https://www.productcompass.pm/p/the-ultimate-list-of-product-metrics)
- [The North Star Framework 101](https://www.productcompass.pm/p/the-north-star-framework-101)
- [The Product Analytics Playbook: AARRR, HEART, Cohorts & Funnels for PMs](https://www.productcompass.pm/p/the-product-analytics-playbook-aarrr)
- [AARRR (Pirate) Metrics: The 5-Stage Framework for Growth](https://www.productcompass.pm/p/aarrr-pirate-metrics)
- [The Google HEART Framework: Your Guide to Measuring User-Centric Success](https://www.productcompass.pm/p/the-google-heart-framework)
- [Funnel Analysis 101: How to Track and Optimize Your User Journey](https://www.productcompass.pm/p/funnel-analysis)
- [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm)（视频课程）
