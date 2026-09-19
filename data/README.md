# Data

## Objetivo

Gerenciar esquemas, exemplos, exports e relatórios do ecossistema HERMES.

## Princípio

- Evitar secrets aqui
- Preferir schemas e exemplos
- Separar raw/ de curated/
- Uma fonte de verdade para dados operacionais

## Estrutura de Dados

### Dados Operacionais (JSON)
- `agents/sales-enablement/crm/state.json` — Estado atual de leads
- `dashboards/model-health.json` — Saúde de modelos LLM
- `docs/inventario-paineis.json` — Inventário de 98 painéis
- `docs/integration-manifest.json` — Links de projetos EPQ

### Dados de Export (CSV)
- `agents/sales-enablement/crm/exports/` — Exportações de leads

### Dados de Configuração
- `agents/sales-enablement/playbooks/` — ICPs, personas, objeções, templates
- `.github/workflows/` — Configuração de CI/CD

## Esquemas de Dados

### Lead Schema
```json
{
  "id": "string",
  "nome": "string",
  "empresa": "string",
  "email": "string",
  "stage": "string",
  "sales_score": "int",
  "deal_health": "string",
  "next_action": "string",
  "next_action_channel": "string",
  "next_action_due": "ISO8601"
}
```

### Model Health Schema
```json
{
  "task_id": "string",
  "status": "FAILED | SUCCESS | PENDING",
  "provider": "string",
  "model": "string",
  "error": "string",
  "retry_count": "int",
  "context_tokens": "int"
}
```

## Regras de Dados

1. **Uma fonte de verdade** — Dashboards interpretam os mesmos dados da operação
2. **Nunca inventar dados** — Todo dado deve ter origem verificável
3. **Separar raw de curated** — Dados brutos vs processados
4. **Nunca expor secrets** — Credenciais em variáveis de ambiente
5. **Versionar mudanças de schema** — Cada mudança de schema documentada

## Dados Atuais

### Lead Data (CRM state.json)
- Dados reais de leads (Adailton Santos, etc.)
- Stage, sales_score, deal_health preenchidos
- Interactions registradas

### Model Health Data (model-health.json)
- Dados de falhas de API (429 errors)
- Taxa de erro: 2397 rate limits em 1 hora
- Fallback para claude-haiku-3.5-4k

## Dados de Inventário

- **98 painéis HTML** catalogados em `docs/inventario-paineis.md`
- **Categorias:** 24 projeto, 20 dashboard, 19 ferramenta/agente, 9 crm, etc.
- **Deploy:** GitHub Pages

## Referência

Ver `docs/inventario-paineis.md` para inventário completo de painéis.
Ver `agents/sales-enablement/crm/state.json` para exemplo de dados operacionais.
Ver `dashboards/model-health.json` para exemplo de métricas.
