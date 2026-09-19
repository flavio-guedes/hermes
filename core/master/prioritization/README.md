# Prioritization

## Objetivo

Definir o sistema de prioridades, níveis de urgência, sequenciamento de tarefas e gerenciamento de dependências para o ecossistema Hermes.

## Níveis de Prioridade

| Prioridade | Descrição | Exemplo |
|---|---|---|
| **Urgente** | Precisa ser executado imediatamente | Lead quente, problema de segurança |
| **Alta** | Importante para operação | CRM update, publicação |
| **Normal** | Parte do workflow regular | Análise, relatórios |
| **Baixa** | Nice to have | Pesquisa, experimentação |

## Regras de Prioridade

1. **Prioridade NÃO pode quebrar dependências.**
2. Uma tarefa Urgente não pode bloquear uma tarefa que dela dependa.
3. A prioridade é definida pelo contexto (lead score, deadline, impacto).
4. A prioridade pode ser reavaliada durante a execução.

## Critérios de Priorização

### Para leads (sales-enablement)
- sales_score ≥ 80 → Alta/Urgente
- deal_health CRITICAL → Urgente
- last_contact_at > 30 dias → Normal (reativação)

### Para projetos
- P0: operação crítica (EPQ CRM, ads)
- P1: geração de receita (prospecção, job hunter)
- P2: organização, documentação
- P3: experimentação, pesquisa

### Para agentes
- Aegis: QA sempre tem prioridade antes de deploy
- Sentinel: segurança tem prioridade máxima para falhas
- Vector: dados atualizados têm prioridade para dashboards

## Sequenciamento

```
1. Identificar tarefas (Inbox)
2. Triar (Triaged)
3. Priorizar (Ready)
4. Verificar dependências
5. Executar (Running)
6. Aguardar se necessário (Waiting)
7. Bloquear se necessário (Blocked)
8. Validar (Review)
9. Concluir (Done) ou Falhar (Failed)
10. Arquivar (Archived)
```

## Integração com Execution Engine

O sistema de priorização alimenta o Execution Engine:
- Fila ordenada por prioridade
- Dependências respeitadas
- Capacidade verificada
- Previsão de início calculada

## Padrão de Implementação

O padrão de priorização é demonstrado pelo fluxo do sales-enablement:
- pending_followups() retorna leads ordenados por sales_score
- pipeline_summary() mostra estágios e contagens
- what_to_do_now() retorna top 10 itens com score ≥ 60

## Referência

Ver `HERMES-REESTRUTURACAO.md` para o sistema de prioridades.
Ver `docs/arquitetura-ecossistema-2026-09-04.md` para o mapa de atividades com prioridades (P0-P2).
Ver `agents/sales-enability/` para exemplos de scoring.
