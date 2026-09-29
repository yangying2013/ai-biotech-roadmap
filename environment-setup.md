# 环境搭建（第 1 周）

## 最快路径：零安装（推荐先用这个）

直接用浏览器里的 notebook，不用在电脑上装任何东西：

1. **Kaggle**（kaggle.com）：注册 → 点 "Create" → "New Notebook"，就能跑 Python/pandas。第 1–4 周的代码练习全可以在这里做。
2. 备选 **Google Colab**（colab.research.google.com）：用 Google 账号登录即用。

scikit-learn、pandas、numpy 这些包在两个平台都预装好了。

## 本地路径（以后再说，不着急）

等第 1–4 周跑顺了、确实需要本地环境时再做：

1. 装 Python 3.11（python.org 下载安装包；Mac 也可用 `brew install python@3.11`）
2. 建虚拟环境：`python3 -m venv ~/ai-biotech-env`
3. 激活：`source ~/ai-biotech-env/bin/activate`（Mac）或 `.\ai-biotech-env\Scripts\activate`（Windows）
4. 装包：`pip install pandas numpy scikit-learn jupyter scanpy rdkit`

## GitHub 仓库（第 1 周必做）

1. 注册 github.com 账号（5 分钟，有就跳过）
2. 点右上角 "+" → "New repository"，起名 `ai-biotech-roadmap`，选 Public
3. 把上面那个 README.md 传上去：进仓库点 "Add file" → "Upload files"，把文件拖进去，点 Commit

第 1 周结束时，这个仓库里应该有：README、技能自评表、关键词频次表。
