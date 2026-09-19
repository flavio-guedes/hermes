# Skills

## Objetivo

Catálogo de capacidades reutilizáveis do ecossistema HERMES. Skills são compartilhados entre agentes e não devem ser duplicadas por agente.

## Princípio

**Skill-first:** capacidades reutilizáveis antes de prompts ad-hoc.

## Catálogo

### Skills de Conteúdo
- frontend — Desenvolvimento frontend (Nexus)
- ui — Design de interface (Vanguard)
- copywriting — Redação de textos (Muse)
- reporting — Geração de relatórios (Vector)

### Skills de Operação
- research — Pesquisa e benchmarking (Oracle)
- data — Análise de dados e métricas (Vector)
- automation — Automação de fluxos (Hermes)
- security — Proteção de credenciais e acessos (Sentinel)
- qa — Validação e regressão (Aegis)

### Skills de Vendas e Marketing
- marketing — Estratégia de marketing (Pulse)
- sales-enablement — Gestão de leads e CRM (sales-enablement)
- crm — Integração com CRM
- lead-scoring — Qualificação de leads

### Skills de Engenharia
- architecture — Arquitetura de software (Forge)
- refactoring — Refatoração e redução de complexidade (Forge)

## Regras de Skill

1. Uma skill NÃO deve ser duplicada por agente
2. Skills são capacidades, não agentes
3. Skill-first antes de prompts ad-hoc
4. Catalogar quando nova skill é criada
5. Registrar qual agente utiliza qual skill

## Padrão de Implementação

Cada skill segue o padrão do sales-enablement:
- Python package com __init__.py
- Testes obrigatórios
- Documentação de uso
- Contrato de dados definido

## Referência

Ver `docs/arquitetura-ecossistema-2026-09-04.md` para o catálogo de 252 skills.
Ver `agents/` para os agentes que utilizam cada skill.
