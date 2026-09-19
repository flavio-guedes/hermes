# Agentes · Hermes

## Objetivo

Inventariar os agentes reais e consolidá-los por responsabilidade.

## Princípio

**Um agente = uma responsabilidade primária.**

Projeto, contexto, tier, canal e cliente não devem gerar agentes duplicados.

## Fontes

- **Local (Drive):** `03 - Projects/GitHub Map/hermes/agents/` — 12 agentes
- **GitHub:** `flavio-guedes/hermes` — 13 agentes
- **Diferença:** GitHub tem `sales-enablement` que não existe localmente

## Inventário completo

| # | Agente | Função declarada | Funcional real | Tipo | Status |
|---|---|---|---|---|---|
| 1 | Hermes | Master / Orquestração | README.md | DOCUMENTAÇÃO | Documentado |
| 2 | Atlas | Chief of Staff / Flávio | README.md | DOCUMENTAÇÃO | Documentado |
| 3 | Oracle | Research / Skills | README.md | DOCUMENTAÇÃO | Documentado |
| 4 | Nexus | Frontend / Painéis | README.md + index.html | PARCIAL | Documentado + HTML |
| 5 | Forge | Arquitetura / Refatoração | README.md | DOCUMENTAÇÃO | Documentado |
| 6 | Vector | Dados / Métricas | README.md + model-health.json | PARCIAL | Documentado + JSON |
| 7 | Aegis | QA / Regressão | README.md | DOCUMENTAÇÃO | Documentado |
| 8 | Sentinel | Segurança | README.md | DOCUMENTAÇÃO | Documentado |
| 9 | Vanguard | UI / Visual | README.md | DOCUMENTAÇÃO | Documentado |
| 10 | Strategos | Roadmap / Estratégia | README.md | DOCUMENTAÇÃO | Documentado |
| 11 | Muse | Conteúdo / UX Writing | README.md | DOCUMENTAÇÃO | Documentado |
| 12 | Pulse | Marketing / Growth | README.md | DOCUMENTAÇÃO | Documentado |
| 13 | sales-enablement | Vendas/Ativação | 12 PY files, 11 tests | **IMPLEMENTADO** | Python funcional |

## Classificações

- **Implementado:** sales-enablement (12 arquivos Python, 11 testes passando)
- **Ativo (evidência funcional):** Nexus (HTML), Vector (JSON), sales-enablement (Python)
- **Documentado:** Hermes, Atlas, Oracle, Forge, Aegis, Sentinel, Vanguard, Strategos, Muse, Pulse
- **Parcial:** Nexus, Vector
- **Órfão:** Nenhum
- **Duplicado:** Nenhum
- **Sobreposto:** Atlas/Hermes (conceitual)
- **Quebrado:** Core modules (agora preenchidos)

## Matriz de sobreposição

| Agente | Responsabilidade | Sobreposição | Ação |
|---|---|---|---|
| Hermes | Orquestração Master | Interface pessoal com Atlas | Manter como orquestrador técnico |
| Atlas | Interface pessoal Flávio | Conceitualmente sobrepõe Hermes | Definir fronteira clara |
| Nexus + Vanguard + Muse | Frontend/UI/Content | Sobreposição no domínio visual | Vanguard → direção, Nexus → implementa, Muse → textualiza |
| Vector + Pulse | Dados/Métricas + Marketing | Pulse usa Vector | Fluxo correto, manter |
| Oracle + Strategos | Research + Roadmap | Strategos pergunta, Oracle pesquisa | Fluxo correto, manter |
| Aegis + Sentinel | QA + Segurança | Domínios distintos | Manter separados |

## Dependências confirmadas

- **VECTOR → Nexus** (dados para dashboards)
- **VECTOR → Pulse** (métricas para marketing)
- **ORACLE → Pulse** (research para marketing)
- **VANGUARD → NEXUS** (direção visual para implementação)
- **ATLAS → HERMES** (solicitações de Flávio passam pelo orquestrador)

## Regra de consolidação

Antes de remover ou fundir agentes: verificar chamadas, automações, integrações, dependências e contextos; testar e registrar decisão.

## Agente adicional (GitHub only)

**sales-enablement**: Presente no repositório GitHub (`flavio-guedes/hermes`) e sincronizado localmente. 12 arquivos Python, 11 testes passando. Serve como template de implementação para todos os outros agentes.

## Template de Implementação

O sales-enabling demonstra o padrão que todos os agentes devem seguir:
- Python package com `__init__.py`
- `CRMAdapter` para state management (JSON-based)
- `IntelligenceEngine` com sales_score, deal_health, next_best_action
- `FollowupEngine` com scheduling
- `AnalyticsEngine` com pipeline_summary, conversion_metrics
- Tests com pytest (padrão obrigatório)
- Agent docs (system.md, rules.md, workflows.md)
- Playbooks (ICPs, personas, objections, messaging)

## Nota sobre Sync

A cópia local estava atrasada em relação ao GitHub. Sincronização concluída em 2026-09-19 com 6 commits adicionais.
