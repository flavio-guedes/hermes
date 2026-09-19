# Tests

## Objetivo

Registro de testes, validações e pipeline de qualidade do ecossistema HERMES.

## Princípio

**Aegis:** Nenhum projeto crítico deve ser considerado concluído sem passar por QA.

## Framework Atual

### Testes Passando
- **Agente:** sales-enablement
- **Framework:** pytest 9.1.1
- **Python:** 3.14.7
- **Testes:** 11/11 passando
- **Cobertura:** CRM adapter, lead scoring, deal health, next-best-action, followups

### Padrão de Testes

Cada agente deve ter:
- Testes unitários para cada módulo
- Testes de integração para fluxos entre agentes
- Testes de regressão para mudanças existentes
- Testes de contrato para validação de dados

## Estrutura de Testes (padrão sales-enablement)

```
agents/<agente>/
├── tests/
│   ├── __init__.py
│   ├── test_<modulo>.py
│   └── __pycache__/
├── <modulo>/
│   ├── __init__.py
│   └── engine.py
└── README.md
```

## Critérios de Qualidade

1. **Teste após cada alteração relevante**
2. **Corrigir se necessário antes de documentar**
3. **Nunca declarar progresso sem evidência**
4. **Registrar resultado de cada teste**
5. **Manter histórico de testes**

## Padrão de Implementação (sales-enabling)

Os testes do sales-enablement demonstram:
- Lead scoring com diferentes cenários (quente, frio, parado)
- Deal health evaluation
- Next-best-action generation
- CRM upsert/get/add_interaction
- Pending followups

```bash
# Executar testes
PYTHONPATH="agents:." python3 -m pytest agents/sales-enablement/tests/ -v
```

## Regras de QA

1. Aegis valida antes de qualquer deploy
2. Regressão testada para cada mudança
3. Evals para workflows repetitivos
4. Sem pipeline de avaliação completa ainda (futuro)

## Testes Futuros (planejados)

- Unit tests para core modules
- Integration tests entre agentes
- Regression test suite
- QA report gerado automaticamente
- Eval pipeline para workflows

## Referência

Ver `agents/sales-enablement/tests/test_sales_enablement_agent.py` para referência.
Ver `agents/aegis/README.md` para o papel do QA.
