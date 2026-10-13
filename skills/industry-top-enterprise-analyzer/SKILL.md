---
name: top-enterprise-analyzer
slug: industry-top-enterprise-analyzer
version: "1.0.0"
displayName: 头部企业分析
category: 行业分析
description: "分析指定行业的 10 家头部企业，按市值/营收从 1 到 10 排名。当用户说“头部企业分析”“X 行业 Top 10”“行业 Top 10”“行业龙头”“行业头部”“行业 leader”时使用。输出 Markdown，含排名总览表 + 逐家公司深度分析。属于行业分析器插件（6 技能流水线第 1 环）。"
source: "https://github.com/zrxparley/industry-analyzer-skill"
---

# 头部企业分析器 (Top Enterprise Analyzer)

分析指定行业的 10 家头部企业，按市值/营收从 1 到 10 排名，并附逐家公司深度分析。

## 适用场景

- 用户明确要求"分析 {行业} 头部企业 / Top 10 / 行业龙头"
- 行业分析流水线第 1 环（由 行业分析成章官 调度）
- 用户给出 `output/{slug}/session.json` 路径，单独跑这个 Skill 做"重跑头部维度"或"补查"

## 输入

- **必填**：`output/{industry-slug}/session.json`
  - 读取 `industry` / `scope` / `time_window` / `language` / `audience`
- **可选**：用户可在 prompt 中追加特殊要求（如"只看上市公司"、"只看未上市独角兽"、"按市值排还是营收排"）

## 输出

- **文件**：`output/{industry-slug}/01-top-enterprise.md`
- **格式**：Markdown，含 1 张总览表 + 10 段公司详解（每段 200-300 字）

### 必含要素（每家公司）

| 要素 | 说明 |
|---|---|
| 排名 | 1-10 |
| 公司名 | 中文 + 英文（如有） |
| 市值或最新年度营收 | 注明口径（市值/营收/估值） |
| 主营业务 | 1-2 句话 |
| 市场份额或行业地位 | 量化或定性 |
| 数据来源 | 注明（财报/官网/榜单/报告） |
| 备注 | 公司近期重大事件、战略动作 |

### 找不到的处理

- 显式标"未找到，参考线索：..."+ 给出 1-2 个备选
- 不编造、不夸大、不假装全知

## 工作流

1. **读 session.json**：确认 industry / scope / time_window / language / audience
2. **web_search 头部企业**：组合多次搜索
   - `"{行业} 头部企业 排名 {year}"`
   - `"{行业} Top 10 companies revenue {year}"`
   - `"{行业} 上市公司 市值 排行"`
   - `"{行业} 行业龙头 市场份额"`
   - `"{industry} market leaders ranking"`
3. **取 Top 10**：按市值或最新年度营收排序，**注明排序口径**
4. **每家深挖**：用 webfetch 拿公司官网 / 财报 / 维基百科 / 行业报告
5. **写 `01-top-enterprise.md`**：总览表 + 逐家详解
6. **更新 session.json**

### 输出模板

参见 `references/top-10-template.md`

## 停止条件

- `01-top-enterprise.md` 存在
- 包含 10 家公司
- 每家公司 4 要素齐（排名 / 营收市值 / 主营 / 份额）
- 数据来源标注
- 不确定处显式标注
- session.json `status.top-enterprise` = `done`

## 风格

- 数据精确、来源可追溯、不夸大
- 表格汇总 + 逐家详解
- 不写"加油""努力"等空话
- 不确定 → 显式标"未找到，参考线索：..."，不编造

## 更新 session.json

- 改 `status.top-enterprise` = `done`（失败则 `failed`）
- 改 `updated_at`
- 在 `data_sources` 追加本次搜索记录 `{dim, queries, results_summary}`

## 独立运行模式

若用户未提供 session.json，可直接传参：
- 行业名（必填）
- scope（默认"中国"）
- time_window（默认"近 1 年"）
- 输出落到默认路径 `output/{industry-slug}/01-top-enterprise.md`（自动生成最小 session.json）

## 错误处理

- 行业名太宽泛（"商业"）→ 提示用户细化
- 行业资料稀少 → 退回 AI 通用知识 + 显式标"未找到具体数据"
- web 搜索失败 → 保留 AI 整合部分 + 在 `data_sources` 标错误原因
- 找不到 10 家 → 至少给 5-7 家，明确说明行业集中度

## 参考

- 行业分析器总 spec：`~/Downloads/周报生成器/行业分析器/docs/superpowers/specs/2026-06-07-industry-analyzer-design.md` §5.1
- 模板：`references/top-10-template.md`
