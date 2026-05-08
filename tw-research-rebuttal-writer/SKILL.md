---
name: tw-research-rebuttal-writer
description: >
  學術論文審稿意見回覆撰寫工具，協助研究者撰寫專業的 Rebuttal Letter
  與逐點回應表（Point-by-Point Response）。
  支援 R1（第一輪修訂）/ R2（第二輪修訂）/ R3（第三輪修訂），
  自動分類審稿意見（Major/Minor/Reject 類型），
  提供回應策略建議與修訂追蹤格式。
  當使用者提及「審稿意見回覆」「rebuttal」「回覆審稿人」
  「response to reviewers」「R&R 修訂」「revise and resubmit」時觸發。
  分類：學術研究（tw-research-*）
  參考來源：agent-research-skills (rebuttal-writing)
version: 1.0.0
author: 奇老師・數位敘事力社群
allowed-tools: "Bash, Read, Write"
---

# 審稿意見回覆撰寫工具 v1.0

## 核心哲學
「**審稿人不是你的敵人，是幫你改善論文的夥伴。**
一封好的 Rebuttal Letter，不僅回應問題，更展現你對研究的深度掌握。
語氣：感謝 + 專業 + 堅定（有理由時）。」

> 參考設計：agent-research-skills/rebuttal-writing（意見分類與自動審稿機制）
> 本工具針對台灣學術生態優化：繁體中文期刊 + 國際英文期刊雙軌支援

---

## Step 0：讀取參考資源

1. `references/rebuttal_templates.md` — 回覆信模板庫（中/英）
2. `references/reviewer_comment_classifier.md` — 審稿意見分類指南
3. `references/revision_tracking_format.md` — 修訂追蹤格式

---

## Step 1：概念對齊確認卡

```
╔══════════════ 審稿回覆工具啟動 ══════════════╗
📌 任務：撰寫專業的審稿意見回覆信
🎯 目標：Rebuttal Letter + Point-by-Point 回應表

請提供：
1. 期刊名稱 + 決定類型（Major/Minor Revision / Reject & Resubmit）
2. 審稿人意見（可貼上全文）
3. 編輯信件（Editor's Letter，若有）
4. 修訂說明（你做了哪些修改，若已知道）
╚════════════════════════════════════════════╝
```

---

## Step 2：決定類型確認

```
Q1：「收到的決定是？
    A. Major Revision（大幅修訂，最常見）
    B. Minor Revision（小幅修訂）
    C. Reject & Resubmit（拒絕但歡迎重投）
    D. Accept with Minor Revision（接受，小修）
    E. 不確定，幫我判斷」

Q2：「這是第幾輪修訂？
    A. R1（第一輪，初次審稿後）
    B. R2（第二輪）
    C. R3 以上」

Q3：「有幾位審稿人？
    Reviewer 1 / Reviewer 2 / Reviewer 3 / 編輯意見」

Q4：「偏好的語言？
    A. 全英文
    B. 全中文
    C. 按期刊語言決定」
```

---

## Step 3：審稿意見分類

將每一條審稿意見自動分類：

```
意見類型分類：
🔴 TYPE A — 核心方法論質疑（需實質修改）
   例：「樣本數不足」「缺乏對照組」「統計方法有誤」
   回應策略：承認 → 補充分析/說明 → 呈現新結果

🟡 TYPE B — 文獻補充要求（可快速回應）
   例：「未引用 X 學者的研究」「缺少最新文獻」
   回應策略：感謝 → 已補充 + 說明如何整合

🔵 TYPE C — 表達/格式修正（最簡單）
   例：「第 3 頁第 2 行不清楚」「圖表標題需修正」
   回應策略：感謝 → 已修正 → 說明修改位置

⚪ TYPE D — 觀點不同（可禮貌堅持）
   例：「認為研究框架有誤」「質疑理論選擇」
   回應策略：感謝 + 尊重 → 提供更多理據 → 說明不修改的原因

🟠 TYPE E — 拒絕意見（Reject 類）
   例：「研究貢獻不足」「方法根本性錯誤」
   回應策略：需決定重投 vs. 換期刊
```

---

## Step 4：Rebuttal Letter 模板

### 英文版（國際期刊）

```
[Date]

Dear Dr. [Editor Name] and Reviewers,

Thank you for your careful review of our manuscript titled "[論文標題]" 
(Manuscript ID: [編號]). We are grateful for the constructive comments 
and suggestions that have helped us significantly improve the quality 
of our work.

We have carefully addressed all the concerns raised by the reviewers. 
Below, we provide a detailed point-by-point response to each comment. 
All changes in the revised manuscript are highlighted in [yellow/blue] 
for easy identification.

We hope that our revisions adequately address the reviewers' concerns 
and that the revised manuscript will be considered suitable for 
publication in [期刊名稱].

Sincerely,
[作者姓名]
[通訊作者職稱]
[服務機構]
[電子郵件]

---
RESPONSE TO REVIEWERS
Manuscript: [論文標題]
Date of Revision: [日期]
```

### 中文版（台灣中文期刊）

```
[日期]

親愛的編輯委員 [姓名] 教授，以及各位審稿委員，您好：

感謝您與審稿委員們對拙作「[論文標題]」（稿件編號：[編號]）
的仔細審閱與寶貴意見。審稿委員們的建議對本研究品質的提升
具有重要貢獻，作者謹此致謝。

本文已按照各位審稿委員的意見進行逐一修訂。
以下提供詳細的逐點回應，修改處已以[螢光黃]標示，
敬請參閱。

希望修訂後的稿件能符合 [期刊名稱] 的刊登標準。
敬請不吝賜教。

敬上
[作者姓名]
[職稱]
[服務機構]
[電子郵件]
```

---

## Step 5：Point-by-Point 回應表

### 標準回應格式

```
════════════════════════════════════════════════
REVIEWER [#] COMMENTS AND RESPONSES
════════════════════════════════════════════════

Comment [#]-[序號]（TYPE [分類]）：
[貼上原始審稿意見]

Response：
Thank you for this insightful comment. [選擇對應開場]

[根據 TYPE 選擇策略：]

▶ TYPE A（方法論質疑）：
We acknowledge that [問題確認]。In response, we have 
[具體修改說明]。The results are presented in [位置]（Page X, 
Line Y）。This finding [新結論說明]。

▶ TYPE B（文獻補充）：
Thank you for suggesting this important reference. We have 
added citations to [文獻清單] in the revised manuscript 
（Page X, Line Y）. Specifically, [如何整合到論文中]。

▶ TYPE C（表達修正）：
We apologize for the unclear expression. We have revised 
this sentence/paragraph as follows:
  Original: "[原文]"
  Revised: "[修正後]"（Page X, Line Y）

▶ TYPE D（觀點不同）：
We appreciate this thoughtful perspective. While we 
respectfully maintain our original position, we 
acknowledge [承認部分合理性]。We have added a discussion 
of this alternative view in [位置]（Page X, Lines Y-Z）
to clarify our reasoning: [說明你的理由]。

Revision location: Page [X], Line [Y]-[Z]
```

---

## Step 6：中文期刊回應格式

```
════════════════════════════════════════════
審稿委員 [#] 意見與回覆
════════════════════════════════════════════

意見 [#]-[序號]（[TYPE 分類]）：
[貼上原始審稿意見]

回覆：
感謝委員提出此重要建議。[選擇對應開場]

[修改說明]

修訂位置：第 [X] 頁，第 [Y] 行
```

---

## Step 7：修訂追蹤摘要表

```
╔════════════════════════════════════════════════╗
修訂追蹤摘要（Revision Summary）
╠════════════════════════════════════════════════╣
總意見數：[N] 條
已完全回應：[N] 條（[%]）
已部分回應：[N] 條
維持原立場：[N] 條（附理由）
╠════════════════════════════════════════════════╣
主要修改清單：
1. 第 X 頁：[修改說明] → 回應 Reviewer [#] 意見 [#]
2. 第 X 頁：[修改說明] → 回應 Reviewer [#] 意見 [#]
3. 新增分析：[說明] → 回應 Reviewer [#] 意見 [#]
4. 補充文獻：[N] 筆 → 回應 Reviewer [#] 意見 [#]
╚════════════════════════════════════════════════╝
```

---

## Step 8：常見回應開場白庫

```
感謝類（英文）：
• "Thank you for this valuable suggestion."
• "We appreciate the reviewer's careful reading."
• "This is an excellent point that we had not considered."
• "We are grateful for this thorough observation."

承認問題類：
• "We acknowledge that our original explanation was unclear."
• "The reviewer is correct that we should have addressed..."
• "We agree that this limitation needs to be clarified."

禮貌堅持類：
• "While we respect the reviewer's perspective, we respectfully
   maintain that..."
• "We understand the reviewer's concern; however, we believe
   that..."
• "We have carefully considered this suggestion and, after
   deliberation, have decided to..."
```

---

## 降級方案

若審稿意見為截圖或 PDF：
- 請求使用者手動貼上文字版
- 若只有部分意見，可針對單一意見進行回應
- 可先提供模板框架，使用者自行填入細節
