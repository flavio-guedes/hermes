# Governance

## Objetivo

Definir políticas, gates de aprovação, níveis de risco e regras de autonomia para o ecossistema Hermes.

## Princípios

1. Nenhuma ação irreversível sem aprovação explícita quando risco ≥ médio.
2. Nenhuma execução aberta sem timeout.
3. Nenhuma ação artificial só para gerar atividade.
4. Toda saída sensível passa por policy.
5. Autonomia só aumenta após observabilidade + recuperação estabelecidas.

## Modelo de Governança

| Ação | Pode executar sozinho | Log + alerta | Precisa aprovação | Não pode |
|---|---|---|---|---|
| Enviar mensagem | mensagens operacionais low-risk | mensagens comerciais | mensagens sensíveis/irreversíveis | spam |
| Publicar | branches/previews | deploy Pages simples | deploy produção/campanha | mudança sem review |
| Excluir/alterar código | não | não | sempre | — |
| Alterar CRM | não | sim | sempre | exclusão massiva sem conferência |
| Alterar campanhas | não | sim | sim | pausar/cancelar sem motivo |
| Candidatar-se | não | não | sempre | — |
| Gastar dinheiro | não | não | sempre | — |
| Acessar dados sensíveis | não | sim | sim | vazamento/export irrestrito |
| Autenticar serviços | não | não | sempre | compartilhar credenciais |
| Tarefa externa irreversível | não | não | sempre | — |

## Níveis de Autonomia

| Nível | Descrição | Exemplo |
|---|---|---|
| 0 | Manual | decisão estratégica |
| 1 | Assistido | proposta com rascunho |
| 2 | Automação determinística | sync/merge de JSONs |
| 3 | Agente supervisionado | job hunter, founder radar |
| 4 | Agente autônomo com guardrails | follow-up com limite baixo |
| 5 | Operação autônoma | não aplicável hoje |

**Regra:** Subir de nível só após: observabilidade, governança, recuperação.

## Approval Gates

- Gate de risco: toda ação com risco ≥ médio requer aprovação.
- Gate de dado: alteração de dados de CRM/produto requer confirmação.
- Gate de deploy: publish em produção requer review.
- Gate de custo: gastar acima de threshold requer aprovação.

## Referência

Ver `docs/arquitetura-ecossistema-2026-09-04.md` para detalhes completos do modelo de governança.

Ver `docs/restructuring/HERMES-REESTRUTURACAO.md` para princípios da reestruturação.
