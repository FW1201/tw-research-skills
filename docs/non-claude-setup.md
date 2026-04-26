# tw-research-skills — Codex & Antigravity 安裝指南

適用平台：**OpenAI Codex CLI** 和 **Google Antigravity IDE**  
版本：V3.1（2026-04-26）

---

## Codex 安裝

### Skills 路徑

```
<your-project>/.agents/skills/<skill-name>/SKILL.md   ← 專案層（推薦）
~/.codex/skills/<skill-name>/SKILL.md                  ← 全域層
```

### 安裝步驟

```bash
git clone https://github.com/FW1201/tw-research-skills.git

# 安裝到專案目錄
mkdir -p <your-project>/.agents/skills
cp -r tw-research-skills/tw-research-*/ <your-project>/.agents/skills/

# 或全域安裝
mkdir -p ~/.codex/skills
cp -r tw-research-skills/tw-research-*/ ~/.codex/skills/
```

### 使用方式

```
"幫我寫一份雙菱形研究計畫書"
→ 自動啟用 tw-research-proposal-diamond

"檢查這篇論文的參考文獻格式"
→ 自動啟用 tw-research-citation-proofer

"幫我視覺化研究架構圖"
→ 自動啟用 tw-research-viz
```

### MCP Connectors 設定

```toml
# ~/.codex/config.toml

# Consensus（學術論文搜尋）
[mcp_servers.consensus]
url = "https://mcp.consensus.app/mcp"
headers = { Authorization = "Bearer ${CONSENSUS_TOKEN}" }

# Excalidraw（研究架構圖）
[mcp_servers.excalidraw]
url = "https://excalidraw-mcp-app.vercel.app/mcp"

# Google Drive（論文存檔）
[mcp_servers.google-drive]
command = "npx"
args = ["-y", "@google/mcp-server-googledrive"]

# Gmail（期刊投稿 Cover Letter）
[mcp_servers.gmail]
url = "https://gmail.mcp.claude.com/mcp"
headers = { Authorization = "Bearer ${GMAIL_TOKEN}" }

# Notion（研究筆記管理）
[mcp_servers.notion]
command = "npx"
args = ["-y", "@notionhq/notion-mcp-server"]
env = { NOTION_API_KEY = "${NOTION_API_KEY}" }
```

### Skills × MCP 需求對照

| Skill | 必要 MCP | 選用 MCP |
|-------|---------|---------|
| tw-research-proposal-diamond | WebSearch | Drive |
| tw-research-citation-checker | WebSearch, Consensus | — |
| tw-research-viz | WebSearch | Excalidraw, Figma |
| tw-research-lit-review | WebSearch, Consensus | Drive |
| tw-research-stat-consultant | — | Drive |

---

## Antigravity 安裝（Google AI IDE）

研究類 Skills 在 Antigravity 效果最佳，尤其是 **Jupyter Notebook 整合**（統計分析、視覺化）。

### Skills 路徑

```
~/.gemini/antigravity/skills/<skill-name>/SKILL.md   ← 全域層
<project>/.agent/skills/<skill-name>/SKILL.md         ← 專案層
```

注意：路徑是 `.agent`（單數），不是 `.agents`。

### 安裝步驟

```bash
mkdir -p ~/.gemini/antigravity/skills
cp -r tw-research-skills/tw-research-*/ ~/.gemini/antigravity/skills/
```

### MCP Connectors 設定

**MCP Server Hub（推薦）**：在 Antigravity 介面搜尋 Consensus、Notion、Google Drive 並啟用。

**JSON 設定**：
```json
// ~/.gemini/antigravity/mcp_config.json
{
  "mcpServers": {
    "consensus": {
      "url": "https://mcp.consensus.app/mcp",
      "headers": { "Authorization": "Bearer ${CONSENSUS_TOKEN}" }
    },
    "notion": {
      "command": "npx",
      "args": ["-y", "@notionhq/notion-mcp-server"],
      "env": { "NOTION_API_KEY": "${NOTION_API_KEY}" }
    },
    "google-drive": {
      "command": "npx",
      "args": ["-y", "@google/mcp-server-googledrive"]
    }
  }
}
```

### Antigravity 特有優勢

- **tw-research-stat-consultant**：可直接在 Jupyter Notebook 中執行 Python/R 統計分析
- **tw-research-viz**：在 Notebook 中即時預覽 matplotlib/Plotly 圖表

---

## 常見問題

| 問題 | 解決方案 |
|------|---------|
| Codex 找不到 Skill | 確認路徑為 `.agents/skills/`（複數） |
| Antigravity 找不到 Skill | 確認路徑為 `.agent/skills/`（單數） |
| Consensus MCP 認證失敗 | 確認 `$CONSENSUS_TOKEN` 已設定 |
| Frontmatter 欄位警告 | `allowed-tools` 是 Claude Code 專屬欄位，忽略即可 |
