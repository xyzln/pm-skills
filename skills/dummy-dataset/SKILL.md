---
name: dummy-dataset
description: "生成逼真的模拟数据集用于测试，支持自定义列、约束与输出格式（CSV、JSON、SQL、Python 脚本）。当需要创建测试数据、构建模拟数据集，或为开发与演示生成样本数据时使用。"
---
# 模拟数据集生成

生成逼真的模拟数据集用于测试，支持自定义列、约束与输出格式（CSV、JSON、SQL、Python 脚本）。产出可直接执行的脚本或直接可用的数据文件，拿来即用。

**适用场景：** 创建测试数据、生成样本数据集、为开发构建逼真的模拟数据，或填充测试环境。

**参数：**
- `$PRODUCT`：产品或系统名称
- `$DATASET_TYPE`：数据类型（例如：客户反馈、交易记录、用户资料）
- `$ROWS`：生成的行数（默认：100）
- `$COLUMNS`：需要包含的列或字段
- `$FORMAT`：输出格式（CSV、JSON、SQL、Python 脚本）
- `$CONSTRAINTS`：额外的约束或业务规则

## 分步流程

1. **明确数据集类型** — 理解数据所属领域
2. **定义列规格** — 名称、数据类型与取值范围
3. **确定行数** — 需要多少条样本记录
4. **选择输出格式** — CSV、JSON、SQL INSERT 或 Python 脚本
5. **应用真实模式** — 确保数据看起来真实、合法
6. **添加业务约束** — 尊重业务逻辑与数据关系
7. **生成数据或脚本** — 产出可执行的结果
8. **校验输出** — 确保数据质量与完整性

## 模板：Python 脚本输出

```python
import csv
import json
from datetime import datetime, timedelta
import random

# 配置
ROWS = $ROWS
FILENAME = "$DATASET_TYPE.csv"

# 列定义与逼真的取值生成器
columns = {
    "id": "auto-increment",
    "name": "first_last_name",
    "email": "email",
    "created_at": "timestamp",
    # 添加更多列……
}

def generate_dataset():
    """生成逼真的模拟数据集"""
    data = []
    for i in range(1, ROWS + 1):
        record = {
            "id": f"U{i:06d}",
            # 根据列定义生成取值
        }
        data.append(record)
    return data

def save_as_csv(data, filename):
    """将数据集保存为 CSV"""
    with open(filename, 'w', newline='') as f:
        writer = csv.DictWriter(f, fieldnames=data[0].keys())
        writer.writeheader()
        writer.writerows(data)

if __name__ == "__main__":
    dataset = generate_dataset()
    save_as_csv(dataset, FILENAME)
    print(f"已生成 {len(dataset)} 条记录，输出至 {FILENAME}")
```

## 示例数据集规格

**数据集类型：** 客户反馈

**列：**
- feedback_id（自增，U001、U002……）
- customer_name（真实感姓名）
- email（合法邮箱格式）
- feedback_date（最近 90 天内的日期）
- rating（1-5 星）
- category（缺陷、功能建议、投诉、好评）
- text（真实感反馈内容）
- product（电子产品、服饰、家居用品）

**约束：**
- 评分分布倾斜：40% 五星、30% 四星、20% 三星、10% 一至二星
- 缺陷类反馈评分只在 1-3 分
- 功能建议类反馈评分只在 3-5 分
- 邮箱域名真实（qq.com、163.com、company.com 等）

## 交付物

- 可直接执行的 Python 脚本，或直接可用的数据文件
- 带规范表头与格式的 CSV 文件
- 结构与类型均合法的 JSON 文件
- 用于灌库的 SQL INSERT 语句
- 通过数据校验并满足约束
- 取值真实且符合业务语境
- 附数据生成逻辑说明
- 附数据集使用快速上手说明

## 输出格式

**CSV：** 扁平表格格式，便于导入表格软件（如 Excel）和数据库

**JSON：** 嵌套结构，适合 API 与 NoSQL 数据库

**SQL：** INSERT 语句，可直接在关系型数据库上执行

**Python 脚本：** 可执行的生成器，适合定制或大规模数据集
