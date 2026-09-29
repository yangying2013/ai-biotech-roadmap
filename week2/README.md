# 第 2 周：SQL 基础

目标：SELECT、WHERE、聚合、GROUP BY、JOIN。交付：10 道题的 SQL + 一句话解释。

## 第一步：学（约 3 小时）

Mode SQL 教程：Basic SQL（15 节）全部 + Intermediate SQL 里 JOIN 和聚合的部分。
只看、不背，每节把例子亲手敲一遍。

## 第二步：生物场景练习（约 2–3 小时）

下面这套数据是模拟的 qPCR 实验：`samples` 是样本信息，`assays` 是每个样本每个基因的 Ct 值。

在 Kaggle 新建 Notebook，把两个 CSV 传上去，跑这段加载代码：

```python
import sqlite3, pandas as pd
con = sqlite3.connect(":memory:")
pd.read_csv("samples.csv").to_sql("samples", con, index=False)
pd.read_csv("assays.csv").to_sql("assays", con, index=False)
pd.read_sql("SELECT * FROM samples LIMIT 3", con)
```

然后按顺序做这 10 道题（Ct 值越小 = 表达量越高）：

1. 查出所有 tumor 样本的 sample_id 和 tissue
2. 按 tissue 分组，统计每种组织有多少样本
3. 计算每个基因的平均 Ct 值
4. 找出 Ct < 28 的所有 assay 记录，按 ct_value 从小到大排
5. 把两张表连起来：查 tumor 样本中 TP53 的 ct_value（要 sample_id、tissue、ct_value）
6. 按 condition 分组，统计 tumor 和 normal 各有多少条 assay 记录
7. 找出做了超过 2 个 replicate 的（sample_id、gene）组合
8. 对比每个基因在 tumor vs normal 中的平均 Ct 值（提示：JOIN + 条件聚合）
9. 找出还没有任何 assay 记录的样本
10. 按 gene 统计 assay 数量，只保留数量 > 5 的基因，按数量降序排列

## 第三步：刷题（约 1–2 小时）

DataLemur 上按 Easy 筛选，做 10 道。重点看官方答案的写法，和你自己的对比。

## 交付

新建 `week2-sol.md`，每道题写：题目、你的 SQL、一句话解释（"为什么这样写"）。
传到 GitHub 仓库的 week2 文件夹。第 2 周结束。
