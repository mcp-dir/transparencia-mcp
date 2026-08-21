---
name: transparencia-mcp
description: Skill da REST API do Transparência (CGU) na MCP.AI: 4 endpoints em /api/transparencia. Consulta no Portal da Transparência do Governo Federal: sanções (CEIS, CNEP, CEPIM) e Pessoas Expostas Politicamente (PEP) por CPF/CNPJ para due diligence e compliance, e despesas recebidas por favorecido (quanto uma empresa recebeu da União, por órgão e por mês, com os documentos de empenho/liquidação/pagamento). Cobre o Executivo Federal. Hospedado pela plataforma; sem credencial do usuário. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Transparência (CGU) — REST API skill

Você tem acesso à **Transparência (CGU)** REST API na MCP.AI.

> Consulta no Portal da Transparência do Governo Federal: sanções (CEIS, CNEP, CEPIM) e Pessoas Expostas Politicamente (PEP) por CPF/CNPJ para due diligence e compliance, e despesas recebidas por favorecido (quanto uma empresa recebeu da União, por órgão e por mês, com os documentos de empenho/liquidação/pagamento). Cobre o Executivo Federal. Hospedado pela plataforma; sem credencial do usuário.

## Base URL

```
https://api.mcp.ai/api/transparencia
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
curl -X POST https://api.mcp.ai/api/transparencia/despesas/documentos \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cpf_cnpj":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/transparencia/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (4)

#### `transparencia_despesas_documentos`

Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e _(POST /api/transparencia/despesas/documentos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf_cnpj` | string | Sim | CPF (11) ou CNPJ (14) do favorecido, com ou sem máscara. |
| `ano` | integer | Não | Ano de emissão (AAAA). Opcional (default: ano atual). |
| `fase` | string | Não | Fase da despesa. Default 'pagamento'. (empenho, liquidacao, pagamento) |
| `ordenacao` | integer | Não | 1=valor asc, 2=valor desc (default), 3=data asc, 4=data desc. |
| `pagina` | integer | Não | Página (1-based). Default 1. |

#### `transparencia_despesas_favorecido`

DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'. _(POST /api/transparencia/despesas/favorecido)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf_cnpj` | string | Sim | CPF (11) ou CNPJ (14) do favorecido, com ou sem máscara. |
| `mes_ano_inicio` | string | Não | Início do período no formato MM/AAAA. Opcional (default: 12 meses atrás). |
| `mes_ano_fim` | string | Não | Fim do período no formato MM/AAAA. Opcional (default: mês atual). |

#### `transparencia_pep`

Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período. _(POST /api/transparencia/pep)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf` | string | Sim | CPF (11 dígitos), com ou sem máscara. |

#### `transparencia_sancoes`

Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas). _(POST /api/transparencia/sancoes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf_cnpj` | string | Sim | CPF (11) ou CNPJ (14) do sancionado, com ou sem máscara. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_transparencia` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
