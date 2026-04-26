---
name: tw-research-viz
description: >
  將學術研究資料（文獻關係、研究架構、概念框架、資料流程、統計結果）
  視覺化為精確的學術圖表，優先調用 Excalidraw MCP 生成手繪風格圖，
  或生成可嵌入論文的 SVG/PNG 圖表。
  當使用者提及「研究架構圖」「概念框架」「文獻關係圖」「理論模型」
  「研究流程圖」「資料視覺化」「畫圖」「論文圖表」「研究地圖」
  「系統性文獻回顧」「SLR 流程」「PRISMA」「期刊投稿圖」
  「色盲友善」「300 DPI」「向量圖」「Nature 格式」「SSCI 格式」時觸發。
  適用情境：碩博士論文、期刊論文、研討會論文、研究計畫書、國際期刊投稿。
version: 2.0.0
author: 奇老師・數位敘事力社群
allowed-tools: "Bash, Read, Write, WebSearch"
disable-model-invocation: true
---

# 學術論文資料視覺化工具 v2.0

## 哲學定位
「一張好的學術圖表，能讓審稿人在 30 秒內理解你的研究邏輯。」

---

## Step 0：讀取必要文件

1. `references/academic_viz_types.md` — 學術圖表類型與規範
2. `references/apa7_figure_format.md` — APA/APA 7th 圖表格式要求
3. `../../tw_edu_guided_collection.md` — 引導式收集框架

若 Excalidraw MCP 可用：
→ 優先使用 Excalidraw 生成可編輯圖表
→ 調用 `Excalidraw:create_view` 工具

---


**概念對齊協議（必要前置步驟）：**
`../../tw_edu_concept_alignment.md`
→ 在執行任何工作前，先完成概念對齊確認卡。


## Step 1：引導式資訊收集（三輪）

### 第一輪（核心，必問）
```
Q1: 「要視覺化什麼類型的內容？
    A. 研究架構 / 概念框架
    B. 文獻關係圖（如：文獻引用網絡、主題分群）
    C. 研究流程圖（含 PRISMA/SLR 流程）
    D. 理論模型（變數關係、路徑圖）
    E. 統計數據視覺化（長條圖/折線/雷達圖）
    F. 心智圖 / 主題概念地圖
    G. 其他（請描述）」

Q2: 「請提供核心資料：
    ・研究題目 / 主題
    ・要呈現的主要元素（節點/變數/步驟等）
    ・元素之間的關係（A→B、A←→B、A包含B）」
```

### 第二輪（細節，選填）
```
Q3: 「圖的最終用途？
    A. 嵌入 Word/PDF 論文（需高解析度）
    B. 學術報告/簡報（.pptx）
    C. 研討會海報
    D. 線上分享 / 可編輯版本」

Q4: 「格式 Preset（投稿/提交目標）？
    A. 臺灣學位論文格式（標楷體、Times New Roman）
    B. APA 7th 社會科學期刊（SSCI，單欄較寬）
    C. 國際理工期刊（Nature/Science 雙欄，sans-serif 字體）
    D. 無特殊要求（使用預設學術格式）」

Q5: 「色彩模式？
    A. 標準學術配色（現有深藍主色系）
    B. 色盲友善模式（Okabe-Ito 8色系，推薦投稿期刊時使用）
    C. 黑白灰階（適合單色列印、部分老期刊要求）」
```

### 確認摘要
```
✅ 圖表類型：{類型}
📐 元素數量：{N 個節點/步驟}
🎨 風格：{黑白/有限色/全彩}
🔧 生成工具：{Excalidraw MCP / SVG / matplotlib}
📄 輸出格式：{svg/png/pptx 嵌入}
```

---

## Step 2：圖表類型規範

### A. 研究架構圖 / 概念框架
```
適用：展示研究的整體架構、各構念之間的關係

Excalidraw 元素設計：
  ・矩形（圓角）= 構念/變數
  ・箭頭 = 影響方向（實線 = 假設正向影響）
  ・虛線箭頭 = 調節/中介關係
  ・雙向箭頭 = 相關但無因果方向

分層建議：
  ├── 前置變數（左側或上方）
  ├── 核心構念（中央）
  └── 結果變數（右側或下方）

標記規範（APA 7th）：
  H1, H2... = 假設編號（在箭頭旁標注）
  β = 標準化路徑係數（若有統計結果）
```

### B. PRISMA 系統性文獻回顧流程圖
```
標準 4 階段結構（PRISMA 2020）：

識別（Identification）
  │ 資料庫搜尋（N = ）
  │ 移除重複（n = ）
  ↓
篩選（Screening）
  │ 標題/摘要篩選（n = 排除 / 原因）
  ↓
資格審查（Eligibility）
  │ 全文審查（n = 排除 / 原因清單）
  ↓
納入（Included）
  └── 最終納入文獻（n = ）

Excalidraw 樣式：
  ・識別 = 藍色框
  ・篩選 = 黃色框
  ・資格 = 橘色框
  ・納入 = 綠色框
  ・排除原因 = 側邊虛線框
```

### C. 文獻關係圖 / 主題群聚
```
適用：展示不同文獻/學者之間的引用關係或主題分群

元素設計：
  ・圓形節點 = 重要文獻/學者
  ・節點大小 = 被引用次數（越大越重要）
  ・線條粗細 = 關係強度
  ・色彩分群 = 研究主題/時期

若文獻數量 > 20：建議使用 Python 腳本生成圖表（matplotlib + networkx）
```

### D. 路徑模型圖（SEM / 迴歸）
```
元素設計：
  ・橢圓 = 潛在變數（latent variable）
  ・矩形 = 觀測變數（observed variable）
  ・單向箭頭 = 因果路徑（標注路徑係數）
  ・雙向彎曲箭頭 = 相關/共變
  ・小圓圈 e = 誤差項

標注規範：
  顯著路徑：β = .XX, p < .001（標注 ***）
  非顯著路徑：β = .XX, ns（虛線箭頭）
```

### E. 統計數據視覺化
```
圖表選擇指南：
  比較多組 → 長條圖（bar chart）
  趨勢/時序 → 折線圖（line chart）
  比例/組成 → 圓餅圖/環形圖
  多維度比較 → 雷達圖（spider chart）
  相關關係 → 散佈圖（scatter plot）
  分佈情況 → 箱形圖（box plot）

生成工具：
  → Python matplotlib / seaborn 腳本
  → 或呼叫 Three.js 3D Viewer（3D 資料呈現）
```

---

## Step 3：Excalidraw MCP 調用規範

### 優先使用 Excalidraw MCP 的情境
```
✅ 研究架構圖、概念框架
✅ PRISMA 流程圖
✅ 文獻關係圖（< 20 節點）
✅ 心智圖
✅ 任何需要「可編輯」的圖表
```

### Excalidraw 調用前的準備
```
Step 1：讀取 Excalidraw read_me
  → 呼叫 Excalidraw:read_me 取得元素格式規範

Step 2：設計元素結構（JSON）
  元素類型：rectangle / ellipse / arrow / text / diamond
  元素屬性：x, y, width, height, backgroundColor, strokeColor, label

Step 3：呼叫 create_view
  Excalidraw:create_view(elements: JSON 陣列字串)
```

### 色彩系統（依 Q5 選擇套用）

**A. 標準學術配色（預設）**
```python
ACADEMIC_PALETTE = {
    "primary":    "#1A5276",  # 深藍：主要節點
    "secondary":  "#2471A3",  # 中藍：次要節點
    "accent":     "#D4AC0D",  # 金色：強調節點
    "boundary":   "#1E8449",  # 綠色：邊界節點
    "background": "#EBF5FB",  # 淺藍：背景
    "text":       "#1C2A35",  # 深色：文字
}
```

**B. Okabe-Ito 色盲友善 8 色系（推薦投稿使用）**
```python
OKABE_ITO = [
    "#E69F00",  # 橙色
    "#56B4E9",  # 天藍
    "#009E73",  # 藍綠
    "#F0E442",  # 黃色
    "#0072B2",  # 深藍
    "#D55E00",  # 深橙
    "#CC79A7",  # 紫粉
    "#000000",  # 黑色（第8色備用）
]
# 適用情境：投稿 Nature/Science/PLOS ONE 等國際期刊時強烈推薦
# 原理：對三種最常見色盲類型（紅綠色盲、藍黃色盲、全色盲）均可辨識
```

**C. 灰階模式（單色列印）**
```python
GRAYSCALE = ["#000000", "#404040", "#808080", "#B0B0B0", "#D8D8D8", "#FFFFFF"]
# 使用時搭配不同形狀/線條樣式（實線/虛線/點線）作為主要區分手段
```

### 學術圖表元素設計原則
```
顏色系統（依上方選擇套用）：
  主要節點：ACADEMIC_PALETTE["primary"] 或 OKABE_ITO[4]（深藍）
  次要節點：ACADEMIC_PALETTE["secondary"] 或 OKABE_ITO[1]（天藍）
  強調節點：ACADEMIC_PALETTE["accent"] 或 OKABE_ITO[0]（橙色）
  邊界節點：ACADEMIC_PALETTE["boundary"] 或 OKABE_ITO[2]（藍綠）
  背景色：#EBF5FB（淺藍，避免純白）
  文字：#1C2A35（深色）

字型：
  節點標題：14px 粗體
  路徑標注：12px 細體
  圖注：12px 斜體

連接器：
  因果關係：實線箭頭
  相關關係：雙向箭頭
  包含關係：虛線框
  調節關係：虛線箭頭
```

---

## Step 4：Python 輔助腳本（無 Excalidraw MCP 時）

```bash
# 生成 PRISMA 流程圖
python scripts/generate_prisma.py \
  --identified [N] \
  --duplicates [n] \
  --screened [n] \
  --eligible [n] \
  --included [n] \
  --output "/mnt/user-data/outputs/PRISMA流程圖.png"

# 生成研究架構圖
python scripts/generate_framework.py \
  --nodes "[節點1:類型,節點2:類型,...]" \
  --edges "[節點1->節點2:標籤,...]" \
  --output "/mnt/user-data/outputs/研究架構圖.svg"
```

---

## Step 5：APA 7th 圖表格式規範

```
圖注格式（Figure caption）：

Figure X
[圖表標題（首字大寫，不加句點）]
注意。[說明文字，如有]。[資料來源，如改編自其他研究]

範例：
Figure 1
Conceptual Framework of Teacher AI Competency and Student Learning Outcomes
注意。本架構整合 Davis (1989) 科技接受模型與 Bandura (1977) 自我效能理論。

圖表編號規則：
  ・全論文連續編號（Figure 1, 2, 3...）
  ・圖注置於圖的正下方
  ・圖標題與論文正文字體一致（通常為 Times New Roman 12pt）
```

---

## Step 6：MCP 整合對照表

| 功能 | Claude Code | Claude.ai | Codex | Antigravity |
|------|------------|-----------|-------|------------|
| Excalidraw 互動圖 | ✅ MCP | ✅ MCP（若連接） | ✅（需設定 config.toml）| ✅（MCP Hub）|
| 統計圖（matplotlib） | ✅ Bash | ✅ Bash | ✅ | ✅ |
| 匯出為 .png/.svg | ✅ | ✅ | ✅ | ✅ |
| Three.js 3D 視覺化 | ✅ MCP | ✅ MCP（若連接） | ✅（需設定 config.toml）| ✅（MCP Hub）|

### Excalidraw MCP 未連接時的降級方案
1. 使用 Python `matplotlib` 生成 `.png` 靜態圖表
2. 生成 SVG 代碼（可貼入 Inkscape 或 Figma 繼續編輯）
3. 生成 Mermaid 語法（flowchart/graph）輸出供用戶複製
4. 提供 draw.io XML（可匯入 diagrams.net 編輯）

---

## Step 7：期刊格式 Preset 規範

依 Q4 選擇的格式，套用以下規範：

### A. 臺灣學位論文格式
```
字型：
  中文標題/標注：標楷體 12pt（粗體用於標題）
  英文/數字：Times New Roman 12pt
圖表尺寸：單欄全寬（文字區寬度，通常約 14-16 cm）
解析度：≥ 300 DPI（印刷用）
格式：PNG 或 PDF（嵌入 Word）
圖注語言：中英對照，Figure 1 / 圖1
```

### B. APA 7th 社會科學期刊（SSCI）
```
字型：
  圖表內文字：Sans-serif（如 Arial、Calibri）8-12pt
  圖注：Times New Roman 12pt（與正文一致）
圖表尺寸：單欄（8.5 cm）或全寬（17.8 cm）
解析度：≥ 300 DPI（點陣圖）/ 向量格式優先（EPS/PDF）
格式：EPS > PDF > TIFF > PNG（JPEG 禁用）
色彩：強烈建議使用 Okabe-Ito 色盲友善色系
注意：圖注（caption）在圖的下方，標題僅首字大寫
```

### C. 國際理工期刊（Nature/Science 系）
```
字型：
  圖表內文字：Helvetica 或 Arial（sans-serif），最小 6pt
  單欄圖時，字體縮放後仍需 ≥ 6pt（列印版）
圖表尺寸：
  單欄：8.9 cm（89 mm）
  雙欄：18.3 cm（183 mm）
  最大高度：24.7 cm（247 mm）
解析度：線條藝術圖 ≥ 1,000 DPI；混合圖 ≥ 600 DPI；照片 ≥ 300 DPI
格式：PDF（向量）> EPS > TIFF；JPEG 僅限照片
色彩：CMYK 色彩空間（非 RGB，提交出版時注意）
       強制使用色盲友善色系（Nature 期刊編輯政策要求）
```

---

## Step 8：Publication-quality 輸出標準

### Python 高品質圖表匯出模板

```python
import matplotlib.pyplot as plt
import matplotlib as mpl

# === 依格式 Preset 設定參數 ===

# --- Preset A：臺灣學位論文 ---
# plt.rcParams.update({
#     "figure.dpi": 300,
#     "savefig.dpi": 300,
#     "font.family": ["Noto Sans CJK TC", "Times New Roman"],
#     "font.size": 12,
#     "axes.labelsize": 12,
#     "xtick.labelsize": 10,
#     "ytick.labelsize": 10,
# })

# --- Preset B：APA 7th / SSCI（推薦） ---
plt.rcParams.update({
    "figure.dpi": 300,
    "savefig.dpi": 300,
    "font.family": "Arial",
    "font.size": 10,
    "axes.labelsize": 10,
    "axes.spines.top": False,
    "axes.spines.right": False,
    "figure.figsize": (8.5 / 2.54, 6 / 2.54),  # 8.5 cm 寬，單位轉換
})

# --- Preset C：Nature/Science 雙欄 ---
# plt.rcParams.update({
#     "figure.dpi": 600,
#     "savefig.dpi": 600,
#     "font.family": "Helvetica",
#     "font.size": 8,
#     "axes.labelsize": 8,
#     "xtick.labelsize": 7,
#     "ytick.labelsize": 7,
#     "figure.figsize": (18.3 / 2.54, 8 / 2.54),  # 183 mm 寬
# })

# === 色盲友善色系（Okabe-Ito）===
OKABE_ITO = ["#E69F00", "#56B4E9", "#009E73", "#F0E442",
             "#0072B2", "#D55E00", "#CC79A7", "#000000"]

# --- 實際繪圖 ---
fig, ax = plt.subplots()
# [在此加入你的繪圖程式碼，使用 OKABE_ITO 作為色彩清單]

# === 匯出（向量優先）===
fig.tight_layout()
fig.savefig("figure.pdf", bbox_inches="tight")   # 向量（最優先）
fig.savefig("figure.svg", bbox_inches="tight")   # 向量（可在 Inkscape 編輯）
fig.savefig("figure.png", dpi=300, bbox_inches="tight")  # 點陣備份
print("✅ 圖表已匯出：figure.pdf / figure.svg / figure.png")
```

### 字型最小值核查

```python
# 確認圖表縮放至目標尺寸後，文字仍 ≥ 6pt
def check_font_size(fig, target_width_cm, min_pt=6):
    current_width_inches = fig.get_figwidth()
    target_width_inches = target_width_cm / 2.54
    scale_factor = target_width_inches / current_width_inches
    current_fontsize = plt.rcParams["font.size"]
    effective_fontsize = current_fontsize * scale_factor
    if effective_fontsize < min_pt:
        print(f"⚠️ 警告：縮放後字型大小約 {effective_fontsize:.1f}pt，低於最小值 {min_pt}pt")
        print(f"   建議：將 font.size 提高至 {current_fontsize / scale_factor * min_pt / effective_fontsize:.0f}pt")
    else:
        print(f"✅ 字型大小符合要求（縮放後約 {effective_fontsize:.1f}pt）")
```

---

## Step 9：品質確認清單（v2.0）

- [ ] 圖表邏輯清晰，看圖能理解研究核心
- [ ] 已選擇適當格式 Preset（臺灣論文 / APA / Nature）
- [ ] 字型符合 Preset 規範（字體名稱、最小 pt 值）
- [ ] 色彩選擇已考慮色盲友善性（建議 Okabe-Ito）
- [ ] 顏色不超過 3-4 種（印刷版可在灰階下辨識）
- [ ] 箭頭方向明確、無歧義
- [ ] 有 APA 7th 或目標期刊格式的圖注
- [ ] 向量格式已匯出（PDF / EPS / SVG）
- [ ] 解析度符合要求（印刷 ≥ 300 DPI；Nature 線稿 ≥ 1,000 DPI）
- [ ] 圖表尺寸符合目標欄寬（單欄 / 雙欄 cm）
- [ ] Excalidraw 版本可供後續編輯（若 MCP 可用）
