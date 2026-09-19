# Team

## Objetivo

Definir a equipe de agentes do Hermes, suas responsabilidades primárias, fluxos de comunicação, regras de coordenação e princípio de "um agente = uma responsabilidade primária".

## Equipe Completa

### Núcleo (Master)

| Agente | Responsabilidade Primária | Posição |
|---|---|---|
| Hermes | Orquestração Master | Centro de comando |
| Atlas | Chief of Staff / Interface Flávio | Camada pessoal |
| Strategos | Roadmap / Estratégia | Planejamento |

### Operação

| Agente | Responsabilidade Primária | Fluxo |
|---|---|---|
| Oracle | Research / Skills | Alimenta equipe com conhecimento |
| Vector | Dados / Métricas | Fornece dados para dashboards |
| Aegis | QA / Regressão | Valida tudo |
| Sentinel | Segurança | Protege credenciais e acessos |

### Entrega

| Agente | Responsabilidade Primária | Fluxo |
|---|---|---|
| Nexus | Frontend / Painéis | Implementa dashboards |
| Vanguard | UI / Visual | Define direção visual |
| Muse | Conteúdo / UX Writing | Texto das interfaces |
| sales-enablement | Vendas / Ativação | Lead management e CRM |

### Suporte

| Agente | Responsabilidade Primária |
|---|---|
| Forge | Arquitetura / Refatoração |
| Pulse | Marketing / Growth |

## Princípios

1. **UM AGENTE = UMA RESPONSABILIDADE PRIMÁRIA.**
2. Projeto, contexto, tier, canal e cliente não geram agentes duplicados.
3. Um mesmo agente pode operar em diferentes contextos.
4. Antes de remover ou fundir: verificar dependências, chamadas, integrações.

## Fluxos Confirmaos

- `USUÁRIO → ATLAS → HERMES → agentes especializados`
- `VECTOR → NEXUS → dashboard` (dados para visualização)
- `ORACLE → PULSE` (research para marketing)
- `VANGUARD → NEXUS` (direção visual para implementação)
- `MUSE → NEXUS` (texto para interface)
- `HERMES → SALES-ENABLEMENT` (orquestração para vendas)

## Regras de Coordenação

- **Nexus + Vanguard + Muse:** Vanguard define visual, Nexus implementa, Muse textualiza.
- **Vector + Pulse:** Pulse usa Vector para métricas e Oracle para research.
- **Atlas + Hermes:** Atlas é interface pessoal, Hermes é orquestrador técnico.
- **Aegis + Sentinel:** QA valida, Segurança protege — domínios distintos.

## Matriz de Sobreposição

| Agente | Responsabilidade | Sobreposição | Ação |
|---|---|---|---|
| Atlas | Interface pessoal | Conceitualmente sobrepõe Hermes | Manter como camada pessoal |
| Nexus + Vanguard + Muse | Frontend/UI/Content | Domínio visual | Regra clara de separação |
| Vector + Pulse | Dados/Métricas + Marketing | Pulse usa Vector | Fluxo correto |
| Oracle + Strategos | Research + Roadmap | Strategos pergunta, Oracle pesquisa | Fluxo correto |

## Referência

Ver `agents/` para os READMEs individuais de cada agente.
Ver `docs/restructuring/agents.md` para o inventário completo.
Ver `HERMES-REESTRUTURACAO.md` para os princípios da reestruturação.
