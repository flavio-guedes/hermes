# Dashboards

## Objetivo

Interfaces e painéis operacionais do ecossistema HERMES.

## Princípio

Dashboard = interpretar os mesmos dados da operação.
Nunca inventar progresso.

## Dashboards Implementados

### 1. HERMES Main (`index.html`)
- **Design:** Glass-morphism (Space Grotesk + Inter + JetBrains Mono)
- **Tema:** Dark (#050509) com accent #00ffc8 e #ff2d7b
- **Sidebar:** 72px colapsável para 220px
- **Fontes:** Space Grotesk, Inter, JetBrains Mono
- **Efeitos:** Radial gradients, glass borders, blur
- **Status:** Funcional

### 2. CRM Command Center (`CRM/index.html`)
- **Design:** Cyberpunk neon (#6d5bff, #4f9dff)
- **Conteúdo:** Prospecção · Command Center
- **Features:** Botões WhatsApp/LinkedIn, tier High Ticket, funil sem etapa 00
- **Fonte:** FontAwesome, Inter
- **Status:** Funcional

### 3. Model Health (`dashboards/model-health.html`)
- **Design:** Dark theme
- **Conteúdo:** Saúde de modelos LLM
- **Dados:** `dashboards/model-health.json`
- **Métricas:** status FAILED, provider, model, error 429, retry_count
- **Status:** Funcional com dados reais

## Painéis Catalogados

Total: **98 painéis HTML** catalogados em `docs/inventario-paineis.md`
- 24 projeto
- 20 dashboard
- 19 ferramenta/agente
- 9 crm
- 8 relatório
- 5 projeto/operações
- 3 infraestrutura
- 1 outro
- 1 documento/design

## Fontes de Dados

| Dashboard | Fonte de Dados |
|---|---|
| HERMES Main | index.html (estático) |
| CRM | CRM/index.html |
| Model Health | model-health.json |
| Inventário | inventario-paineis.json |

## Regras

1. **Unificar fonte de dados** — Todos os dashboards consomem os mesmos dados operacionais
2. **Não inventar progresso** — Dashboard mostra estado real
3. **Filtros** — Projeto, contexto, período, tier, agente, bot, status
4. **Lentes temporais** — Agora, Programado, Histórico
5. **Evidências** — Não scores arbitrários; exemplos: "7 operações acima do tempo esperado"

## Deploy

- Padrão: GitHub Pages
- Repositório: `flavio-guedes/hermes`
- URLs mantidas nos repositórios existentes

## Catálogo de Painéis (referência)

Ver `docs/inventario-paineis.md` para lista completa de 98 painéis.
Ver `docs/inventario-paineis.json` para dados estruturados.

## Padrão de Implementação

Os dashboards são implementados como HTML/CSS/JS estáticos:
- Sem framework de backend
- Dados embutidos ou via JSON
- GitHub Pages para deploy
- Design system consistente
