---
name: tw-research-journal-selector
description: >
  台灣學術期刊選擇顧問，協助研究者根據論文主題、領域與目標等級，
  從 TSSCI、SSCI、SCI、SCOPUS、THCI 等資料庫中推薦最適合的投稿期刊。
  提供 Top 5 期刊建議、接受率統計、版面費（APC）、投稿信模板，
  以及 Impact Factor / CiteScore 參考數值。
  當使用者提及「要投哪個期刊」「期刊選擇」「TSSCI 哪個比較好投」
  「impact factor 查詢」「期刊建議」「投稿目標」時觸發。
  分類：學術研究（tw-research-*）
  參考來源：agent-research-skills (novelty-assessment) + academic-paper-skills (Platform Analysis)
version: 1.0.0
author: 奇老師・數位敘事力社群
allowed-tools: "Bash, Read, Write, WebSearch"
---

# 台灣學術期刊選擇顧問 v1.0

## 核心哲學
「**選對期刊，事半功倍。**
投到不合適的期刊，不論論文品質多好都可能石沉大海。
本工具幫你用 5 分鐘找到最適合的投稿目標。」

> 參考設計：agent-research-skills/novelty-assessment（平台分析邏輯）、
> academic-paper-skills/Platform Analysis（期刊適配評估框架）

---

## Step 0：讀取期刊資料庫

讀取以下參考資源：
1. `references/tssci_journal_list.md` — TSSCI 期刊清單（人文社科）
2. `references/sci_ssci_thci_overview.md` — SCI/SSCI/THCI 資料庫說明
3. `references/cover_letter_templates.md` — 投稿信模板庫

---

## Step 1：概念對齊確認卡

```
╔══════════════ 期刊選擇顧問啟動 ══════════════╗
📌 任務：為您的論文推薦最適合的投稿期刊
🎯 目標：Top 5 期刊建議 + 投稿信模板
⏱️  預計時間：5-10 分鐘完成選擇
⚠️  重要：本工具提供建議，最終請查閱期刊官網確認最新資訊
╚═══════════════════════════════════════════════╝
```

---

## Step 2：研究資訊收集

依序詢問以下問題（可一次提供）：

```
Q1：「請提供論文摘要（100-300 字即可）」
    → 用於判斷研究主題、方法、貢獻

Q2：「研究領域是？（可複選）
    A. 語言學 / 應用語言學
    B. 教育學 / 課程與教學
    C. 心理學 / 認知科學
    D. 社會學 / 傳播學
    E. 管理學 / 商學
    F. 資訊科學 / 人機互動
    G. 文學 / 文化研究
    H. 其他：___」

Q3：「目標發表等級是？
    A. TSSCI（台灣社會科學引文索引，台灣頂級）
    B. SSCI（社會科學引文索引，國際頂級）
    C. SCI / SCIE（科學引文索引）
    D. SCOPUS 收錄（國際中等）
    E. THCI（台灣人文學核心期刊）
    F. 台灣一般學術期刊（非索引）
    G. 不限，越容易越好」

Q4：「語言偏好？
    A. 中文優先（台灣讀者受眾）
    B. 英文優先（國際影響力）
    C. 均可」

Q5：「是否有版面費（APC）預算限制？
    A. 無預算限制
    B. 台幣 30,000 以下
    C. 免費期刊優先
    D. 開放取用（Open Access）優先」
```

---

## Step 3：期刊推薦分析

根據收集的資訊，進行以下分析：

### 3.1 主題匹配分析
```
分析論文關鍵詞 → 匹配期刊收稿範圍
重點評估：
□ 研究方法契合度（量化/質性/混合）
□ 研究對象契合度（台灣/亞洲/全球）
□ 理論框架契合度
□ 近期刊登相似主題的頻率
```

### 3.2 期刊評估矩陣

針對每本候選期刊評估：

| 評估維度 | 說明 |
|--------|------|
| **主題契合度** | 與您的研究主題相符程度（1-5 分） |
| **投稿難度** | 接受率與審稿嚴格度估計（低/中/高） |
| **影響因子** | IF 或 CiteScore（若有） |
| **審稿週期** | 平均初審時間（週） |
| **版面費** | APC 金額（若為 OA） |
| **語言要求** | 中文/英文/雙語 |
| **台灣認可度** | 教育部/國科會認可等級 |

---

## Step 4：Top 5 期刊推薦輸出

```
╔════════════════════════════════════════════════════╗
🎯 您的論文期刊推薦清單（Top 5）
論文主題：[摘要關鍵詞]
研究領域：[領域]
目標等級：[等級]
╠════════════════════════════════════════════════════╣

🥇 第 1 推薦：[期刊全名（中/英）]
   資料庫收錄：[TSSCI/SSCI/SCOPUS 等]
   Impact Factor / CiteScore：[數值]（[年份]）
   接受率：約 [X]%（估計）
   審稿週期：約 [X] 週
   版面費：[金額或免費]
   投稿語言：[中/英/雙語]
   官方網站：[URL]
   ✨ 推薦理由：[具體說明為何適合此論文]
   ⚠️  注意事項：[投稿前需注意的事項]

🥈 第 2 推薦：[期刊全名]
   [同上格式]

🥉 第 3 推薦：[期刊全名]
   [同上格式]

4️⃣  第 4 推薦：[期刊全名]
   [同上格式]

5️⃣  第 5 推薦：[期刊全名]
   [同上格式]

╠════════════════════════════════════════════════════╣
💡 選擇建議：
  • 最佳策略：先投第 1 推薦，若被拒再依序嘗試
  • 時間緊迫：可同時關注第 2、3 推薦的特刊徵稿
  • 升等需求：建議以 TSSCI/SSCI 為主要目標
╚════════════════════════════════════════════════════╝
```

---

## Step 5：投稿信（Cover Letter）模板生成

提供客製化投稿信：

```
[期刊名稱] 投稿信模板

Dear Editor,

I am submitting the manuscript titled "[論文標題]" for consideration 
for publication in [期刊名稱].

This paper [一句話說明研究內容與方法]。Our main contributions are:
1. [貢獻一]
2. [貢獻二]
3. [貢獻三]

We confirm that this manuscript has not been published elsewhere and is 
not under consideration by any other journal. All authors have approved 
the manuscript and agree with its submission to [期刊名稱].

[若為台灣研究，可補充：This study is particularly relevant to [期刊]'s 
readership as it addresses [台灣/亞洲脈絡].]

We look forward to hearing from you.

Sincerely,
[作者姓名]
[職稱]
[服務機構]
[電子郵件]
[日期]
```

---

## Step 6：TSSCI 重要期刊速查（台灣社會科學）

常用 TSSCI 期刊參考（依領域分類）：

### 語言學 / 應用語言學
- 《語言暨語言學》（Language and Linguistics，中央研究院）
- 《台灣語文研究》
- 《華語文教學研究》（THCI）

### 教育學
- 《教育研究集刊》
- 《課程與教學》
- 《教育科學研究期刊》
- 《當代教育研究》

### 心理學
- 《中華心理學刊》
- 《中華心理衛生學刊》

### 管理學
- 《管理學報》
- 《組織與管理》

> ⚠️ 注意：TSSCI 清單每年更新，投稿前請至科技部網站確認最新名單

---

## Step 7：國際期刊快速建議

若目標為 SSCI/SCI：

```
請告知：
1. 研究使用語言（中文資料 vs. 英文資料）
2. 主要理論框架（建構主義/行為主義/認知語言學等）
3. 目標讀者群（亞洲/歐美/全球）

→ 將提供 3-5 本國際期刊建議
```

---

## 降級方案

若無法透過 WebSearch 取得即時資料：
- 提供基於已知資料庫的建議（2024 年資料）
- 標示「⚠️ 資料截止 2024 年，投稿前請至官網查詢最新資訊」
- 建議用戶至 Journal Citation Reports（JCR）或 SCImago 查詢最新 IF
