# HERMES · REESTRUTURAÇÃO

## Objetivo

Reestruturar o Hermes como um sistema operacional orientado a:

**dados → contexto → decisão → execução → evidência → histórico → aprendizado → evolução**

A reestruturação deve reduzir duplicação, tornar a execução observável e permitir que o Hermes evolua sem depender de reconstrução manual de contexto.

## Princípios

1. Uma fonte de verdade para estado operacional.
2. Um agente = uma responsabilidade primária.
3. Projeto não é agente.
4. Contexto não é agente.
5. Bot é uma instância contextual de um agente.
6. Operação é um registro/estado de trabalho, não necessariamente um menu.
7. Dashboard interpreta os mesmos dados da operação.
8. Conclusão exige evidência verificável.
9. Mudanças devem ser incrementais e testáveis.
10. Mudanças destrutivas, perda de dados, credenciais ou quebra de integração exigem bloqueio.

## Hierarquia

```text
PROJETO
  ↓
CONTEXTO
  ↓
GRUPO
  ↓
AGENTE
  ↓
BOT / INSTÂNCIA
  ↓
TAREFA
  ↓
OPERAÇÃO
  ↓
EXECUÇÃO
```

## Contexto e público

Projetos devem permanecer isolados.

```text
EPQ
└── Tier: Perfil
    ├── PMERJ
    ├── GCM
    ├── INSS
    └── Outros
```

```text
FLÁVIO
├── Tier: Segmento
└── Tier: Temperatura
```

Tiers são dimensões de segmentação, não níveis de permissão.

## Agentes

Antes de criar um agente novo, verificar responsabilidade, sobreposição, prompt, modelo, provider, ferramentas, skills, integrações, automações, chamadas, projetos/contextos e evidência de uso.

Classificar como: ativo, parcial, inativo, órfão, duplicado, sobreposto, indefinido ou quebrado.

A consolidação deve ocorrer por capacidade real, não pelo nome.

## Execution Engine

Deve representar tarefa, operação, execução, estado, prioridade, fila, capacidade, dependências, início, progresso, pausa, retomada, retry, timeout, erro, resultado, evidência e histórico.

Estados mínimos:

```text
Disponível
Executando
Aguardando
Pausado
Bloqueado
Erro
Concluído
Cancelado
```

## Fila e capacidade

A fila deve responder o que está executando, aguardando, programado, por que está aguardando, capacidade atual, previsão de início e dependências.

Prioridades: Urgente, Alta, Normal, Baixa. Prioridade não pode quebrar dependências.

Capacidade:

```text
Disponível
Parcial
Saturado
Bloqueado
Indisponível
```

## Command Bar

Entrada operacional compacta e contextual:

> O que você quer fazer ou buscar?

Deve aceitar buscar, perguntar, executar, programar, colocar na fila, diagnosticar, otimizar, criar sprint, criar automação, criar template e `me mostre`.

Atalhos desejáveis: `⌘K`, `/`, `Esc`, `⌘Enter`.

Deve utilizar o Execution Engine e não virar um chat gigante.

## Dados e filtros

Filtros devem cruzar projeto, contexto, período, tier, subtier, canal, agente, bot, status, origem, operação e prioridade.

Lentes temporais: Agora, Programado, Histórico.

Exemplo:

```text
EPQ + Perfil PMERJ + WhatsApp + Mercúrio + Em execução + Hoje
```

## Dashboard

Dashboard = entender e decidir.

Deve responder o que está acontecendo, executando, aguardando, programado, concluído, com erro, onde está o gargalo, o que exige atenção e o que mudou.

Não usar scores arbitrários. Preferir evidências como `7 operações acima do tempo esperado`.

## Raio-X

Olha para dentro do Hermes: saúde operacional, competências, gargalos, performance, arquitetura, agentes, modelos, automações, integrações e alertas.

Alertas: Crítico, Atenção, Oportunidade, Evolução, Conhecimento.

## Radares

Olham para fora: Skills, Templates, Copy, Ferramentas, Modelos, UX/UI, Arquitetura, Automação, Performance e Tendências.

Pergunta central:

> Isso pode melhorar alguma coisa que o Hermes já faz?

Descobertas podem gerar oportunidades e experimentos, mas não devem instalar ou alterar componentes automaticamente sem regras.

## Templates e Sprints

Categorias: Fluxos, Automações, Sprints, Agentes, CRM, Marketing.

Exemplos: Follow-up de lead, Triagem, Recuperação, Qualificação, Atendimento → CRM, Lead → WhatsApp → CRM, Sprint de aquisição, conteúdo, CRM e automação.

Sprint: objetivo, período, meta, etapas, agentes, métricas e critérios de conclusão.

## Bot Mode

Bot é uma instância operacional contextual, não um agente duplicado.

```text
Mercúrio → EPQ → Bot Follow-up PMERJ
Mercúrio → Flávio → Bot CRM
```

Bot Builder: nome, agente base, projeto, contexto, função, canais, capacidades, autonomia, regras e limites.

Estados: Disponível, Raciocinando, Executando, Aguardando, Delegando, Em comunicação, Bloqueado, Erro, Pausado.

## Grupos e multiagente

Grupo é uma composição contextual de agentes/bots. Deve possuir objetivo, contexto, membros, supervisor, ordem, regras e delegação.

## Autonomia

Níveis: Assistido, Semi-autônomo, Autônomo, Autônomo com limites.

## Experimentos

```text
Hipótese → Mudança → Teste → Métrica → Resultado → Decisão → Adotar/Reverter
```

## Memória de decisões

```text
Contexto → Evidência → Decisão → Responsável → Resultado
```

## Me mostre

Deve demonstrar evidências reais da execução: arquivos alterados, operações, etapas, testes, resultados, métricas, commits e alterações de estado.

## Fluxo geral

```text
COMMAND BAR / CONTEXTO
          ↓
       DADOS
          ↓
      DECISÃO
          ↓
  EXECUTION ENGINE
          ↓
 FILA + CAPACIDADE
          ↓
 AGENTES / BOTS
          ↓
      EXECUÇÃO
          ↓
     VALIDAÇÃO
          ↓
      EVIDÊNCIA
          ↓
      HISTÓRICO
          ↓
   RAIO-X / RADARES
          ↓
   OPORTUNIDADES
          ↓
    EXPERIMENTOS
          ↓
 MEMÓRIA / EVOLUÇÃO
```

## Roadmap

00 Auditoria
01 Base documental
02 Painel de reestruturação
03 Auditoria e consolidação de agentes
04 Execution Engine
05 Fila e capacidade
06 Command Bar
07 Dados e filtros
08 Dashboard
09 Raio-X
10 Radares
11 Templates e Sprints
12 Bot Mode
13 Grupos e orquestração
14 Experimentos
15 Memória de decisões
16 Autonomia

## Regra de implementação

```text
INSPECIONAR → PLANEJAR → IMPLEMENTAR → TESTAR → DOCUMENTAR → ATUALIZAR PAINEL → COMMIT → PRÓXIMA ETAPA
```

Não avançar cegamente. Se uma etapa tiver risco estrutural, registrar bloqueio e continuar apenas com etapas independentes e seguras.

## Critério de conclusão

Uma etapa só é concluída quando houver implementação ou evidência correspondente, teste, documentação, status atualizado, arquivos identificados e commit quando aplicável.

O painel nunca deve inventar progresso.
