# Routing

## Objetivo

Componente responsável por rotear tarefas, contextos e fluxos para o agente ou workflow correto usando o padrão router-first.

## Princípio Router-First

1. Quando um fluxo é determinístico → usar workflow
2. Quando há ambiguidade → usar agente especializado
3. Quando há necessidade de decisão → usar orquestrador (Hermes)
4. Quando há pesquisa → usar Oracle
5. Quando há estratégia → usar Strategos
6. Quando há vendas → usar sales-enablement

## Padrões de Roteamento

### Por tipo de tarefa

| Tipo de Tarefa | Destino | Critério |
|---|---|---|
| Content creation | Muse + Nexus | UX writing + interface |
| Data analysis | Vector + Nexus | Métricas + dashboard |
| Sales/CRM | sales-enablement | Lead management |
| Research | Oracle | Investigation |
| Strategy | Strategos | Roadmap |
| QA | Aegis | Validation |
| Security | Sentinel | Protection |
| Marketing | Pulse | Growth |
| Architecture | Forge | Structure |
| UI/Design | Vanguard | Visual |

### Por prioridade

- **Urgente:** Roteamento imediato, sem fila
- **Alta:** Roteamento na próxima janela
- **Normal:** Roteamento quando capacidade disponível
- **Baixa:** Roteamento em batch

### Por dependência

- Verificar dependências antes de roteamento
- Não rotear tarefa que dependa de tarefa não concluída
- Registrar dependências no Execution Engine

## Integração com Execution Engine

O Routing utiliza o Execution Engine para:
- Verificar capacidade dos agentes
- Verificar estado de execução
- Gerenciar filas
- Respeitar dependências

## Implementação de Referência

O padrão de routing é demonstrado pelo fluxo de integração entre agentes:
- `VECTOR → NEXUS` (dados para dashboards)
- `ORACLE → PULSE` (research para marketing)
- `HERMES → SALES-ENABLEMENT` (orquestração para vendas)

## Referência

Ver `HERMES-REESTRUTURACAO.md` para a arquitetura completa.
Ver `docs/arquitetura-ecossistema-2026-09-04.md` para o mapa detalhado de gargalos e integrações.
