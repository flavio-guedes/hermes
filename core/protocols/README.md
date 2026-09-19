# Protocols

## Objetivo

Definir os protocolos de comunicação, contratos de dados, formatos de integração e padrões de troca de informação entre componentes do ecossistema Hermes.

## Princípios

1. **Um sistema de estado** para dados operacionais.
2. **Contratos de dados** para troca entre agentes.
3. **Integração via API/MCP/webhook** quando tecnicamente viável.
4. **Browser automation como fallback**, não primeira via.
5. **Logging estruturado** para toda execução.

## Contratos de Dados

### Lead Record (sales-enablement)
```json
{
  "id": "string",
  "nome": "string",
  "empresa": "string",
  "cargo": "string",
  "telefone": "string",
  "email": "string",
  "linkedin": "string",
  "fonte": "string",
  "stage": "string",
  "status": "string",
  "sales_score": "int",
  "deal_health": "string",
  "next_action": "string",
  "next_action_channel": "string",
  "next_action_due": "ISO8601",
  "last_contact_at": "ISO8601",
  "tags": ["string"],
  "notes": ["string"],
  "interactions": [{}],
  "updated_at": "ISO8601"
}
```

### Task Record (Execution Engine)
```json
{
  "id": "string",
  "projeto": "string",
  "contexto": "string",
  "agente": "string",
  "bot": "string",
  "prioridade": "enum",
  "estado": "enum",
  "dependencias": ["string"],
  "inicio": "ISO8601",
  "progresso": "int",
  "resultado": "string",
  "evidencias": ["string"],
  "historico": [{}]
}
```

### Model Health Record
```json
{
  "task_id": "string",
  "status": "FAILED | SUCCESS | PENDING",
  "provider": "anthropic | openai | ...",
  "model": "string",
  "error": "string",
  "retry_count": "int",
  "cooldown_until": "ISO8601"
}
```

## Protocolos de Integração

### GitHub Pages
- Deploy de dashboards via GitHub Pages
- GitHub CLI para versionamento
- Padrão: `git push origin main`

### Google Drive/Sheets
- Repositório de dados e estado
- OAuth para autenticação
- Padrão: arquivos JSON + Sheets

### Telegram
- Canal de saída para notificações
- Padrão: mensagens operacionais

### WhatsApp
- API Business para mensagens comerciais
- Padrão: mensagens com aprovação

### Cron Jobs
- 8 cron jobs identificados no ecossistema
- Padrão: checkpoints, treinamento, founder radar, job hunter

## Logging Estruturado

Toda execução deve gerar log com:
- task, agent, início, fim, duração, tokens, status, erro, retries
- Métrica: taxa de sucesso, custo por domínio, bloqueios, espera
- Tracing: handoff, tool use, falha

## Padrão Router-First

Para comunicação entre componentes:
1. Determinístico → workflow direto
2. Ambíguo → agente especializado
3. Complexo → orquestração via Hermes

## Implementação de Referência

O protocolo de integração é demonstrado pelo sales-enablement:
- `CRMAdapter` lê/escreve via JSON
- `IntelligenceEngine` processa leads
- `FollowupEngine` agenda ações
- `AnalyticsEngine` resume pipeline
- Testes validam o contrato

## Referência

Ver `docs/arquitetura-ecossistema-2026-09-04.md` para matriz de integrações.
Ver `docs/integration-manifest.json` para links de projetos EPQ.
Ver `docs/inventario-paineis.md` para inventário de painéis.
