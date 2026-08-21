# Ferramentas

Transparência (CGU) expõe 4 ferramentas (todas somente leitura).

### 1. `transparencia_sancoes`
**Input**: `cpf_cnpj`

Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas).

### 2. `transparencia_pep`
**Input**: `cpf`

Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período.

### 3. `transparencia_despesas_favorecido`
**Input**: `cpf_cnpj`, `mes_ano_inicio` (opcional), `mes_ano_fim` (opcional)

DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'.

### 4. `transparencia_despesas_documentos`
**Input**: `cpf_cnpj`, `ano` (opcional), `fase` (opcional), `ordenacao` (opcional), `pagina` (opcional)

Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e nº do processo.

## Prompts de exemplo

```
Quanto a empresa do CNPJ 00.000.000/0001-00 recebeu do governo federal nos últimos 12 meses?
A empresa desse CNPJ tem alguma sanção (CEIS/CNEP)?
Liste os pagamentos federais feitos a esse CNPJ em 2025
```
