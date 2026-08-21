# Remover Fundo

### Remover Fundo for Claude, ChatGPT and AI agents

Removes the background from an image by URL, cutting out the foreground person or object with AI and returning a PNG with a transparent background. Optionally swaps the background for a solid color or resizes. Takes a few seconds, no credentials, platform-hosted.

- 📊 **1 tool**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Remover Fundo`, URL `https://api.mcp.ai/p_removebg`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=removebg&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZW1vdmViZyJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=removebg&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_removebg%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_removebg
```

---

## 1 tool

| Tool | Description |
|---|---|
| `removebg_remove` | Remove o fundo de uma imagem apontada por URL: recorta o objeto/pessoa em primeiro plano e devolve um link de download do resultado (PNG com fundo transparente por padrão), que também fica na aba Arquivos do mcp.ai. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_removebg` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
