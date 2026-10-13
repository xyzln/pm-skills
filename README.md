<p align="center">
  <img src="assets/logo.png" alt="PM Skills Logo" width="200">
</p>

<h1 align="center">PM Skills · 产品经理技能库</h1>

<p align="center"><strong>135 个即装即用的中文产品管理技能，覆盖产品全生命周期。</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/skills-135-brightgreen" alt="skills">
  <img src="https://img.shields.io/badge/lang-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-red" alt="lang">
  <img src="https://img.shields.io/badge/license-MIT%20%2B%20CC%20BY--NC--SA%204.0-blue" alt="license">
</p>

让你的 AI 助手具备产品经理的完整思维框架。从用户发现、战略规划到执行落地、上市增长——135 个技能全部按中文产品经理的工作场景重构：框架术语中英对照、示例改用中国公司与人民币场景、办公工具对齐钉钉/飞书/企业微信，且完全平台中立，适用于任何支持 SKILL.md 的 AI 助手。

---

## 📦 快速安装

```bash
# 一键安装所有技能
git clone <本仓库地址> /tmp/pm-skills
cp -R /tmp/pm-skills/skills/* <你的AI助手技能目录>/
rm -rf /tmp/pm-skills
```

或者，直接把仓库地址发给你的 AI 助手：

> 「安装这个技能库：<本仓库地址>」

---

## 🚀 使用方式

### 方式一：自然对话

直接聊你的需求，技能自动匹配触发：

| 你说 | AI 助手自动调用 |
|------|----------------|
| "帮我写个 PRD" | → `create-prd` |
| "做一个 SWOT 分析" | → `swot-analysis` |
| "设计用户访谈提纲" | → `interview-script` |
| "估算市场规模" | → `market-sizing` 或 `tam-sam-som-calculator` |
| "做用户画像" | → `user-personas` 或 `proto-persona` |
| "给我竞争对手分析" | → `competitor-analysis` |
| "排优先级" | → `prioritization-frameworks` 或 `prioritize-features` |

### 方式二：`/pm` 聚合入口

输入 **`/pm`** 查看完整技能菜单，选择方向后自动路由：

```
/pm

🎯 想做什么？
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 1. 产品发现    — 脑暴、访谈、假设验证
 2. 产品策略    — SWOT、PESTLE、商业模式
 3. 执行        — PRD、OKR、Sprint、复盘
 4. 市场研究    — 用户画像、旅程图、竞品
 5. 数据分析    — SQL、Cohort、A/B 测试
 6. 上市策略    — GTM、ICP、战卡
 7. 营销增长    — 定位、北极星指标
 8. 行业分析    — 企业调研、生态图谱
 9. SaaS 指标   — 营收、CAC、LTV
10. PM 职场     — 简历、面试、晋升
...
```

---

## 🗂️ 技能全景图

| 分类 | 数量 | 核心技能 |
|------|:---:|---------|
| 🎯 **产品发现** | 15 | 脑暴、机会解决方案树、假设验证、访谈、功能排优 |
| 📋 **产品策略** | 14 | 战略画布、精益画布、商业模式、定价、SWOT、PESTLE、五力 |
| 🚀 **执行** | 22 | PRD、OKR、Sprint、故事拆分、测试场景、排优框架 |
| 🔬 **市场研究** | 12 | 用户画像、旅程图、竞品、市场估算、访谈准备 |
| 📊 **数据分析** | 5 | SQL、Cohort、A/B 测试、SaaS 营收指标 |
| 🏪 **上市策略（GTM）** | 6 | GTM 策略、ICP、滩头市场、增长飞轮、战卡 |
| 📈 **营销与增长** | 10 | 定位、北极星指标、营销创意、新闻稿、获客渠道 |
| 🧰 **工具箱** | 11 | NDA、隐私政策、简历、问题陈述、精益 UX 画布 |
| 🤖 **AI 交付与 AI 产品** | 7 | 文档化、差距分析、AI 就绪度、POL 探针 |
| 🎯 **JTBD 与问题界定** | 3 | JTBD 框架、问题框架、问题陈述 |
| 📊 **SaaS 财务与指标** | 5 | 营收指标、单位经济、财务参考、健康诊断、定价 |
| 🏆 **PM 职业发展与领导力** | 6 | 总监/VP 转型、面试、高管入职 |
| 🔬 **工作坊与引导** | 5 | 旅程图/故事图/定位工作坊 |
| 🎯 **端到端工作流** | 7 | 发现流程、PRD 开发、策略 session、全能 PM 操作员 |
| 🔬 **行业分析** | 4 | 头部企业、生态图谱、数字化方案 |
| 📊 **商业战略与分析** | 8 | BCG 矩阵、价值链、情景分析、赢单分析 |
| 🏆 **KPMG 战略框架** | 1 | KPMG 7 心智模型 + 5 决策启发式 |
| 🎯 **线索打分** | 2 | 线索打分启动与报告 |
| 🧭 **商业决策工具** | 3 | 商业背景与机会、定位模型、价值路线图 |
| 🧬 **自我进化（SkillOpt）** | 2 | 技能训练循环、睡眠进化 |

---

## 💡 亮点技能速览

| 技能 | 用途 |
|------|------|
| `create-prd` / `prd-development` | 8 段 PRD 模板 / 结构化 PRD 全流程 |
| `opportunity-solution-tree` | Teresa Torres 机会解决方案树 |
| `jobs-to-be-done` | 结构化 JTBD 需求探索 |
| `prioritization-frameworks` | 9 种排优先级框架参考（ICE/RICE/MoSCoW/Kano） |
| `saas-economics-efficiency-metrics` | CAC/LTV/Rule of 40 计算 |
| `press-release` | Amazon 逆向工作法新闻稿 |
| `kpmg-strategy-framework` | KPMG 7 个心智模型 |
| `bcg-growth-share-matrix` | BCG 产品组合矩阵 |
| `win-loss-analysis` | 赢单/丢单原因分析 |
| `pm-operator-digidai` | 全能 PM 操作员（SaaS 诊断 + PRD 评审 + 路线图） |

---

## 📜 技能来源与许可

本库整合了以下开源项目，并按中文习惯进行了重构（全文翻译、示例本地化、平台标记中立化）。每个技能的 `SKILL.md` frontmatter 中都保留了 `source` 与 `license` 原始署名：

| 来源 | 许可 | 技能数 |
|------|:----:|:----:|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT | 68 |
| [zrxparley 自建项目](https://github.com/zrxparley)（business-decision-tool / industry-analyzer-skill / lead-scoring / kpmg-strategy-framework） | MIT | 18 |
| [microsoft/SkillOpt](https://github.com/microsoft/SkillOpt) | MIT | 2 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 45 |
| [Digidai/Product-Manager-Skills](https://github.com/Digidai/Product-Manager-Skills) | CC BY-NC-SA 4.0 | 1 |
| 自定义（pm-hub 聚合入口） | MIT | 1 |

> ⚠️ **许可提示**：来自 deanpeters 和 Digidai 的 46 个技能采用 **CC BY-NC-SA 4.0**（署名-非商业性使用-相同方式共享），使用时需遵守非商业性要求及署名义务；其余技能为 MIT。派生作品需保留上述署名链条。

---

## 🏗️ 仓库结构

```
pm-skills/
├── LICENSE                    # MIT（仅适用 MIT 来源技能）
├── README.md                  # 本文件
├── assets/                    # 站点资源
└── skills/                    # 所有技能（扁平目录）
    ├── pm/                    # 聚合入口 ← 输入 /pm 进入
    ├── create-prd/            # 写 PRD
    ├── swot-analysis/         # SWOT 分析
    ├── jobs-to-be-done/       # JTBD 框架
    ├── kpmg-strategy-framework/  # KPMG 战略框架
    └── ...                    # 共 135 个技能
```

每个技能对应一个目录，内含一份 `SKILL.md`（YAML frontmatter + Markdown 指令体），复制到你的 AI 助手技能目录即可使用。

---

## 🔧 贡献指南

欢迎提交 Issue 或 PR 来完善技能库：

- **新增技能**：将 `SKILL.md` 放入 `skills/<技能名>/` 目录，frontmatter 至少包含 `name` 与 `description`（描述需写清"做什么"和"何时触发"）
- **修正内容**：发现某个技能的内容有误，直接提交 PR 修正
- **中文化规范**：新技能默认使用简体中文，术语首次出现附英文原文，示例优先使用中国公司场景

---

## 📄 许可证

- **MIT 来源技能**（phuryn、zrxparley 自建、microsoft/SkillOpt、pm-hub）：MIT License，见 [LICENSE](LICENSE)
- **CC BY-NC-SA 4.0 来源技能**（deanpeters、Digidai）：以各技能 frontmatter 中的 `license` 字段为准，需署名、非商业性使用、相同方式共享

---

<p align="center">
  <sub>Built from <a href="https://github.com/phuryn/pm-skills">phuryn/pm-skills</a> · <a href="https://github.com/deanpeters/Product-Manager-Skills">deanpeters/PM-Skills</a> · <a href="https://github.com/Digidai/Product-Manager-Skills">Digidai/PM-Skills</a> · <a href="https://github.com/microsoft/SkillOpt">microsoft/SkillOpt</a> · and more.</sub>
</p>
