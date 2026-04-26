# tw-research-skills — Claude Code 專案設定
# 學術研究 Skills Repo
# 最後更新：2026-04-26

---

## Repo 定位

此 repo 包含 **11 個學術研究 Skills**，目標用戶為台灣碩博生與學術研究者。

---

## 工具許可

### 允許（無需確認）
- `WebSearch`：搜尋學術文獻、期刊資料
- `Read`：讀取 SKILL.md 和 references/ 文件
- `Bash`：執行 Python 統計分析腳本

### 需確認
- `Write`：寫入任何檔案
- `Gmail`：草稿確認後才允許

---

## 輸出規範

### 論文文件格式
- 字型：標楷體 12pt（中文）、Times New Roman 12pt（英文）
- 行距：1.5 倍
- 頁邊距：上 3cm、下 2cm、左右各 3cm
- 引用格式：APA 7th Edition（預設）

### 設計皮膚
- 研究類：**Academic Clean**（白底、深藍配色）
- 統計圖：Okabe-Ito 色盲友善色系

---

## Skill 開發規範

### Frontmatter 必要欄位
```yaml
name: tw-research-<name>
description: >
  [功能描述，包含觸發詞]
version: x.x.x
author: 奇老師・數位敘事力社群
allowed-tools: "<必要工具清單>"
```

### 統計分析標準
- Python：`pandas`, `scipy`, `statsmodels`, `matplotlib`
- R：`tidyverse`, `lavaan`（SEM），`lme4`（多層次）
- 圖表解析度：≥ 300 DPI

---

## 測試

```bash
# 安裝到 Claude Code 測試
npx skills add . --all -a claude-code
```
