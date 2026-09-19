# HERMES · REESTRUTURAÇÃO

Esta pasta contém a documentação operacional da reestruturação.

## Documentos

- `HERMES-REESTRUTURACAO.md` — visão, princípios, arquitetura e roadmap.
- `HERMES-REESTRUTURACAO-STATUS.md` — estado vivo (atualizado a cada sessão).
- `roadmap.md` — etapas (00-16).
- `agents.md` — inventário completo (13 agentes) e matriz de sobreposição.
- `AGENTS.md` — documento vivo de agentes com fontes e diferenças.
- `execution-engine.md` — motor de execução (conceitual).
- `bot-mode.md` — modo Bot (conceitual).
- `dashboard.md` — painel (conceitual).
- `decisions.md` — log de decisões.
- `HERMES-REESTRUTURACAO-STATUS.md` — estado vivo atualizado com auditoria completa.

## Regra

O código é a fonte de verdade para o estado técnico real. A documentação registra intenção, decisões, descobertas e evidências. O painel deve interpretar o estado real, não criar uma segunda fonte de verdade.

## Progresso Atual (2026-09-19)

- ✅ Fase 0: Auditoria completa (108 arquivos versionados no git)
- ✅ Git sincronizado com `flavio-guedes/hermes`
- ✅ Core modules preenchidos (8 arquivos)
- ✅ skills/projects/automations/tests/data preenchidos
- ✅ Dashboards catalogados (98 painéis)
- ✅ 12 arquivos Python (sales-enablement)
- ✅ 11 testes passando
- ✅ CI/CD configurado (crm-backup.yml)
- 📝 Base documental consolidada

## Padrão de Implementação

O agente `sales-enablement` serve como template para implementação de todos os outros agentes:
- Python package structure
- CRMAdapter pattern
- IntelligenceEngine pattern
- Tests com pytest
- Agent docs (system.md, rules.md, workflows.md)
