# Delegation

## Objetivo

Componente responsável por delegar tarefas entre agentes, gerenciar handoffs, implementar human-in-the-loop quando necessário e garantir que cada delegação tenha contexto, limites e critérios de sucesso claros.

## Princípios de Delegação

1. **Contexto completo:** Toda delegação inclui objetivo, restrições e critérios de sucesso.
2. **Limites claros:** O delegado sabe exatamente onde parar.
3. **Verificável:** O delegador pode rastrear o progresso.
4. **Recuperável:** Se o delegado falhar, há mecanismo de retry/retomada.
5. **Human-in-the-loop:** Quando risco ≥ médio, requer aprovação humana.

## Fluxo de Delegação

```
Hermes (orquestrador)
    ↓ delega com contexto
Agente Especialista
    ↓ executa
    ↓ retorna evidência
Hermes (valida + consolida)
    ↓ relatório
Usuário/ATLAS
```

## Modelo de Delegação

### Para agentes de conteúdo (Muse)
- Contexto: tom, público, canal
- Limites: não executar ações irreversíveis
- Entrega: copy, UX writing, documentação

### Para agentes de dados (Vector)
- Contexto: métricas necessárias, período
- Limites: não inventar dados
- Entrega: schemas, KPIs, dashboards

### Para agentes de vendas (sales-enablement)
- Contexto: objetivo comercial, lead, limites
- Limites: CRM update requer aprovação
- Entrega: sales score, next best action, follow-ups

### Para agentes de pesquisa (Oracle)
- Contexto: pergunta de pesquisa, escopo
- Limites: não assumir implementação
- Entrega: findings, recomendações, evidências

### Para QA (Aegis)
- Contexto: o que validar, critérios de aceitação
- Limites: não aprovar sem testes
- Entrega: relatório de qualidade, bugs encontrados

## Human-in-the-Loop Gates

Quando a delegação requer aprovação:
1. Ação proposta → Gate de aprovação
2. Aprovado → Executar + registrar
3. Rejeitado → Retornar com motivo
4. Pendente → Esperar decisão

## Padrão de Implementação

O padrão de delegação é demonstrado pelo fluxo:
- **ATLAS → HERMES → sales-enablement** (solicitação de Flávio passa pelo orquestrador para o agente de vendas)
- **Hermes → Vector → Nexus** (dados fluem do agente de dados para o agente de dashboards)

## Referência

Ver `HERMES-REESTRUTURACAO.md` para a hierarquia completa.
Ver `agents/atlas/README.md` para o papel do ATLAS na delegação.
Ver `docs/arquitetura-ecossistema-2026-09-04.md` para o modelo de autonomia.
