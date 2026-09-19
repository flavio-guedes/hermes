# Execution Engine · Hermes

## Objetivo

Base única para execução, fila, capacidade, dependências, estados, resultados e evidências.

## Hierarquia

```text
Projeto → Contexto → Grupo → Agente → Bot → Tarefa → Operação → Execução
```

## Estados

Disponível · Executando · Aguardando · Pausado · Bloqueado · Erro · Concluído · Cancelado

## Operação

Deve representar, quando aplicável: id, projeto, contexto, tarefa, agente, bot, canal, prioridade, estado, dependências, horário programado, início, fim, progresso, tentativa, timeout, resultado, evidências, erro e histórico.

## Fila

Ordenação, prioridade, capacidade, dependências, previsão, reordenação segura e motivo de espera.

## Resiliência

Sempre que possível: checkpoint, retry, retomada, timeout, isolamento de falha e execução idempotente.

Não reescrever o sistema inteiro sem necessidade. Reutilizar e adaptar estruturas existentes.
