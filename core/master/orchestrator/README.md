# Orchestrator

## Objetivo

Componente central do sistema HERMES responsável por receber objetivos, decompor tarefas, escolher agentes, delegar, priorizar, acompanhar execução, redistribuir tarefas, identificar gargalos, coordenar QA e consolidar resultados.

## Fluxo Principal

```
COMMAND BAR / CONTEXTO
           ↓
        DADOS
           ↓
       DECISÃO
           ↓
   EXECUTION ENGINE
           ↓
  FILA + CAPACIDADE
           ↓
  AGENTES / BOTS
           ↓
       EXECUÇÃO
           ↓
      VALIDAÇÃO
           ↓
       EVIDÊNCIA
           ↓
       HISTÓRICO
```

## Responsabilidades

1. Receber objetivos do usuário ou do ATLAS
2. Decompor tarefas em subtarefas executáveis
3. Escolher o(s) agente(s) apropriado(s)
4. Delegar com contexto claro
5. Priorizar baseado em urgência, importância e dependências
6. Acompanhar execução em tempo real
7. Redistribuir tarefas quando necessário
8. Identificar gargalos
9. Coordenar QA via Aegis
10. Consolidar resultados com evidências

## Padrão Router-First

- **Router-first:** Hermes roteia para workflow quando possível; agente só quando há ambiguidade.
- **Skill-first:** capacidades reutilizáveis antes de prompts ad-hoc.
- **State-first:** sem estado não existe coordenação confiável.
- **Governance-first:** sem approval/policy não existe autonomia segura.
- **Observability-first:** sem tracing/metrícula não existe melhoria contínua.

## Estados de Tarefa

- Inbox → Triaged → Ready → Running → Waiting → Blocked → Review → Done → Failed → Archived

## Integração com Ventana de Vendas

O Hermes coordena o sales-enablement-agent quando o contexto é comercial:
- Preparação de abordagens
- Lead scoring e qualification
- Follow-up scheduling
- CRM updates

## Padrão de Implementação (referência)

O agente `sales-enablement` demonstra o padrão completo:
- Python package com `__init__.py`
- CRMAdapter para state management
- IntelligenceEngine para scoring
- FollowupEngine para scheduling
- AnalyticsEngine para métricas

## Referência

Ver `agents/hermes/README.md` para a identidade do agente Master.
Ver `docs/restructuring/HERMES-REESTRUTURACAO.md` para a hierarquia completa.
Ver `agents/sales-enablement/` para implementação de referência.
