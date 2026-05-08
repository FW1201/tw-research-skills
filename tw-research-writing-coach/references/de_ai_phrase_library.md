# De-AI 機械化短語偵測庫

> 設計參考：research-writing-skill/Norman-bury（De-AI-ification 規則）
> 本庫整合中英文學術寫作中最常見的機械化短語，並提供替換建議

---

## 中文機械化短語清單

### 空泛強調類
| ❌ 機械化短語 | ✅ 替換策略 |
|------------|-----------|
| 值得注意的是 | 直接陳述具體發現，不需前導語 |
| 顯而易見 | 提供數據或引用支持「顯而易見」的事實 |
| 不言而喻 | 如果真的不言而喻就不要說，否則說清楚 |
| 眾所周知 | 改為「根據 [作者, 年份]」 |
| 毫無疑問 | 改為「如 [研究] 所示」或直接陳述 |

### 空洞連接類
| ❌ 機械化短語 | ✅ 替換策略 |
|------------|-----------|
| 綜上所述 | 直接寫結論句，不需導語 |
| 由此可見 | 直接用「因此」或「這表明」 |
| 總而言之 | 直接進入總結，不需前置語 |
| 基於以上分析 | 直接說「本研究發現...」 |
| 不難發現 | 改為具體陳述 |

### 過度修飾類
| ❌ 機械化短語 | ✅ 替換策略 |
|------------|-----------|
| 極其重要 | 說明為什麼重要（具體理由）|
| 非常顯著 | 如有統計意義，報告 p 值和效果量 |
| 至關重要 | 說明對什麼而言重要 |
| 具有重要意義 | 說明具體意義是什麼 |
| 深遠影響 | 具體說明影響什麼方面 |

### 弱化主動性類
| ❌ 機械化短語 | ✅ 替換策略 |
|------------|-----------|
| 有研究指出 | 改為「[Author, Year] 指出」 |
| 許多學者認為 | 列出具體學者並引用 |
| 相關研究顯示 | 引用具體研究 |
| 據相關文獻 | 提供具體文獻來源 |

---

## 英文機械化短語清單

### Filler Phrases（填充短語）
| ❌ Mechanical Phrase | ✅ Replacement Strategy |
|---------------------|----------------------|
| It is worth noting that | State the fact directly |
| It should be noted that | Delete entirely, state the point |
| It is interesting to note | Delete, let the finding speak |
| Needless to say | If needless, don't say it |
| As mentioned above | Avoid backward references; restructure |

### Weak Transitions（弱連接詞）
| ❌ Mechanical Phrase | ✅ Replacement |
|---------------------|--------------|
| In conclusion (at paragraph start) | Cut, write the conclusion directly |
| In summary | Cut, state the summary |
| To summarize | Cut |
| Last but not least | Simply say "Finally" |
| All in all | Delete |

### Vague Qualifiers（模糊修飾）
| ❌ Mechanical Phrase | ✅ Replacement |
|---------------------|--------------|
| "Significantly" (without stats) | Use only with p < .05 data |
| "Very important" | State why it's important |
| "Clearly shows" | If clear, just state it |
| "Obviously" | Delete (nothing is obvious) |
| "It is evident that" | State the evidence |

### Passive Overuse（被動語態過度）
| ❌ Overused Passive | ✅ Active Alternative |
|--------------------|---------------------|
| "It was found that" | "We found" / "The analysis revealed" |
| "It is suggested that" | "We suggest" or cite the source |
| "It can be seen that" | "The data show" |

---

## 替換強動詞庫（中文）

描述研究發現：
- 呈現、揭示、顯示、表明、指出、發現
- 證實、驗證、支持、挑戰、推翻

描述分析動作：
- 分析、探討、檢視、考察、比較、對照
- 歸納、統整、推論、詮釋

描述貢獻：
- 補充、擴展、深化、修正、更新

---

## 替換強動詞庫（英文）

**Research findings:**
demonstrate, reveal, indicate, suggest, highlight, underscore,
elucidate, confirm, challenge, refute, extend, corroborate

**Analysis actions:**
analyze, examine, investigate, compare, contrast, identify,
synthesize, interpret, evaluate, assess

**Contributions:**
contribute, advance, extend, fill, address, bridge, refine
