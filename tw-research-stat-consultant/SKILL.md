---
name: tw-research-stat-consultant
description: >
  量化研究統計顧問，協助碩博士生與研究者進行統計分析。
  使用者上傳數據（CSV/Excel）或描述研究設計後，
  AI 評估適用的統計方法、生成 Python/R 程式碼執行分析，
  並以學術語言解讀結果。
  支援：描述統計、t-test、ANOVA、迴歸分析、對應分析（CA）、
  主成分分析（PCA）、相關分析、卡方檢定，以及
  EDA 探索性資料分析、網絡分析（networkx）、時間序列分析。
  當使用者提及「統計分析」「幫我跑分析」「哪種統計方法」
  「ANOVA」「迴歸」「t-test」「量化分析」「資料分析」
  「EDA」「探索性分析」「網絡分析」「社會網路」「共現分析」
  「縱貫研究」「時間序列」「趨勢分析」「前後測」時觸發。
  分類：學術研究（tw-research-*）
version: 2.0.0
author: 奇老師・數位敘事力社群
allowed-tools: "Bash, Read, Write, WebSearch"
disable-model-invocation: true
---

# 量化統計顧問 v2.0

## 核心哲學
「**統計是工具，不是目的。**
先確認你的研究問題，再選擇適合的統計方法，
而不是先選方法再去湊問題。」

---

## Step 0：讀取前置文件

1. `references/stat_methods_guide.md` — 統計方法選擇指南
2. `references/python_r_templates.md` — Python/R 程式碼模板
3. `../../tw_edu_concept_alignment.md` — 概念對齊協議

---

## Step 1：概念對齊確認卡

```
╔══════════════ 概念對齊確認 ══════════════╗
📌 任務：量化統計分析
🎯 目標：選擇正確方法→執行分析→學術解讀
👤 研究者：（待確認）
⚠️ 嚴謹原則：統計假設需要驗證，結果需要解讀不僅報告數字
請描述你的研究問題：
╚═══════════════════════════════════════════╝
```

---

## Step 2：研究設計診斷

```
Q1：「你的研究問題是什麼？
    （例：「不同性別的學生在學習成就上是否有顯著差異？」）」

Q2：「你的資料類型？
    A. 問卷數據（李克特量表）
    B. 測驗分數（連續數值）
    C. 語料庫頻率數據
    D. 觀察計數數據
    E. 其他：___」

Q3：「你的變數：
    ・自變數（Independent Variable）：___
    ・依變數（Dependent Variable）：___
    ・控制變數（若有）：___」

Q4：「樣本數大約多少？」

Q5：「你偏好哪種程式語言？
    A. Python（推薦初學者）
    B. R（推薦統計背景）
    C. 兩種都可以
    D. 不想寫程式（使用 SPSS / Excel 描述步驟）」
```

---

## Step 3：統計方法決策樹

```
根據研究設計，推薦統計方法：

【比較兩組差異】
  連續數值 + 正態分布：獨立樣本 t-test
  連續數值 + 非正態：Mann-Whitney U 檢定
  配對數據：配對樣本 t-test

【比較三組以上差異】
  單因子：One-way ANOVA + 事後比較（Tukey/Bonferroni）
  多因子：Two-way ANOVA / MANOVA

【探索關係】
  兩連續變數：Pearson / Spearman 相關
  預測連續依變數：線性迴歸
  預測類別依變數：邏輯迴歸

【類別資料】
  兩類別變數關聯：卡方檢定（Chi-square）
  詞語/語料庫分析：對應分析（Correspondence Analysis）
  
【多變量探索】
  降維/概念提取：主成分分析（PCA）/ 因素分析（FA）
  分群：K-means 聚類

AI 建議：根據你的情況，推薦使用 [方法名稱]
原因：___
前提假設需要確認：[列出假設]
```

---

## Step 4：Python 程式碼生成

```python
# === 自動生成的統計分析程式碼 ===
# 研究問題：[填入]
# 統計方法：[填入]
# 生成日期：[YYYY-MM-DD]

import pandas as pd
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt
import seaborn as sns

# 設定中文字體（台灣環境）
plt.rcParams["font.family"] = "Noto Sans CJK TC"
plt.rcParams["axes.unicode_minus"] = False

# Step 1: 載入資料
df = pd.read_csv("your_data.csv", encoding="utf-8-sig")
print("資料基本資訊：")
print(df.describe())
print(f"\n樣本數：{len(df)}")

# Step 2: 資料清理
# 檢查缺失值
print("\n缺失值統計：")
print(df.isnull().sum())

# Step 3: 統計假設驗證
# 正態性檢定（Shapiro-Wilk）
from scipy.stats import shapiro
stat, p_value = shapiro(df["[依變數欄位名]"])
print(f"\n正態性檢定：W={stat:.4f}, p={p_value:.4f}")
if p_value > 0.05:
    print("→ 資料符合正態分布假設（p > 0.05）")
else:
    print("→ 資料不符合正態分布（考慮使用非參數方法）")

# Step 4: 執行 [選定的統計方法]
# [根據方法生成對應程式碼]

# Step 5: 效果量（Effect Size）計算
# [Cohen's d / eta-squared / Cramer's V 等]

# Step 6: 視覺化
# [對應圖表生成程式碼]

# Step 7: 結果摘要
print("\n===== 統計分析結果摘要 =====")
# [格式化輸出]
```

### R 版本（若使用者選擇 R）
```r
# === 自動生成的 R 統計分析程式碼 ===
library(tidyverse)
library(rstatix)
library(ggpubr)

# [對應 R 程式碼]
```

---

## Step 5：結果學術解讀

```
統計結果學術寫作格式：

【t 檢定】
「獨立樣本 t 檢定結果顯示，實驗組（M = [均值], SD = [標準差]）
與對照組（M = [均值], SD = [標準差]）在[依變數]上達到顯著差異，
t([自由度]) = [t 值], p = [p 值], d = [效果量]。
此結果支持研究假設 H₁，表示[實質意義解讀]。」

【ANOVA】
「單因子變異數分析結果顯示，三組在[依變數]上的差異達統計顯著，
F([組間df], [組內df]) = [F 值], p < .001, η² = [效果量]。
事後比較（Tukey HSD）顯示，[群組 A] 顯著高於 [群組 B]（p = [p值]）。」

【對應分析（CA）】
「對應分析呈現[變數1]與[變數2]的關聯結構，
第一維度解釋了 [X]% 的慣性，第二維度解釋了 [Y]%。
在二維散點圖中，[詞語/類別1] 與 [詞語/類別2] 呈現正向關聯，
位於圖形的[象限]方向。」
```

---

## Step 6：統計誤用警示

```
⚠️ 常見統計誤用清單（執行前確認）：

1. 小樣本濫用 t-test：
   → 樣本數 < 30 且非正態，改用非參數檢定

2. 多重比較未校正：
   → 若同時做多個 t-test，p 值膨脹問題
   → 應用 Bonferroni 校正或改用 ANOVA

3. 只看 p 值，忽略效果量：
   → p 值只告訴你有沒有差異，效果量告訴你差多少

4. 相關 ≠ 因果：
   → r = 0.8 不代表 A 導致 B

5. 李克特量表的爭議：
   → 嚴格來說是順序尺度，不能用平均數
   → 實務上 5 點以上常視為等距尺度使用，
     需在方法論章節說明立場
```

---

## 降級方案（無 Bash 執行時）
- 生成程式碼供使用者在本機執行
- 提供 SPSS 操作步驟說明
- 提供 Excel 基礎統計計算方法

---

## Module A：EDA 探索性資料分析

### 適用時機
使用者上傳資料檔案（CSV/Excel/SPSS .sav/R .rds）並想「先了解資料長什麼樣子」，
或需要在正式統計分析前進行資料品質確認。

### A1：資料格式偵測與讀取

```python
# 自動偵測並讀取常見台灣學術資料格式
import pandas as pd
import numpy as np

# CSV / Excel
df = pd.read_csv("data.csv", encoding="utf-8-sig")          # 台灣常見 UTF-8 BOM
# df = pd.read_excel("data.xlsx", sheet_name=0)

# SPSS .sav（需 pyreadstat）
# import pyreadstat
# df, meta = pyreadstat.read_sav("data.sav")
# print("SPSS 變數標籤：", meta.column_labels)

print(f"資料維度：{df.shape[0]} 筆 × {df.shape[1]} 個變項")
print(df.dtypes)
```

### A2：一鍵 EDA 報告（ydata-profiling）

```python
# 安裝：pip install ydata-profiling
from ydata_profiling import ProfileReport

profile = ProfileReport(df, title="研究資料 EDA 報告", explorative=True)
profile.to_file("EDA_report.html")
print("✅ EDA 報告已生成：EDA_report.html")
```

報告自動包含：
- 各變項分布直方圖 / 類別計數長條圖
- 缺失值矩陣（Missing value matrix）
- 相關係數熱圖（Pearson / Spearman）
- 異常值偵測（IQR 方法）
- 高相關警告（r > 0.9）

### A3：手動 EDA 核心程式碼

```python
# --- 描述統計 ---
print(df.describe(include="all").round(3))

# --- 缺失值檢查 ---
missing = df.isnull().sum()
missing_pct = (missing / len(df) * 100).round(1)
missing_df = pd.DataFrame({"缺失數": missing, "缺失率(%)": missing_pct})
print(missing_df[missing_df["缺失數"] > 0])

# --- 相關熱圖 ---
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 8))
corr = df.select_dtypes(include=[np.number]).corr()
sns.heatmap(corr, annot=True, fmt=".2f", cmap="coolwarm",
            center=0, square=True, linewidths=0.5)
plt.title("相關係數矩陣", fontsize=14)
plt.tight_layout()
plt.savefig("correlation_heatmap.png", dpi=300)
plt.show()

# --- 異常值（Box plot）---
numeric_cols = df.select_dtypes(include=[np.number]).columns
fig, axes = plt.subplots(1, len(numeric_cols), figsize=(4 * len(numeric_cols), 5))
for i, col in enumerate(numeric_cols):
    axes[i].boxplot(df[col].dropna())
    axes[i].set_title(col)
plt.tight_layout()
plt.savefig("outlier_boxplots.png", dpi=300)
```

### A4：EDA 結論 → 後續統計建議

EDA 完成後，AI 自動輸出：
```
EDA 摘要結論：
・資料筆數：N = {n}；變項數：{k}
・缺失值：{變項名} 缺失 {n}（{%}），建議：{刪除/插補/說明}
・分布情況：{連續變項} 呈{正態/偏態}；建議後續做 Shapiro-Wilk 確認
・高相關警告：{變項A} 與 {變項B}（r = .XX）→ 小心共線性問題
・異常值：{變項} 有 {n} 個潛在異常值（IQR × 1.5 標準）

建議後續統計方法：[連結回 Step 3 決策樹]
```

---

## Module B：網絡分析（Network Analysis）

### 適用時機
- 文獻引用網絡（誰引誰、哪些文獻形成叢集）
- 社會網路分析（問卷中的人際互動、教師合作關係）
- 共現分析（關鍵詞共現、訪談文本詞語共現）

### B1：基礎網絡建立

```python
# 安裝：pip install networkx matplotlib
import networkx as nx
import matplotlib.pyplot as plt
import pandas as pd

# 從邊列表（edge list）建立網絡
# 假設 CSV 格式：source, target, weight
edges_df = pd.read_csv("edges.csv")
G = nx.from_pandas_edgelist(edges_df, source="source",
                              target="target", edge_attr="weight")

print(f"節點數：{G.number_of_nodes()}")
print(f"邊數：{G.number_of_edges()}")
print(f"網絡密度：{nx.density(G):.4f}")
```

### B2：網絡中心性指標計算

```python
# 計算中心性指標（最常用的三種）
degree_cent = nx.degree_centrality(G)
betweenness_cent = nx.betweenness_centrality(G)
closeness_cent = nx.closeness_centrality(G)

# 整理為 DataFrame
centrality_df = pd.DataFrame({
    "Degree Centrality": degree_cent,
    "Betweenness Centrality": betweenness_cent,
    "Closeness Centrality": closeness_cent
}).round(4).sort_values("Degree Centrality", ascending=False)

print("前 10 個關鍵節點：")
print(centrality_df.head(10))

# 偵測社群（Louvain 演算法，需 python-louvain）
# import community as community_louvain
# partition = community_louvain.best_partition(G)
```

### B3：網絡視覺化

```python
plt.figure(figsize=(12, 10))

# 節點大小根據 degree 設定
node_size = [G.degree(n) * 100 for n in G.nodes()]
# 色彩根據社群分群（若有）
pos = nx.spring_layout(G, seed=42, k=0.5)

nx.draw_networkx(G, pos,
                 node_size=node_size,
                 node_color="steelblue",
                 edge_color="gray",
                 alpha=0.8,
                 with_labels=True,
                 font_size=9)

plt.title("節點關係網絡圖", fontsize=14)
plt.axis("off")
plt.tight_layout()
plt.savefig("network_graph.png", dpi=300, bbox_inches="tight")
plt.show()
```

### B4：學術解讀模板

```
網絡分析結果顯示，本研究中共識別出 {N} 個節點與 {E} 條邊，
網絡密度為 {density}，屬於{稀疏/中等/密集}網絡。

度中心性（Degree Centrality）最高的節點為「{節點名}」（DC = {值}），
代表其在網絡中與最多其他節點直接連結。
中介中心性（Betweenness Centrality）最高的為「{節點名}」（BC = {值}），
顯示該節點在網絡資訊流通中扮演關鍵橋接角色。

社群偵測結果識別出 {k} 個次群體，分別以{主題/時期/角色}為核心。
```

### B5：匯出 Gephi 格式（進階視覺化）

```python
# 匯出 GEXF 格式，可在 Gephi 中開啟進行精細視覺化
nx.write_gexf(G, "network_for_gephi.gexf")
print("✅ 已匯出 network_for_gephi.gexf，可在 Gephi 開啟")
```

---

## Module C：時間序列分析（Time Series）

### 適用時機
- 縱貫研究（longitudinal study）的趨勢分析
- 前後測設計的時序效果
- 政策介入前後的變化追蹤
- 自然情境下的時間序列觀察資料

### C1：時間序列資料準備

```python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# 讀取資料（確認時間欄位格式）
df = pd.read_csv("timeseries_data.csv", parse_dates=["date"])
df = df.set_index("date").sort_index()

print(df.head())
print(f"時間範圍：{df.index.min()} 至 {df.index.max()}")
print(f"觀察點數：{len(df)}")
```

### C2：趨勢與季節性分解

```python
# 分解時間序列：趨勢 + 季節性 + 殘差
result = seasonal_decompose(df["value"], model="additive", period=12)

fig, axes = plt.subplots(4, 1, figsize=(12, 10))
result.observed.plot(ax=axes[0], title="原始資料")
result.trend.plot(ax=axes[1], title="趨勢（Trend）")
result.seasonal.plot(ax=axes[2], title="季節性（Seasonality）")
result.resid.plot(ax=axes[3], title="殘差（Residual）")
plt.tight_layout()
plt.savefig("timeseries_decomposition.png", dpi=300)
plt.show()
```

### C3：前後測設計的時序分析

```python
# 適用：有明確介入時間點的前後測設計
import numpy as np
from scipy import stats

intervention_date = "2023-09-01"
pre = df[df.index < intervention_date]["score"]
post = df[df.index >= intervention_date]["score"]

# 效果量（Cohen's d）
def cohen_d(group1, group2):
    n1, n2 = len(group1), len(group2)
    pooled_std = np.sqrt(((n1-1)*group1.std()**2 + (n2-1)*group2.std()**2) / (n1+n2-2))
    return (group2.mean() - group1.mean()) / pooled_std

t_stat, p_value = stats.ttest_ind(pre, post)
d = cohen_d(pre, post)

print(f"前測：M = {pre.mean():.2f}, SD = {pre.std():.2f}, N = {len(pre)}")
print(f"後測：M = {post.mean():.2f}, SD = {post.std():.2f}, N = {len(post)}")
print(f"t({len(pre)+len(post)-2}) = {t_stat:.3f}, p = {p_value:.3f}, d = {d:.3f}")
```

### C4：ARIMA 預測（選用）

```python
# 適用：需要預測未來趨勢時
from statsmodels.tsa.arima.model import ARIMA

model = ARIMA(df["value"], order=(1, 1, 1))
result = model.fit()
print(result.summary())

# 預測未來 12 個時間點
forecast = result.forecast(steps=12)
print(f"\n未來 12 期預測：\n{forecast}")
```

### C5：學術解讀模板

```
時間序列分析結果顯示，{研究期間}內{結果變項}呈現{上升/下降/平穩/波動}趨勢。

【趨勢描述】：季節性分解顯示，整體趨勢在{時間點}後出現{轉折}，
可能與{外部事件/政策介入/節慶效應}有關。

【前後測比較】（若適用）：
介入前（M = {值}, SD = {值}）與介入後（M = {值}, SD = {值}）
經獨立樣本 t 檢定，t({df}) = {值}, p = {值}, Cohen's d = {值}，
達{顯著/未達顯著}差異，效果量屬{小/中/大}。

【研究限制】：本研究為觀察性縱貫設計，時序相關不代表因果關係；
需排除歷史效應（history effect）與成熟效應（maturation effect）的可能干擾。
```
