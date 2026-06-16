---
name: curso-beta-test
description: Automatiza revisao de cursos online em plataforma web, com descoberta de estrutura, navegacao por paginas, coleta de evidencia, aplicacao de rubrica e geracao de relatorio.
---

# Curso Beta Test

## Objetivo

Roteador principal para revisao automatizada de cursos. Escolhe um modo, aplica contratos de execucao/evidencia/rubrica, e produz saidas auditaveis.

Para a frente atual INA/NAU, o objetivo operacional e transformar uma URL de curso NAU em um relatorio Betatest INA quase pronto para curadoria humana. A navegacao principal deve seguir estrategia de captura unica por pagina: ao passar por uma pagina, coletar evidencias visuais, texto, DOM, midia, links, documentos e dados revisaveis suficientes para as fases seguintes trabalharem offline sempre que possivel.

## Contratos Obrigatorios

Ler antes de executar qualquer modo:

1. `docs/contracts/execution-loop-contract.md`
2. `docs/contracts/evidence-contract.md`
3. `docs/contracts/single-pass-capture-contract.md`
4. `docs/contracts/browser-operator-contract.md`
5. `docs/contracts/review-rubric-contract.md`

Para pedidos INA/NAU, ler tambem:

1. `docs/glossario-operacional.md`
2. `docs/products/ina-nau-mooc/objective-and-plan.md`
3. `docs/products/ina-nau-mooc/requirements-and-checklist.md`
4. `docs/templates/ina-nau-run-structure.md`
5. `docs/templates/page-packet.template.json`
6. `docs/templates/ina-betatest-report-template.md`

## Roteador

1. Classificar o pedido em exatamente um modo.
2. Ler apenas o modo selecionado.
3. Criar checklist antes de operar navegador.
4. Executar um item por vez.
5. Fazer `Auditoria Final`.

## Modos

Os identificadores dos modos e nomes de arquivos continuam em ingles por compatibilidade com artefatos e automacoes futuras. O nome operacional em portugues aparece na primeira linha de cada arquivo de modo.

1. `ina-nau-course-review`
   - Arquivo: `modes/mode-ina-nau-course-review.md`
   - Use quando o usuario fornecer uma URL de curso NAU/INA ou pedir relatorio Betatest INA.
   - Este e o modo preferencial da frente atual.

2. `discovery`
   - Arquivo: `modes/mode-discovery.md`
   - Use quando ainda nao existe manifest confiavel do curso.

3. `single-course-review`
   - Arquivo: `modes/mode-single-course-review.md`
   - Use para cursos fora da frente INA/NAU ou quando o usuario pedir explicitamente uma revisao generica.

4. `batch-review`
   - Arquivo: `modes/mode-batch-review.md`
   - Use quando o usuario quer revisar varios cursos/modulos em lote.

5. `report-remediation`
   - Arquivo: `modes/mode-report-remediation.md`
   - Use quando ja existe relatorio e o trabalho e revisar, consolidar ou preparar plano de correcao.

## Criterios De Desempate

- Se ha URL de curso NAU/INA, curso MOOC INA, modelo Betatest ou caderno de encargos INA, use `ina-nau-course-review`.
- Se nao ha manifest, comece por `discovery`.
- Se ha um curso pequeno definido para MVP, use `single-course-review`.
- Se a lista tem varios cursos e o fluxo ja foi calibrado, use `batch-review`.
- Se o usuario trouxe exemplos de revisao humana, use primeiro para calibrar a rubrica antes de rodar lote.

## Saida Padrao

Retornar:

1. escopo revisado
2. cobertura
3. estado sugerido
4. achados por severidade
5. evidencias principais
6. itens para revisao humana
7. proximas acoes

Para `ina-nau-course-review`, a saida principal deve ser o relatorio Betatest INA. JSON, snapshots de DOM, capturas de tela e registros de log sao anexos internos de rastreabilidade.
