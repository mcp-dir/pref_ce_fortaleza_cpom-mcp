---
name: pref_ce_fortaleza_cpom-mcp
description: Skill da REST API do Prefeitura CE Fortaleza: CPOM na MCP.AI: 1 endpoint em /api/pref_ce_fortaleza_cpom. Prefeitura CE Fortaleza: CPOM, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Prefeitura CE Fortaleza: CPOM — REST API skill

Você tem acesso à **Prefeitura CE Fortaleza: CPOM** REST API na MCP.AI.

> Prefeitura CE Fortaleza: CPOM, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/pref_ce_fortaleza_cpom
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
curl -X POST https://api.mcp.ai/api/pref_ce_fortaleza_cpom/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cnpj":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/pref_ce_fortaleza_cpom/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `pref_ce_fortaleza_cpom_consultar`

Prefeitura CE Fortaleza: CPOM, consulta em fonte oficial. _(POST /api/pref_ce_fortaleza_cpom/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Sim | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_pref_ce_fortaleza_cpom` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
