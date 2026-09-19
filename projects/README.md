# Projects

## Objetivo

Registro de projetos concretos do ecossistema HERMES. Cada projeto mantém seu contexto isolado.

## Princípio

**Projeto não é agente.** Projetos são contextos onde agentes operam.

## Estrutura de Registro

Cada projeto deve ter:
- objetivo
- responsáveis
- entregáveis
- status
- links de dashboards/repos

## Projetos Conhecidos

### EPQ (Educação e Qualificação Profissional)
- Contexto: Perfil PMERJ, GCM, INSS
- Tiers: Perfil, Segmento, Temperatura
- Dashboards: plano de ads, funil, follow-up
- Agentes: sales-enablement, Vector, Nexus

### Flávio (Pessoal/Profissional)
- Contexto: Segmento, Temperatura
- Áreas: Marketing, Vendas, Conteúdo, Prospecção
- Agentes: Atlas, Oracle, Pulse

### Job Hunter
- Contexto: Vagas e candidaturas
- Frequência: Diária
- Agentes: Vector, founder-radar

### Founder Radar
- Contexto: Parceiros e oportunidades
- Frequência: Diária
- Agentes: Vector, founder-radar

### Prospecção
- Contexto: B2B, FoodHub, LinkedIn
- Ferramentas: browser automation, HTML
- Agentes: sales-enablement, Nexus

## Regras

1. Projetos permanecem isolados
2. Um projeto pode usar múltiplos agentes
3. Um agente pode operar em múltiplos projetos
4. Contexto não é agente
5. Tier é dimensão de segmentação, não nível de permissão

## Dados de Referência

Ver `docs/integration-manifest.json` para links de projetos EPQ.
Ver `docs/arquitetura-ecossistema-2026-09-04.md` para o mapa de projetos.
Ver `docs/inventario-paineis.md` para dashboards de cada projeto.
