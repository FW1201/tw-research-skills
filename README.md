# tw-research-skills — 學術研究 Claude Skills 套組

> **臺灣學術研究者 / 碩博生專用 AI 研究輔助套組**  
> 整合文獻管理、統計分析、引用格式校對、學術辯證，嚴謹對應臺灣學術規範。

[![Skills](https://img.shields.io/badge/Skills-8-red)](https://github.com/FW1201/tw-research-skills)
[![Version](https://img.shields.io/badge/Version-1.0-green)](https://github.com/FW1201/tw-research-skills)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 📦 套組概覽

本套組包含 **8 個 Skills**，面向臺灣大學研究生、學術研究者，涵蓋：
- 系統性文獻探討（多資料庫搜尋策略）
- 量化統計分析（Python/R 程式碼生成與執行）
- APA 7th / MLA 9th / 臺灣學位論文格式引用校對
- 學術辯證與論點強化（Toulmin 論證模型）

> **相關套組**：[tw-edu-skills（教師）](https://github.com/FW1201/tw-edu-skills) ｜ [tw-stu-skills（學生）](https://github.com/FW1201/tw-stu-skills)

---

## 🛠 Skills 清單

### 研究規劃
| Skill | 功能說明 |
|-------|---------|
| `tw-research-proposal-diamond` | 雙菱形研究計畫書：發散式問題探索→聚焦研究設計→國科會計畫格式輸出 |
| `tw-research-lit-review` | 系統性文獻探討：Boolean 搜尋策略→多資料庫（Web of Science / Scopus / CNKI / NDLTD）→主題聚類→研究缺口識別→綜述草稿 |

### 資料分析
| Skill | 功能說明 |
|-------|---------|
| `tw-research-stat-consultant` | 量化統計顧問：上傳資料→選擇統計方法→執行 Python/R 檢定→效果量報告→學術解讀文字 |
| `tw-research-viz` | 研究視覺化：數據圖表、概念架構圖、研究流程圖生成 |

### 引用管理
| Skill | 功能說明 |
|-------|---------|
| `tw-research-citation-checker` | 文獻引用查核：確認文獻真實存在（DOI 驗證）、作者/年份/標題比對 |
| `tw-research-citation-proofer` | 引用格式校對：逐條檢查 APA 7th / MLA 9th / 台灣學位論文格式，列出錯誤並給出正確版本 |

### 學術寫作
| Skill | 功能說明 |
|-------|---------|
| `tw-research-dialectics` | 學術內容辯證：輸入論點→AI 提出反駁（四類辯證）→往返辯論→生成正式反駁段落（Toulmin 模型） |

### 套組設定
| Skill | 功能說明 |
|-------|---------|
| `tw-research-synchronizer` | 個人化套組設定助手，根據研究領域/方法論/目標期刊/指導教授風格客製化所有 tw-research-* Skills |

---

## 🚀 安裝方式

### Claude Code（推薦）

Claude Code 是本套組設計的**主要平台**，所有功能完整支援，包含程式碼執行。

```bash
# 安裝全套組（8 個 Skills）
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
> pip install pandas scipy statsmodels numpy matplotlib prince
> ```

### Codex CLI

```bash
npx skills add FW1201/tw-research-skills --all -a codex
```

> ⚠️ **Codex 限制**：
> - `tw-research-stat-consultant` 的 **Bash 程式碼執行不可用**，僅能生成 Python/R 程式碼供複製執行
> - MCP Connectors（Notion、GitHub、Hugging Face）**不可用**，文獻卡片需手動存檔
> - `WebSearch`（用於 DOI 驗證、文獻搜尋）依連線狀態而定

### Antigravity

```bash
npx skills add FW1201/tw-research-skills --all -a antigravity
```

> ⚠️ **Antigravity 限制**：
> - `Bash` 程式碼執行需確認沙箱環境已啟用
> - MCP Connectors 支援程度依個人環境設定而定
> - Hugging Face 語料庫查詢需 HF API Token 設定

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

## 📊 tw-research-stat-consultant 支援的統計方法

| 類別 | 方法 |
|------|------|
| 差異檢定 | t-test（獨立/相依）、單因子/多因子 ANOVA、Kruskal-Wallis |
| 相關分析 | Pearson r、Spearman ρ、Kendall τ |
| 迴歸分析 | 線性迴歸、邏輯迴歸、多層次迴歸 |
| 多變量 | 主成分分析（PCA）、對應分析（CA）、集群分析 |
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
吳奇（Kevin Wu）. (2025). tw-research-skills: 學術研究 Claude Skills 套組 [Software].
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
