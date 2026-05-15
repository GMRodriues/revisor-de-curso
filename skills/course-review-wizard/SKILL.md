---
name: course-review-wizard
description: Automatiza revisao de cursos online em plataforma web, com descoberta de estrutura, navegacao por paginas, coleta de evidencia, aplicacao de rubrica e geracao de relatorio.
---

# Course Review Wizard

## Objetivo

Roteador principal para revisao automatizada de cursos. Escolhe um modo, aplica contratos de execucao/evidencia/rubrica, e produz saidas auditaveis.

## Contratos Obrigatorios

Ler antes de executar qualquer modo:

1. `docs/contracts/execution-loop-contract.md`
2. `docs/contracts/evidence-contract.md`
3. `docs/contracts/browser-operator-contract.md`
4. `docs/contracts/review-rubric-contract.md`

## Router

1. Classificar o pedido em exatamente um modo.
2. Ler apenas o modo selecionado.
3. Criar checklist antes de operar navegador.
4. Executar um item por vez.
5. Fazer `Final Audit`.

## Modos

1. `discovery`
   - Arquivo: `modes/mode-discovery.md`
   - Use quando ainda nao existe manifest confiavel do curso.

2. `single-course-review`
   - Arquivo: `modes/mode-single-course-review.md`
   - Use quando o escopo e revisar um curso ou modulo ja identificado.

3. `batch-review`
   - Arquivo: `modes/mode-batch-review.md`
   - Use quando o usuario quer revisar varios cursos/modulos em lote.

4. `report-remediation`
   - Arquivo: `modes/mode-report-remediation.md`
   - Use quando ja existe relatorio e o trabalho e revisar, consolidar ou preparar plano de correcao.

## Tie-Breakers

- Se nao ha manifest, comece por `discovery`.
- Se ha um curso pequeno definido para MVP, use `single-course-review`.
- Se a lista tem varios cursos e o fluxo ja foi calibrado, use `batch-review`.
- Se o usuario trouxe exemplos de revisao humana, use primeiro para calibrar a rubrica antes de rodar lote.

## Saida Padrao

Retornar:

1. escopo revisado
2. cobertura
3. status sugerido
4. achados por severidade
5. evidencias principais
6. itens para revisao humana
7. proximas acoes
