# Memory

## Objetivo

Gerenciar estado, histórico de decisões, aprendizados, contexto cross-session e evolução do conhecimento no ecossistema Hermes.

## Tipos de Memória

### 1. Estado Operacional
- Dados atuais de execução
- Estado de leads, tarefas, projetos
- Local: JSON files (CRM state.json, model-health.json)
- Padrão: CRMAdapter pattern (visto em sales-enablement)

### 2. Memória de Decisões
```
Contexto → Evidência → Decisão → Responsável → Resultado
```
- Cada decisão registra: data, contexto, problema, evidência, decisão, impacto, responsável, resultado, status
- Local: docs/restructuring/decisions.md

### 3. Histórico de Execução
- Arquivos alterados
- Testes realizados
- Resultado de cada execução
- Erros encontrados
- Commits realizados

### 4. Aprendizados
- Documentação de patterns que funcionaram
- Documentação de patterns que falharam
- Atualização de playbooks
- Evolução de templates

## Padrão de Implementação

O padrão de Memory é demonstrado por:

### State Management (sales-enablement/crm/adapter.py)
```python
class CRMAdapter:
    def _load() → Dict[str, Dict]
    def _save() → None
    def upsert_lead(lead) → LeadRecord
    def get_lead(id) → Optional[LeadRecord]
```

### Evidence Pattern
- Toda execução gera evidência (arquivos alterados, testes, resultados)
- O `me mostre` pode demonstrar evidências reais
- Nunca inventar evidência

### Cross-Session Memory
- O Hermes tem memória cross-session (documentado na arquitetura-ecossistema)
- Cron jobs executam checkpoints noturnos
- O STATUS.md serve como ponto de retomada

## Regras de Memória

1. **Nunca apagar histórico de decisões**
2. **Sempre registrar resultado** (sucesso ou falha)
3. **Sempre vincular evidência** a cada decisão
4. **Nunca inventar dados** para memória
5. **Sempre atualizar** quando houver mudança de estado

## Estrutura de Arquivos

```
core/memory/
├── decisions/          # Memória de decisões
├── execution/          # Histórico de execução
├── state/              # Estado operacional atual
├── learning/           # Aprendizados e padrões
└── history/            # Histórico completo
```

## Referência

Ver `HERMES-REESTRUTURACAO.md` para o modelo de memória.
Ver `docs/restructuring/decisions.md` para o formato de decisões.
Ver `agents/sales-enablement/crm/` para estado baseado em JSON.
