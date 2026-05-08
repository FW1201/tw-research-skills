---
name: tw-research-structure-advisor
description: >
  學術論文章節結構設計顧問，根據論文類型（實驗報告/理論論文/評論論文/案例研究）
  生成標準章節骨架、每章大綱要點，以及各章節寫作重點說明。
  支援碩士論文（五章）、期刊文章、研討會論文三種格式。
  與 tw-research-proposal-diamond 互補：proposal 生成研究計畫，
  structure-advisor 展開為完整論文章節框架。
  當使用者提及「論文架構」「章節規劃」「不知道怎麼分章」「目次設計」
  「論文骨架」「章節大綱」「怎麼分章節」「thesis structure」時觸發。
  分類：學術研究（tw-research-*）
  參考來源：research-writing-skill (writing-chapters)
version: 1.0.0
author: 奇老師・數位敘事力社群
allowed-tools: "Bash, Read, Write"
---

# 學術論文章節結構設計顧問 v1.0

## 核心哲學
「**好的論文結構，是讀者無需努力就能跟上你的思路。**
章節架構不是形式要求，是讀者的認知地圖。
本工具幫你在動筆前，先建好這張地圖。」

> 參考設計：research-writing-skill/writing-chapters（章節組織邏輯）
>
> 與 tw-research-proposal-diamond 的分工：
> - **proposal-diamond**：研究計畫書（說服委員批准研究）
> - **structure-advisor**：論文章節框架（指導研究後的撰寫）

---

## Step 0：讀取參考資源

1. `references/thesis_structure_templates.md` — 各類論文結構模板
2. `references/chapter_writing_guides.md` — 章節寫作要點指引

---

## Step 1：概念對齊確認卡

```
╔══════════════ 章節結構設計顧問啟動 ══════════════╗
📌 任務：為您的論文設計最適合的章節架構
🎯 目標：完整章節骨架 + 每章大綱 + 撰寫建議

請提供：
1. 研究主題（一句話）
2. 論文類型（見下方選項）
3. 研究方法（量化/質性/混合）
╚══════════════════════════════════════════════════╝
```

---

## Step 2：論文類型與格式決策樹

```
Q1：「論文輸出格式是？
    A. 碩士/博士學位論文（台灣五章式）
    B. 國際期刊文章（IMRaD 格式）
    C. 台灣中文期刊論文（五段或四段）
    D. 研討會論文（4-8頁簡短版）
    E. 文獻評析 / 系統性回顧
    F. 不確定，幫我建議」

Q2：「研究類型是？
    A. 實證研究（有數據分析）
      A1. 實驗設計（有控制組）
      A2. 調查研究（問卷/訪談）
      A3. 語料庫研究
      A4. 縱貫研究（時間序列）
    B. 理論建構（提出新框架）
    C. 文獻評析（系統性文獻回顧）
    D. 案例研究（深度個案）
    E. 混合方法」

Q3：「研究對象/領域？
    A. 語言學 / 應用語言學 / 華語教學
    B. 教育學 / 課程與教學
    C. 心理學 / 認知科學
    D. 社會學 / 傳播學
    E. 管理學 / 商學
    F. 其他：___」
```

---

## Step 3：章節架構生成

### 架構 A：台灣碩士論文標準五章式

```
適用：實證研究類碩博士論文（最常見）

第一章 緒論（Introduction）
建議頁數：10-20 頁
主要段落：
  1.1 研究背景與動機
      → 建立研究重要性，說明社會/學術需求
  1.2 研究目的
      → 清楚宣示研究要達成什麼
  1.3 研究問題（Research Questions）
      → 列出 2-4 個具體可回答的問題
  1.4 研究範圍與限制
      → 說明研究邊界，誠實說明限制
  1.5 名詞界定
      → 本研究對關鍵術語的操作性定義
  1.6 論文組織
      → 說明各章內容（一段即可）

第二章 文獻探討（Literature Review）
建議頁數：25-40 頁
主要段落：
  2.1 [理論框架1]（依研究主題決定）
  2.2 [理論框架2]
  2.3 [先行研究回顧]
  2.4 [研究缺口識別]
      → ⚠️ 重要：這一節為第一章研究目的的理據

第三章 研究方法（Methodology）
建議頁數：15-25 頁
主要段落：
  3.1 研究設計
      → 說明量化/質性/混合方法及選擇理由
  3.2 研究對象/樣本
      → 人數、選樣標準、基本資料描述
  3.3 研究工具/語料
      → 問卷/訪談大綱/語料庫說明
      → 工具信效度說明
  3.4 資料收集程序
      → 施測/訪談/蒐集過程
  3.5 資料分析方式
      → 使用何種統計/質性分析方法

第四章 研究結果（Results / Findings）
建議頁數：20-35 頁
主要段落：
  4.1 [對應研究問題1的結果]
  4.2 [對應研究問題2的結果]
  4.3 [對應研究問題3的結果]
  ⚠️  重要：每個研究問題都要有對應的結果段落

第五章 討論與結論（Discussion and Conclusion）
建議頁數：15-25 頁
主要段落：
  5.1 研究結果摘要
  5.2 研究發現討論
      → 連結文獻探討，說明發現的意義
  5.3 學術貢獻
      → 本研究對理論/實務的貢獻
  5.4 研究限制
      → 誠實說明，但不要削弱研究價值
  5.5 未來研究建議
      → 具體可操作的方向
  5.6 結語
      → 一段有力的收尾

附錄（Appendices）
  附錄一：研究工具（問卷/訪談大綱）
  附錄二：IRB 核准文件（如適用）
  附錄三：其他補充材料
```

---

### 架構 B：國際期刊 IMRaD 格式

```
適用：英文國際期刊投稿（理工科/社科均適用）

Abstract（250字以內，含關鍵詞）
  結構：Background → Objective → Method → Results → Conclusion

1. Introduction（引言，800-1200字）
   → Background → Gap → Objective → Contribution宣示

2. Literature Review / Theoretical Framework（文獻，依期刊而異）
   → 有些期刊整合到 Introduction，有些獨立成章

3. Methodology（方法，800-1500字）
   → Design → Participants → Instruments → Procedure → Analysis

4. Results（結果，依數據量調整）
   → 客觀呈現，不詮釋（詮釋留到 Discussion）

5. Discussion（討論，1000-2000字）
   → 與文獻連結 → 解釋預期外結果 → 理論意涵

6. Conclusion（結論，300-600字）
   → 貢獻 → 限制 → 未來方向

References（APA 7th / 依期刊格式）
```

---

### 架構 C：文獻評析 / 系統性回顧

```
1. Introduction
   → 評析範圍界定 + 重要性說明

2. Search Strategy and Inclusion Criteria
   → 資料庫選擇 + 關鍵詞 + 納排標準 + PRISMA 流程圖

3. Thematic Analysis / Synthesis
   → 依主題分組（不依時間順序）
   → 每組：研究趨勢 + 方法對比 + 矛盾發現

4. Research Gaps
   → 系統性識別未探索的面向

5. Conclusion and Future Directions

附錄：文獻篩選清單
```

---

### 架構 D：案例研究

```
1. Introduction + Case Rationale
   → 為何選擇此案例？代表性說明

2. Theoretical Framework
   → 用何種理論視角分析案例

3. Case Description
   → 案例背景、脈絡、歷史

4. Case Analysis
   → 依理論框架進行系統性分析

5. Discussion + Cross-Case Comparison（若多案例）

6. Conclusion + Implications
```

---

## Step 4：章節內部架構建議

每章的標準內部組織：

```
每章建議遵循「PEEL 段落結構」：

P (Point)：主題句——本段核心論點
E (Evidence)：支持證據——文獻引用/數據
E (Elaboration)：深化解釋——說明證據如何支持論點
L (Link)：連結段落——與下一段或本章主題的連接

章節之間的連接：
□ 每章結尾：一段「本章小結」（3-5句）
□ 下一章開頭：回扣上一章，引入新方向
□ 全文邏輯線：Introduction的問題 → Literature的缺口 →
              Method的設計 → Results的發現 → Discussion的意義
```

---

## Step 5：客製化大綱輸出

根據使用者提供的研究主題，生成量身定做的章節大綱：

```
╔════════════════════════════════════════════════╗
📐 [論文題目]
   論文類型：[類型]  方法：[方法]
╠════════════════════════════════════════════════╣

第一章 緒論
  1.1 [具體標題，含研究主題關鍵詞]
  1.2 [具體標題]
  ...（依研究內容客製化）

[各章具體小節大綱]
...

預估總頁數：[X-X] 頁（依一般碩士論文標準）

⚠️  特別注意事項（依研究類型）：
  [針對此研究的特殊結構建議]
╚════════════════════════════════════════════════╝
```

---

## 降級方案

若使用者研究主題不夠明確：
- 先使用 tw-research-proposal-diamond 確認研究設計
- 或使用 tw-research-hypothesis-generator 釐清研究方向
- 再回到 structure-advisor 生成章節架構
