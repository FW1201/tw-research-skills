# 貢獻指南 — tw-research-skills

感謝你有興趣為 **tw-research-skills（學術研究 Skills 套組）** 貢獻或提交客製化作品！  
本指南說明如何製作符合規格的 Skill，以及如何將成果分享給數位敘事力期刊。

---

## 🌱 貢獻方式

| 方式 | 說明 |
|------|------|
| **提交新 Skill** | 製作 Skill 後郵寄給維護者審核 |
| **回報問題** | 在 GitHub Issues 描述 Bug 或改善建議 |
| **改善現有 Skill** | Fork → 修改 → 提交 Pull Request |
| **客製化自用** | Fork 自行維護，只需在 README 標註來源 |

---

## 🛠 如何製作一個 Skill

### 方法一：使用 Claude Skills Creator（推薦）

**Claude Skills Creator** 是 Anthropic 官方的 Skill 製作工具，在 Claude Code 中操作。

**步驟：**

1. 開啟 Claude Code（`claude` 指令或桌面應用程式）
2. 輸入以下提示詞啟動製作流程：

   ```
   請幫我製作一個新的 Claude Skill，名稱是 tw-research-[你的功能名稱]，
   功能是[描述你想要的學術研究輔助功能]，目標使用者是[碩士生/博士生/研究員]。
   ```

3. Claude 會引導你完成：
   - SKILL.md 的 frontmatter（name、description、version、allowed-tools）
   - Skill 的執行步驟與學術規範整合
   - 概念對齊確認卡（Concept Alignment Protocol）
   - references/ 參考文件（引用格式、統計方法、期刊規範等）

4. 完成後，儲存至本機資料夾，資料夾名稱即為 Skill ID（如 `tw-research-my-skill/`）

**SKILL.md 最低規格：**

```yaml
---
name: tw-research-[your-skill-name]
description: >
  一句話描述功能 + 觸發詞清單
  分類：學術研究（tw-research-*）
version: 1.0.0
author: 你的名稱・數位敘事力期刊
allowed-tools: "Bash, Read, Write, WebSearch, Notion"
disable-model-invocation: true
---

# Skill 標題

[執行步驟...]
```

> 📌 **學術研究 Skill 規格重點**：  
> 所有涉及統計分析的 Skill 需在 `allowed-tools` 加入 `Bash`，  
> 並在 SKILL.md 中說明需要的 Python/R 套件版本。

---

### 方法二：使用 Codex Skills Creator

**Codex Skills Creator** 是 OpenAI Codex 環境中的 Skill 建構工具。

**步驟：**

1. 在 Codex CLI 環境中輸入：

   ```
   /create-skill tw-research-[你的功能名稱]
   ```

2. 依照提示填寫 Skill 的描述、觸發詞、執行邏輯

3. Codex 生成的 SKILL.md 需手動補充以下欄位：
   - `disable-model-invocation: true`
   - 概念對齊確認卡
   - 臺灣學術倫理規範（TAERC）相關說明
   - 引用格式規範（APA 7th / 台灣格式）

> ⚠️ **注意**：Codex 環境的 `Bash` 工具執行能力依沙箱設定而定，若你的 Skill 需要執行 Python/R 統計程式碼，建議在 Claude Code 環境中完整測試後再提交。

---

## 📋 Skill 品質檢核清單

提交前請確認：

- [ ] **命名規範**：`tw-research-[功能名]`（全小寫、連字號分隔）
- [ ] **SKILL.md 完整**：包含所有必要 frontmatter 欄位
- [ ] **概念對齊確認卡**：Skill 執行前有對齊機制
- [ ] **學術倫理聲明**：Skill 說明 AI 輸出僅供參考，研究者需獨立判斷
- [ ] **引用規範對應**：說明支援哪些引用格式（APA / MLA / 台灣格式）
- [ ] **觸發詞清單**：description 中列出至少 5 個中文觸發詞
- [ ] **版本號**：遵循 SemVer（major.minor.patch）
- [ ] **作者欄位**：填寫姓名 + 數位敘事力期刊
- [ ] **references/ 目錄**：包含相關學術規範說明文件（建議）

---

## 📧 如何提交給維護者

製作完成後，請將 Skill 資料夾（包含 SKILL.md 及所有子目錄）壓縮後寄至：

**📮 kevinwu@gtrainerdemo.jdn2023.com**

郵件主旨格式：
```
[Skill 貢獻] tw-research-[你的 Skill 名稱] — [你的姓名]
```

郵件內容請包含：
1. Skill 名稱與功能簡介（100字以內）
2. 目標使用情境（研究方法論、學科領域、適用階段）
3. 製作工具（Claude Skills Creator / Codex Skills Creator / 手動編寫）
4. 你的 GitHub 帳號（若有，將列入貢獻者名單）
5. 壓縮附件：`tw-research-[功能名].zip`

收到後，維護者將於 **7 個工作天**內回覆審核結果。

---

## 📜 Citation 規範

Fork 或衍生本套組時，請在你的作品中標註：

```
基於 吳奇（Kevin Wu）. (2025). tw-research-skills: 學術研究 Claude Skills 套組 [Software].
數位敘事力期刊. https://github.com/FW1201/tw-research-skills
受 曾慶良老師（GitHub: @ChatGPT3a01）啟發。
```

---

## 🤝 行為準則

- 尊重所有使用者與貢獻者
- 提交內容須符合學術倫理規範，不得設計為代替研究者進行學術判斷
- 涉及人類受試者研究的 Skill，需在說明中提醒使用者遵守 IRB 規範

---

## 📬 聯絡資訊

**數位敘事力期刊**

📮 kevinwu@gtrainerdemo.jdn2023.com  
📘 [Facebook](https://www.facebook.com/Journal.of.Digital.Narrative)  
▶️ [YouTube](https://www.youtube.com/@Journal_of_Digital_Narrative)  
📸 [Instagram](https://www.instagram.com/journal_of_digital_narrative/)  
💻 GitHub：[@FW1201](https://github.com/FW1201)
