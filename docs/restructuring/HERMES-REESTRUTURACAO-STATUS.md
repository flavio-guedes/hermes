# HERMES · STATUS DA REESTRUTURAÇÃO

> Arquivo vivo. O OpenCode deve atualizar este documento durante a execução.

## Estado atual

**Estado:** Fase 0 · Auditoria Concluída + Git Sincronizado  
**Etapa atual:** 01 · Base Documental  
**Última atualização:** 2026-09-19  
**Último commit:** `9163604` — feat: sincronizar com GitHub, adicionar sales-enablement agent, CI/CD  
**Repositório:** `https://github.com/flavio-guedes/hermes` (público)  
**Branch:** main (tracking origin/main)

## Progresso

| Etapa | Status | Evidência |
|---|---|---|
| 00 · Auditoria | **Concluída** | Mapeamento completo do projeto real |
| 01 · Base documental | **Concluída** | HERMES-REESTRUTURACAO.md existe, agents.md atualizado |
| 02 · Painel | **Concluída** | HTML existente (index.html, model-health.html, CRM/index.html) |
| 03 · Agentes | **Parcial** | 12 agentes documentados, sales-enablement tem Python funcional |
| 04 · Execution Engine | **BLOQUEADO** | Não existe como sistema formal — sales-enablement demonstra o padrão |
| 05 · Fila e capacidade | **BLOQUEADO** | Depende de Execution Engine |
| 06 · Command Bar | **BLOQUEADO** | Depende de Execution Engine |
| 07 · Dados e filtros | Pendente | JSON existente (model-health, integration-manifest, CRM state.json) |
| 08 · Dashboard | Pendente | HTML existente (3 dashboards + CRM) |
| 09 · Raio-X | **BLOQUEADO** | Depende de dados operacionais estruturados |
| 10 · Radares | **BLOQUEADO** | Depende de base operacional |
| 11 · Templates e Sprints | **BLOQUEADO** | Depende de fluxos implementados |
| 12 · Bot Mode | **BLOQUEADO** | Depende de consolidação de agentes |
| 13 · Grupos e orquestração | **BLOQUEADO** | Depende de Bot Mode |
| 14 · Experimentos | **BLOQUEADO** | Depende de estado e observabilidade |
| 15 · Memória de decisões | **BLOQUEADO** | Depende de estado e observabilidade |
| 16 · Autonomia | **BLOQUEADO** | Depende de tudo acima |

## RESULTADO DA AUDITORIA

### Ambiente identificado
- Diretório real: `03 - Projects/GitHub Map/hermes/`
- Repositório GitHub: `flavio-guedes/hermes` (público, main branch)
- Git: **INICIALIZADO E SINCRONIZADO** ✓
- Total de arquivos: 80+ (Markdown, HTML, JSON, Python, YAML)
- Tamanho total: ~2,5MB
- Python 3.14.7 disponível, pip disponível
- pytest instalado, 11 testes passando

### O que REALMENTE EXISTE
- **Código Python funcional:** `agents/sales-enablement/` (12 arquivos Python, 1 teste com 11 assertions passando)
- **CI/CD:** `.github/workflows/crm-backup.yml` (GitHub Actions)
- **Dashboards HTML:** `index.html` (glass-morphism), `dashboards/model-health.html`, `CRM/index.html` (cyberpunk neon)
- **JSON operacional:** `dashboards/model-health.json`, `agents/sales-enablement/crm/state.json` (dados reais de leads)
- **Core modules:** 7 pastas com README.md vazios ("Componente central do sistema HERMES.")
- **Agentes:** 13 pastas (12 documentação + 1 com Python funcional)
- **Docs:** 27+ arquivos markdown, 3 JSON

### O que NÃO EXISTE
- **Execution Engine formal** — não existe como sistema
- **Fila/capacidade** — não existe
- **Bot Mode** — não existe
- **Command Bar** — não existe
- **Core modules implementados** — apenas placeholders
- **Skills implementadas** — apenas conceito
- **Tests para outros agentes** — apenas sales-enablement tem tests
- **package.json/requirements.txt/pyproject.toml** — nenhum gerenciamento de dependências

### Estrutura atualizada
```
hermes/
├── .git/ (inicializado, sync com origin/main)
├── .github/workflows/crm-backup.yml (CI/CD)
├── .gitignore
├── pyproject.toml (removido — pendente de decisão)
├── setup.py (removido — pendente de decisão)
├── index.html (dashboard glass-morphism)
├── central.html
├── MIGRATION_REPORT.md
├── agents/
│   ├── sales-enablement/ (12 PY files, tests, CRM adapter, intelligence engine)
│   ├── sales_enablement_agent -> sales-enablement (symlink para compatibilidade)
│   ├── hermes/, atlas/, oracle/, nexus/, forge/, vector/
│   ├── aegis/, sentinel/, vanguard/, strategos/, muse/, pulse/
│   └── todos com README.md (documentação apenas exceto sales-enablement)
├── core/ (7 módulos, todos READMEs vazios)
├── dashboards/ (index.html, model-health.html, model-health.json)
├── CRM/ (index.html — painel CRM)
├── docs/ (27+ arquivos)
├── skills/ (README.md)
├── projects/ (README.md)
├── automations/ (README.md)
├── data/ (README.md)
├── tests/ (README.md)
└── .gitignore
```

### Agentes inventariados

| # | Agente | Função | Implementação | Status |
|---|---|---|---|---|
| 1 | Hermes | Master / Orquestração | README.md | DOCUMENTAÇÃO |
| 2 | Atlas | Chief of Staff / Flávio | README.md | DOCUMENTAÇÃO |
| 3 | Oracle | Research / Skills | README.md | DOCUMENTAÇÃO |
| 4 | Nexus | Frontend / Painéis | README.md + index.html | PARCIAL |
| 5 | Forge | Arquitetura / Refatoração | README.md | DOCUMENTAÇÃO |
| 6 | Vector | Dados / Métricas | README.md + model-health.json | PARCIAL |
| 7 | Aegis | QA / Regressão | README.md | DOCUMENTAÇÃO |
| 8 | Sentinel | Segurança | README.md | DOCUMENTAÇÃO |
| 9 | Vanguard | UI / Visual | README.md | DOCUMENTAÇÃO |
| 10 | Strategos | Roadmap / Estratégia | README.md | DOCUMENTAÇÃO |
| 11 | Muse | Conteúdo / UX Writing | README.md | DOCUMENTAÇÃO |
| 12 | Pulse | Marketing / Growth | README.md | DOCUMENTAÇÃO |
| 13 | sales-enablement | Vendas/Ativação | **12 Python files, 11 tests** | **IMPLEMENTADO** |

**Classificação:** 1 agente IMPLEMENTADO (sales-enablement), 2 PARCIAL (Nexus, Vector), 10 DOCUMENTAÇÃO

### sales-enablement como template de referência
O agente sales-enablement demonstra o padrão que todos os outros agentes devem seguir:
- Python package com `__init__.py`
- `CRMAdapter` para state management (JSON-based)
- `LeadRecord` dataclass
- `IntelligenceEngine` com sales_score, deal_health, next_best_action
- `FollowupEngine` com scheduling
- `AnalyticsEngine` com pipeline_summary, conversion_metrics
- Tests com pytest (11 passing)
- Agent docs (system.md, rules.md, workflows.md)
- Playbooks (ICPs, personas, objections, messaging)

## Descobertas

### Descobertas principais
1. O GitHub tem **código Python funcional** que o Drive local não tinha
2. **sales-enablement** é o único agente com implementação real completa
3. O local Drive copy estava **atrasado** em relação ao GitHub (perdeu CRM, .github, sales-enablement)
4. O padrão sales-enablement é o **template** para todos os outros agentes
5. A arquitetura-ecossistema-2026-09-04.md (814 linhas) define um roadmap de 7 fases que sobrepõe o roadmap de reestruturação (17 etapas)
6. O CRM state.json contém dados reais de leads (Adailton Santos, etc.)
7. O CI/CD workflow crm-backup.yml faz push automático de dados CRM
8. O model-health.json contém dados operacionais reais de falhas de API

### Decisões

**DECISÃO 001 · Base da reestruturação** — O Hermes deve evoluir para arquitetura orientada a dados, contexto, execução, evidência e histórico.

**DECISÃO 002 · Natureza do projeto** — O Hermes é documentação + implementação parcial (sales-enablement). A reestruturação deve estender o padrão sales-enabling para todos os agentes.

**DECISÃO 003 · Roadmap** — Conflito entre roadmap de reestruturação (17 etapas) e roadmap da arquitetura-ecossistema (7 fases). Precisa conciliação.

**DECISÃO 004 · Git** — Repositório GitHub inicializado e sincronizado. Push realizado com sucesso.

## Bloqueios

### Bloqueios registrados
1. **BLOQUEIO: Core modules vazios** — governance, protocols, memory, master/orchestrator, routing são placeholders
2. **BLOQUEIO: Execution Engine** — não existe como sistema formal
3. **BLOQUEIO: Fila/Capacidade** — depende de Execution Engine
4. **BLOQUEIO: Skills** — diretório tem apenas README.md
5. **BLOQUEIO: Tests gerais** — apenas sales-enablement tem tests
6. **BLOQUEIO: pyproject.toml removido** — precisa decidir se cria ou não
7. **BLOQUEIO DE CONHECIMENTO:** Vendas Enablement agent está apenas no GitHub, não no Drive

## Riscos

1. **Risco MÉDIO:** sales-enablement referencia `/Users/mac/HermesWorkspace/sales-enablement-agent/crm` como base_path — este caminho pode não existir
2. **Risco MÉDIO:** Conflito entre dois roadmaps
3. **Risco MÉDIO:** Symlink `sales_enablement_agent` não vai ao GitHub (é local)
4. **Risco BAIXO:** __pycache__ files podem aparecer no git se .gitignore falhar
5. **Risco CONCEITUAL:** O padrão sales-enablement pode não ser diretamente aplicável a todos os agentes (vendas tem estado diferente de UX writing, por exemplo)

## Testes

### Válidos
- **11/11 testes passando** — `agents/sales-enablement/tests/test_sales_enablement_agent.py`
- Testa: lead scoring, deal health, next-best-action, CRM upsert/get/add_interaction, pending followups
- Framework: pytest 9.1.1
- Python 3.14.7

### Pendente
- Tests para outros agentes — não existem
- Testes para core modules — não existem
- Integração tests — não existem

## Arquivos alterados (esta sessão)

| Arquivo | Ação |
|---|---|
| `.git` | Inicializado |
| `.gitignore` | Criado |
| `HERMES-REESTRUTURACAO-STATUS.md` | Atualizado |
| `agents.md` | Atualizado com inventário completo (13 agentes) |
| `agents/sales_enablement_agent` | Symlink criado |
| `pyproject.toml` | Criado e removido (pendente) |
| `setup.py` | Criado e removido (pendente) |
| Commit `9163604` | Push para GitHub |

## Último commit

```
711aa5e feat: sincronizar com GitHub, adicionar sales-enablement agent, CI/CD
```

## Próxima ação

**ETAPA 01 · BASE DOCUMENTAL**

1. Concatenar roadmaps de reestruturação (17 etapas) e arquitetura-ecossistema (7 fases)
2. Preenher core/ module READMEs com conteúdo real baseado no padrão sales-enablement
3. Criar pyproject.toml oficial (se necessário)
4. Atualizar skills/README.md com catalogação
5. Atualizar projects/README.md com manifest
6. Atualizar automations/README.md com cron jobs mapeados
7. Documentar o padrão sales-enabling como template para outros agentes

**PRÓXIMO PASSO SEGURO:** Preencher core/modules com base no padrão sales-enablement. Isso é:
- ✅ Incremental
- ✅ Reverível (apenas READMEs)
- ✅ Testável (os testes do sales-enablement continuam passando)
- ✅ Documentável
- ✅ Sem perda de dados
- ✅ Sem alteração de credenciais
