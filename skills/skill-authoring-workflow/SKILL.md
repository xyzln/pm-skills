---
name: skill-authoring-workflow
slug: skill-authoring-workflow
version: "1.0.0"
displayName: 技能创作工作流
category: 端到端工作流
description: 把原始 PM 内容变成合规、可发布的技能。当需要创建或更新仓库中的技能且不破坏标准时使用。
intent: >-
  有条不紊地创建或更新 PM 技能。这条工作流把粗糙的笔记、工作坊内容或半成品的提示词堆料，转化为合规的 `skills/<skill-name>/SKILL.md` 资产——真正能通过校验、配得上放进本仓库。
type: workflow
best_for:
  - "从笔记或源材料创建一个新的仓库技能"
  - "在保持标准不变的前提下更新现有技能"
  - "在提交前跑完整的创作与校验工作流"
scenarios:
  - "帮我把这些工作坊笔记变成一个新的 PM 技能"
  - "我需要更新一个现有技能，又不想破坏仓库标准"
  - "在这个仓库里创作新技能应该用哪条工作流？"
source: "https://github.com/deanpeters/Product-Manager-Skills"
license: "CC BY-NC-SA 4.0"
adapted: true
---

## 用途

有条不紊地创建或更新 PM 技能。这条工作流把粗糙的笔记、工作坊内容或半成品的提示词堆料，转化为合规的 `skills/<skill-name>/SKILL.md` 资产——真正能通过校验、配得上放进本仓库。

当你想发布一个新技能，又不想凭「我看着还行」碰运气时，请使用本工作流。

## 核心概念

### Dogfood 优先

先用仓库内的工具与标准，而不是自创流程：
- `scripts/find-a-skill.sh`
- `scripts/add-a-skill.sh`
- `scripts/build-a-skill.sh`
- `scripts/test-a-skill.sh`
- `scripts/check-skill-metadata.py`

### 选对创建路径

- **引导式向导（`build-a-skill.sh`）**：有想法但还没有成文时最佳。
- **内容优先的生成器（`add-a-skill.sh`）**：已经有源内容时最佳。
- **手动编辑 + 校验**：打磨现有技能时最佳。

### 完成的定义（Definition of Done，没有例外）

一个技能只有满足以下条件才算完成：
1. frontmatter 合法（`name`、`description`、`intent`、`type`）
2. 章节顺序合规
3. 元数据长度限制得到遵守（`name` 不超过 64 字符，`description` 不超过 200 字符）
4. `description` 同时说明技能做什么、什么时候用
5. `intent` 承载更完整的面向仓库的摘要，但不能取代以触发为导向的 `description`
6. 交叉引用均可解析
7. README 目录中的计数与表格已更新（若增删技能）

### 引导协议来源

当以引导对话的方式运行本工作流时，使用 [`workshop-facilitation`](../workshop-facilitation/SKILL.md) 作为交互协议。

它定义了：
- 会话开始提示 + 进入模式（引导式、背景倾倒、最佳猜测）
- 每轮只问一个问题，并使用通俗易懂的提示语
- 进度标识（例如「背景问题 Qx/8」与「评分问题 Qx/5」）
- 中断处理与暂停/恢复行为
- 决策点给出编号建议
- 常规问题提供编号快捷选项（必要时包含「其他（请说明）」）

本文件定义工作流顺序与领域专用产出。如有冲突，以本文件的工作流逻辑为准。

## 应用方式

### 阶段 1：预检（避免重复劳动）

1. 搜索是否有重叠的技能：

```bash
./scripts/find-a-skill.sh --keyword "<topic>"
```

2. 确定类型：
- **组件（Component）**：单一产物/模板
- **交互式（Interactive）**：3-5 个自适应问题 + 编号选项
- **工作流（Workflow）**：多阶段编排

### 阶段 2：生成草稿

如果你有源材料：

```bash
./scripts/add-a-skill.sh research/your-framework.md
```

如果你想要引导式提问：

```bash
./scripts/build-a-skill.sh
```

### 阶段 3：打磨技能

人工检查以下几点：
- 清晰的「何时使用」指引
- 一个具体示例
- 一个明确的反模式
- 没有废话或含糊的顾问式空话

### 阶段 4：严格校验

在考虑提交之前，先跑严格检查：

```bash
./scripts/test-a-skill.sh --skill <skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<skill-name>/SKILL.md
python3 scripts/check-skill-triggers.py skills/<skill-name>/SKILL.md --show-cases
```

### 阶段 5：与仓库文档整合

如果这是一个新技能：
1. 把它加进 README 中正确的分类表格
2. 更新技能总数与各分类计数
3. 验证链接路径可解析

### 阶段 6：可选打包

若需打包技能以上传到技能平台：

```bash
./scripts/zip-a-skill.sh --skill <skill-name>
# 或按分类打包：
./scripts/zip-a-skill.sh --type component --output dist/skill-zips
# 或使用精选入门预设：
./scripts/zip-a-skill.sh --preset core-pm --output dist/skill-zips
```

## 示例

### 示例：把工作坊笔记转化为技能

输入：`research/pricing-workshop-notes.md`  
目标：一个新的交互式顾问技能

```bash
./scripts/add-a-skill.sh research/pricing-workshop-notes.md
./scripts/test-a-skill.sh --skill <new-skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<new-skill-name>/SKILL.md
```

预期结果：
- 新技能目录已创建
- 技能通过结构与元数据检查
- README 目录条目已添加/更新

### 反模式示例

「我们写了个很酷的技能，跳过校验，忘了更新 README 计数，然后就发布了。」

结果：
- 引用失效
- 目录数字前后不一致
- 贡献者和用户都感到困惑

## 常见陷阱

- 凭感觉发布，而不是靠标准。
- 任务本质上是组件模板，却选成了 `workflow` 类型。
- 描述臃肿，超出上传限制。
- 描述只说了技能是什么，却没说明 AI 助手应该在什么时候触发它。
- 描述悄悄顶到 200 字符上限，话没说完就被截断。
- 让 `intent` 取代了无力的触发型描述。
- 添加技能后忘记更新 README 计数。
- 把生成结果当作终稿，不做复核。

## 参考

- `README.md`
- `AGENTS.md`
- `docs/Building PM Skills.md`
- `docs/Add-a-Skill Utility Guide.md`
- 《AI 助手技能构建完全指南》（外部参考资料）
- `scripts/add-a-skill.sh`
- `scripts/build-a-skill.sh`
- `scripts/find-a-skill.sh`
- `scripts/test-a-skill.sh`
- `scripts/check-skill-metadata.py`
- `scripts/check-skill-triggers.py`
- `scripts/zip-a-skill.sh`

---
*本技能改编自 [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills)，依据 CC BY-NC-SA 4.0 许可协议发布。*
