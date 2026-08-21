# Transparência (CGU)

### Transparência (CGU) para Claude, ChatGPT e agentes de IA

Consulta no Portal da Transparência do Governo Federal: sanções (CEIS, CNEP, CEPIM) e Pessoas Expostas Politicamente (PEP) por CPF/CNPJ para due diligence e compliance, e despesas recebidas por favorecido (quanto uma empresa recebeu da União, por órgão e por mês, com os documentos de empenho/liquidação/pagamento). Cobre o Executivo Federal. Hospedado pela plataforma; sem credencial do usuário.

- 📊 **4 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Transparência (CGU)` e **URL** `https://api.mcp.ai/p_transparencia`.

### Cursor

[➕ Instalar Transparência (CGU) no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=transparencia&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF90cmFuc3BhcmVuY2lhIn0=)

### VS Code (Copilot Chat)

[➕ Instalar Transparência (CGU) no VS Code](vscode:mcp/install?name=transparencia&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_transparencia%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_transparencia
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Quanto a empresa do CNPJ 00.000.000/0001-00 recebeu do governo federal nos últimos 12 meses?
A empresa desse CNPJ tem alguma sanção (CEIS/CNEP)?
Liste os pagamentos federais feitos a esse CNPJ em 2025
```

---

## 4 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `transparencia_sancoes` | Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas). |
| `transparencia_pep` | Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período. |
| `transparencia_despesas_favorecido` | DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'. |
| `transparencia_despesas_documentos` | Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e nº do processo. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Portal da Transparência (CGU), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_transparencia`.


---

## Suporte

- 📧 [transparencia@mcp.ai](mailto:transparencia@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/transparencia-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_transparencia` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
