# Transparência (CGU)

### Transparência (CGU) for Claude, ChatGPT and AI agents

Brazilian Federal Transparency Portal: sanctions (CEIS, CNEP, CEPIM) and Politically Exposed Persons (PEP) by CPF/CNPJ for due diligence and compliance, plus expenses received by recipient (how much a company received from the federal government, by agency and month, with the empenho/liquidation/payment documents). Covers the federal Executive branch. Platform-hosted; no user credentials.

- 📊 **4 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Transparência (CGU)`, URL `https://api.mcp.ai/p_transparencia`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=transparencia&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF90cmFuc3BhcmVuY2lhIn0=)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=transparencia&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_transparencia%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_transparencia
```

---

## 4 tools

| Tool | Description |
|---|---|
| `transparencia_sancoes` | Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas). |
| `transparencia_pep` | Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período. |
| `transparencia_despesas_favorecido` | DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'. |
| `transparencia_despesas_documentos` | Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e nº do processo. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_transparencia` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
