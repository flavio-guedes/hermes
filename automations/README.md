# Automations

## Objetivo

Registro de automações, fluxos, jobs e rotinas do ecossistema HERMES.

## Princípio

Automatizar depois o que já tem evidência de repetição e retorno.

## Automaciones Confirmadas

### CI/CD Pipeline
- **Arquivo:** `.github/workflows/crm-backup.yml`
- **Tipo:** GitHub Actions workflow
- **Trigger:** repository_dispatch + workflow_dispatch
- **Função:** Backup automático do histórico CRM
- **Comportamento:** Gera JSON, commita, pusha

### Cron Jobs (8 identificados)
1. **checkpoint 18h** — Checkpoint noturno
2. **treinamento noturno** — Treinamento de agentes
3. **founder radar diário** — Atualização do Founder Radar
4. **atualizações job hunter** — Atualização de vagas
5. **EPQ CRM sync** — Sincronização de dados do CRM
6. **Lead follow-up** — Follow-up automático de leads
7. **Dashboard refresh** — Atualização de dashboards
8. **Relatório matinal** — Relatório de status matinal

## Padrão de Automação

Toda automação deve ter:
- Nome descritivo
- Gatilho (cron, evento, manual)
- Ação executada
- Estado (disponível, executando, concluído, erro)
- Timeout definido
- Retry configurado
- Logging estruturado
- Evidência de execução

## Padrão de Segurança

- Nenhuma ação reversível sem aprovação quando risco ≥ médio
- Nenhuma execução aberta sem timeout
- Nenhum loop sem saída
- Secrets NUNCA em código ou config
- Credenciais isoladas em variáveis de ambiente

## Fluxo de Automação

```
HERMES (orquestrador)
    ↓
  Workflow (determinístico)
    ↓
  Agente especialista (se ambiguidade)
    ↓
  Execução com timeout + retry
    ↓
  Evidência + log estruturado
    ↓
  Dashboard atualizado
```

## Regras

1. Automatizar só o que tem evidência de repetição
2. Manter browser automation como fallback
3. Preferir API/MCP/webhook quando possível
4. Toda automação tem timeout e retry
5. Registrar evidência de cada execução

## Referência

Ver `docs/arquitetura-ecossistema-2026-09-04.md` para matriz de integrações.
Ver `.github/workflows/crm-backup.yml` para exemplo de CI/CD.
