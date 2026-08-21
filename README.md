# Remover Fundo

### Remover Fundo para Claude, ChatGPT e agentes de IA

Remove o fundo de uma imagem por URL, recorta a pessoa ou objeto em primeiro plano com IA e devolve um PNG com fundo transparente. Opcionalmente troca o fundo por uma cor sólida ou redimensiona. Leva poucos segundos, sem credenciais, hospedado pela plataforma.

- 📊 **1 ferramenta**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Remover Fundo` e **URL** `https://api.mcp.ai/p_removebg`.

### Cursor

[➕ Instalar Remover Fundo no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=removebg&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZW1vdmViZyJ9)

### VS Code (Copilot Chat)

[➕ Instalar Remover Fundo no VS Code](vscode:mcp/install?name=removebg&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_removebg%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_removebg
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Remova o fundo desta foto de produto: https://…/tenis.jpg
Recorte a pessoa desta imagem e deixe o fundo branco
Tire o fundo desta logo e me devolva um PNG transparente
```

---

## 1 ferramenta disponível

| Tool | Descrição |
|---|---|
| `removebg_remove` | Remove o fundo de uma imagem apontada por URL: recorta o objeto/pessoa em primeiro plano e devolve um link de download do resultado (PNG com fundo transparente por padrão), que também fica na aba Arquivos do mcp.ai. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Cloudflare, o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_removebg`.


---

## Suporte

- 📧 [removebg@mcp.ai](mailto:removebg@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/removebg-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_removebg` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
