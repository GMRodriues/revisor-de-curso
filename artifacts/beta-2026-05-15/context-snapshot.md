# Beta Context Snapshot

Data: 2026-05-15

## Classificacao

- Fase atual: `phase-0-intake`
- Modo provavel para o primeiro teste: `discovery`
- Modo alternativo: `single-course-review`, se ja existir manifest confiavel ou escopo fechado de paginas

## Objetivo Do Projeto

Automatizar revisao mecanica de cursos online sem substituir a revisao humana. O fluxo deve navegar curso, modulo, aula e pagina; coletar evidencia verificavel; aplicar contratos objetivos; e gerar relatorio com severidade, reproducao e evidencia.

## Principios Ativos

- Evidencia antes de conclusao.
- Contratos objetivos antes de julgamento subjetivo.
- Navegacao deterministica antes de clique cego.
- Menor escopo verificavel antes de lote.
- Revisao humana no loop para calibrar falsos positivos e falsos negativos.
- Nao persistir credenciais, cookies, tokens ou dados pessoais.

## Estrutura Encontrada

- `AGENTS.md`: instrucoes locais do projeto.
- `skills/course-review-wizard/SKILL.md`: roteador principal da skill.
- `skills/course-review-wizard/modes/`: modos `discovery`, `single-course-review`, `batch-review` e `report-remediation`.
- `docs/contracts/`: contratos de execucao, evidencia, navegador e rubrica.
- `docs/phases/`: fases do fluxo de revisao.
- `docs/templates/`: modelos de manifest e relatorio.
- `artifacts/`: destino de evidencias e relatorios de runs.
- `scripts/`: reservado; nenhum runner implementado ainda.

## Contratos Obrigatorios

- `execution-loop-contract`: planejar antes de navegar, executar checklist item por item, registrar evidencia e fazer auditoria final.
- `evidence-contract`: cada pagina e cada achado precisam ter localizacao, URL/rota, screenshot/log e dados suficientes para reproducao.
- `browser-operator-contract`: operador retorna fatos da pagina, nao julgamento final.
- `review-rubric-contract`: classificar achados em `blocking`, `major`, `minor` ou `manual_review`.

## Estado Do Beta

O beta ainda nao pode revisar curso real sem dados de intake:

- URL da plataforma ou curso.
- Forma segura de login, preferencialmente perfil local ja logado.
- Curso alvo ou criterio de selecao.
- Escopo pequeno para MVP.
- Viewport alvo.
- Criterios obrigatorios de lancamento.

## Decisao Para Primeiro Teste

Comecar pequeno:

1. Rodar `discovery` em um curso pequeno.
2. Gerar manifest inicial.
3. Revisar uma aula ou modulo com `single-course-review`.
4. Produzir relatorio com evidencias.
5. Comparar com revisao humana e ajustar a rubrica.
