---
name: removebg-mcp
description: Skill da REST API do Remover Fundo na MCP.AI: 1 endpoint em /api/removebg. Remove o fundo de uma imagem por URL, recorta a pessoa ou objeto em primeiro plano com IA e devolve um PNG com fundo transparente. Opcionalmente troca o fundo por uma cor sólida ou redimensiona. Leva poucos segundos, sem credenciais, hospedado pela plataforma. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Remover Fundo — REST API skill

Você tem acesso à **Remover Fundo** REST API na MCP.AI.

> Remove o fundo de uma imagem por URL, recorta a pessoa ou objeto em primeiro plano com IA e devolve um PNG com fundo transparente. Opcionalmente troca o fundo por uma cor sólida ou redimensiona. Leva poucos segundos, sem credenciais, hospedado pela plataforma.

## Base URL

```
https://api.mcp.ai/api/removebg
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/removebg/remove \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"image_url":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/removebg/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `removebg_remove`

Remove o fundo de uma imagem apontada por URL: recorta o objeto/pessoa em primeiro plano e devolve um link de download do resultado (PNG com fundo transparente por padrão), que também fica na aba Arqu _(POST /api/removebg/remove)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `image_url` | string | Sim | URL pública (http/https) da imagem a recortar. Aceita PNG, JPEG, WebP, GIF ou HEIC, até 20 MB. |
| `format` | string | Não | Formato de saída. 'png' (padrão) e 'webp' preservam a transparência; 'jpeg' NÃO tem canal alfa, então use-o só junto de `background` (uma cor sólida) — sem cor, o fundo do JPEG sai preto. (png, webp, jpeg) |
| `background` | string | Não | Opcional. Cor sólida para o novo fundo, no lugar de transparência (ex.: 'white', '#ff0000', 'rgb(0,0,0)'). Sem este campo, o fundo fica transparente. |
| `max_width` | integer | Não | Opcional. Largura máxima em pixels do resultado (redimensiona proporcional). Teto 4000. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_removebg` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
