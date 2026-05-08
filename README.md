# tw-research-skills — 學術研究 Claude Skills 套組

> **臺灣學術研究者 / 碩博生專用 AI 研究輔助套組**  
> 整合文獻管理、假說生成、統計分析（EDA / 網絡 / 時間序列）、引用格式校對、學術辯證、**投稿全流程支援（v2.5 新增）**，嚴謹對應臺灣學術規範，並支援國際期刊投稿模式。

[![Skills](https://img.shields.io/badge/Skills-15-red)](https://github.com/FW1201/tw-research-skills)
[![Version](https://img.shields.io/badge/Version-2.5-green)](https://github.com/FW1201/tw-research-skills)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 📦 套組概覽

本套組包含 **15 個 Skills**（v2.0 原有 10 個 + v2.5 新增 5 個），面向臺灣大學研究生、學術研究者，涵蓋：
- 假說生成與研究方法設計引導（競爭假說框架）
- 系統性文獻探討（多資料庫搜尋策略）
- 量化統計分析（Python/R 程式碼生成）+ EDA / 網絡分析 / 時間序列
- APA 7th / MLA 9th / 臺灣學位論文格式引用校對
- 學術辯證 + ScholarEval 8 維度系統評估
- 國科會 / NSF / NIH 研究計畫書撰寫
- Publication-quality 圖表（色盲友善、期刊格式 preset）
- **🆕 v2.5 投稿全流程支援**：期刊選擇顧問 / 投稿前檢查清單 / 審稿回覆撰寫 / 研究倫理自評 / 學位論文規範校對

> **相關套組**：[tw-edu-skills（教師）](https://github.com/FW1201/tw-edu-skills) ｜ [tw-stu-skills（學生）](https://github.com/FW1201/tw-stu-skills)

---

## 🛠 Skills 清單

### 研究規劃
| Skill | 版本 | 功能說明 |
|-------|------|---------|
| `tw-research-hypothesis-generator` | v1.0 🆕 | 假說生成：從研究缺口產生 3-5 個競爭假說→品質評估矩陣（可測試性/可偽證性/簡約性）→研究方法設計建議 |
| `tw-research-proposal-diamond` | v1.0 | 雙菱形研究計畫書：發散式問題探索→聚焦研究設計→國科會計畫格式輸出 |
| `tw-research-grant-writer` | v1.0 🆕 | 研究計畫書撰寫：國科會五段引導→三位評審視角模擬→引用驗證整合；支援切換 NSF / NIH 國際模式 |
| `tw-research-lit-review` | v1.0 | 系統性文獻探討：Boolean 搜尋策略→多資料庫（Web of Science / Scopus / CNKI / NDLTD）→主題聚類→研究缺口識別→綜述草稿 |

### 資料分析
| Skill | 版本 | 功能說明 |
|-------|------|---------|
| `tw-research-stat-consultant` | v2.0 ⬆️ | 量化統計顧問：上傳資料→選擇統計方法→Python/R 程式碼→效果量→學術解讀；**新增** EDA 自動分析（ydata-profiling）、網絡分析（networkx）、時間序列分析（statsmodels） |
| `tw-research-viz` | v2.0 ⬆️ | 研究視覺化：數據圖表、概念架構圖、研究流程圖；**新增** 期刊格式 Preset（台灣論文/APA/Nature）、Okabe-Ito 色盲友善色系、300 DPI 向量輸出標準 |

### 引用管理
| Skill | 版本 | 功能說明 |
|-------|------|---------|
| `tw-research-citation-checker` | v1.0 | 文獻引用查核：確認文獻真實存在（DOI 驗證）、作者/年份/標題比對 |
| `tw-research-citation-proofer` | v1.0 | 引用格式校對：逐條檢查 APA 7th / MLA 9th / 台灣學位論文格式，列出錯誤並給出正確版本 |

### 學術寫作
| Skill | 版本 | 功能說明 |
|-------|------|---------|
| `tw-research-dialectics` | v2.0 ⬆️ | 學術辯證（Toulmin 模型）+ **新增評估模式**：ScholarEval 8 維度 × 5 分量表系統評估論文草稿 |

### 套組設定
| Skill | 版本 | 功能說明 |
|-------|------|---------|
| `tw-research-synchronizer` | v1.1 ⬆️ | 個人化套組設定助手；**新增** 假說生成取向、計畫書目標機構、圖表國際模式三項設定 |

---

## 🆕 v2.5 新增：投稿全流程支援（2026-05）

> 方案 C：本地化投稿流程優化（對標四大競品後優先實施）
> 競品參考來源：academic-paper-skills / agent-research-skills / research-writing-skill / claude-prism

### 投稿前流程

```
論文完成
  ↓
tw-research-citation-proofer（現有）— 引用格式校對
  ↓
tw-research-submission-checklist（新）— 投稿前 18 項檢查
  ↓
tw-research-journal-selector（新）— 期刊選擇 + 投稿信
  ↓
tw-research-ethics-reviewer（新）— 研究倫理自評（如適用）
  ↓
正式投稿
  ↓
tw-research-rebuttal-writer（新）— 審稿回覆撰寫
  ↓
tw-research-taiwan-regulation（新）— 學位論文繳交規範（碩博生）
```

### v2.5 新增 Skills 清單

| Skill | 版本 | 功能說明 | 參考來源 |
|-------|------|---------|--------|
| `tw-research-journal-selector` | v1.0 🆕 | 期刊選擇顧問：TSSCI / SSCI / SCOPUS 三大資料庫對應 + Top 5 期刊建議 + 投稿信模板生成 | agent-research-skills (novelty-assessment) + academic-paper-skills |
| `tw-research-submission-checklist` | v1.0 🆕 | 投稿前全面檢查：18 項清單（格式/內容/倫理/De-AI 品質）+ 投稿準備度評分 + 修正建議 | research-writing-skill (Red Flags system) |
| `tw-research-rebuttal-writer` | v1.0 🆕 | 審稿回覆撰寫：R1/R2/R3 全輪次 + 意見自動分類（TYPE A-E）+ Point-by-Point 回應表 + 修訂追蹤 | agent-research-skills (rebuttal-writing) |
| `tw-research-ethics-reviewer` | v1.0 🆕 | 研究倫理自評：IRB 風險矩陣（人體/動物/敏感資料）+ 知情同意書範本 + IRB 申請準備指引 | 台灣人體研究法 + Belmont Report |
| `tw-research-taiwan-regulation` | v1.0 🆕 | 學位論文格式校對：各校封面格式 + 國家圖書館繳交規範 + 合規報告 + 電子檔製作指引 | 國家圖書館 ETD + 學位授予法 |

---

## 🚀 安裝方式

### Claude Code（推薦）

Claude Code 是本套組設計的**主要平台**，所有功能完整支援，包含程式碼執行。

```bash
# 安裝全套組（15 個 Skills，含 v2.5 新增）
npx skills add FW1201/tw-research-skills --all -a claude-code

# 安裝單一 Skill
npx skills add FW1201/tw-research-skills tw-research-stat-consultant -a claude-code

# 確認安裝
npx skills list -a claude-code

# 更新套組
npx skills update -a claude-code
```

> **注意**：`tw-research-stat-consultant` 需要 Claude Code 的 `Bash` 工具執行 Python/R 統計程式碼。請確認 Python 3.8+ 已安裝，並安裝必要套件：
> ```bash
> pip install pandas scipy statsmodels numpy matplotlib seaborn prince
> pip install ydata-profiling networkx pyreadstat  # v2.0 新增：EDA / 網絡分析 / SPSS 格式支援
> ```

### Codex CLI

Codex 原生支援 MCP，透過 `~/.codex/config.toml` 設定 Connectors。

**Skills 安裝路徑**：
```
<your-project>/.agents/skills/<skill-name>/SKILL.md
```

```bash
git clone https://github.com/FW1201/tw-research-skills.git
mkdir -p <your-project>/.agents/skills
cp -r tw-research-skills/tw-research-*/ <your-project>/.agents/skills/
```

**MCP 設定**（`~/.codex/config.toml`）：
```toml
[mcp_servers.consensus]
url = "https://mcp.consensus.app/mcp"
headers = { Authorization = "Bearer ${CONSENSUS_TOKEN}" }

[mcp_servers.notion]
command = "npx"
args = ["-y", "@notionhq/notion-mcp-server"]
env = { NOTION_API_KEY = "${NOTION_API_KEY}" }
```

> 詳細設定請參閱 [docs/non-claude-setup.md](docs/non-claude-setup.md)

### Antigravity（Google AI IDE）

Antigravity 完整支援 MCP + **Jupyter Notebook 原生整合**，是研究類 Skills 的最佳非 Claude 平台。

**Skills 安裝路徑**：
```
~/.gemini/antigravity/skills/<skill-name>/SKILL.md   ← 全域層
<project>/.agent/skills/<skill-name>/SKILL.md         ← 專案層
```

```bash
mkdir -p ~/.gemini/antigravity/skills
cp -r tw-research-skills/tw-research-*/ ~/.gemini/antigravity/skills/
```

**特有優勢**：`tw-research-stat-consultant` 可在 Jupyter Notebook 中直接執行 Python/R 統計分析，即時查看圖表輸出。

**MCP 設定**：透過 MCP Server Hub 介面直接啟用 Consensus、Notion、Google Drive Connector。

> 詳細設定請參閱 [docs/non-claude-setup.md](docs/non-claude-setup.md)

---

## 🔌 MCP Connectors 整合

| Connector | 應用 Skills | 功能 |
|-----------|------------|------|
| Notion | `tw-research-lit-review`, `tw-research-synchronizer` | 文獻卡片存入知識庫、研究節點管理 |
| GitHub | `tw-research-stat-consultant` | 統計程式碼版本控制、資料存儲 |
| Hugging Face | `tw-research-lit-review` | 語料庫查詢、語言模型探索 |
| Google Drive | 所有 Skills | 論文草稿讀取 / 儲存 |
| Gamma | `tw-research-proposal-diamond` | 研究計畫書簡報生成 |

---

## 📊 tw-research-stat-consultant 支援的分析方法（v2.0）

| 類別 | 方法 |
|------|------|
| EDA 自動分析 🆕 | ydata-profiling 報告、缺失值矩陣、相關熱圖、異常值偵測 |
| 差異檢定 | t-test（獨立/相依）、單因子/多因子 ANOVA、Kruskal-Wallis |
| 相關分析 | Pearson r、Spearman ρ、Kendall τ |
| 迴歸分析 | 線性迴歸、邏輯迴歸、多層次迴歸 |
| 多變量 | 主成分分析（PCA）、對應分析（CA）、集群分析 |
| 網絡分析 🆕 | 引用網路、社會網路、共現分析（networkx + gephi 輸出） |
| 時間序列 🆕 | 季節性分解、ARIMA、前後測時序比較（statsmodels） |
| 語料庫 | 頻率統計、關鍵字分析、搭配詞分析（MI 值、t-score） |

---

## 📚 學術規範整合

本套組參考以下規範設計：
- APA 7th Edition
- MLA 9th Edition
- 臺灣學位論文格式（NTNU / 國科會標準）
- 臺灣學術倫理教育資源中心（TAERC）規範
- CASLAR、語言學相關期刊投稿規範

---

## 💡 第一次使用建議

1. **執行 `tw-research-synchronizer`**（輸入「我要設定學術研究套組」）  
   → 填寫研究領域、方法論、目標期刊，系統自動客製化所有 Skills
2. **嘗試 `tw-research-lit-review`**（輸入「幫我做文獻探討」）
3. **使用 `tw-research-stat-consultant`** 前確認 Python 環境就緒

---

## ⚠️ 重要聲明

### 鼓勵共創與客製化

本套組以開放精神釋出，**歡迎所有人 Fork、客製化、延伸開發**。  
唯使用或衍生本套組時，請務必遵守以下 Citation 規範：

```
吳奇（Kevin Wu）. (2026). tw-research-skills: 學術研究 Claude Skills 套組 [Software].
數位敘事力期刊. https://github.com/FW1201/tw-research-skills
```

> 本套組的設計理念深受 **曾慶良老師**（GitHub：[@ChatGPT3a01](https://github.com/ChatGPT3a01)）啟發，  
> 在此致上誠摯謝意。

如需提交貢獻或客製化 Skills，請參閱 [CONTRIBUTING.md](CONTRIBUTING.md)。

---

## 👨‍💻 作者

**奇老師・數位敘事力期刊**  
GitHub：[@FW1201](https://github.com/FW1201)  
研究領域：語料庫語言學、漢語語法、AI×教育

📘 [Facebook](https://www.facebook.com/Journal.of.Digital.Narrative) ｜
▶️ [YouTube](https://www.youtube.com/@Journal_of_Digital_Narrative) ｜
📸 [Instagram](https://www.instagram.com/journal_of_digital_narrative/)

---

*本套組採 MIT 授權。歡迎學術社群貢獻新 Skill 或更新統計方法支援。使用時請標註來源。*
