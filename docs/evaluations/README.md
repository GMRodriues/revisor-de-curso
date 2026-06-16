# Course Evaluation V2

Esta pasta contem a primeira versao dos arquivos de avaliacao baseados em relatorios reais.

Os documentos aqui ainda nao sao canonicos. Eles servem para transformar exemplos reais de revisao em criterios operacionais que depois podem virar automacao, checklist humano ou rubrica hibrida.

## Fontes Usadas

Relatorios analisados em 2026-05-17:

- `OPGPN1_VF.docx`
- `OPGPN2_VFLuuu.docx`
- `OPGPN3_VF (2).docx`
- `OPN3_VF.docx`

Extracoes locais:

- `artifacts/real-report-analysis/extracted/`
- `artifacts/real-report-analysis/extraction-summary.json`

## Estrutura Criada

- `real-report-patterns.md`: padroes encontrados nos 4 relatorios.
- `evaluation-workflow-v2.md`: fluxo proposto para o avaliador de cursos.
- `report-output-v2.md`: formato esperado para o relatorio final.
- `checks/`: familias de criterios que o avaliador deve aplicar.
- `schemas/evaluation-finding.schema.json`: formato inicial de um achado.
- `schemas/evaluation-run.schema.json`: formato inicial de uma execucao.
- `schemas/page-packet.schema.json`: formato de captura unica por pagina.

## Principio De Uso

Cada avaliacao deve separar:

1. Inventario do curso.
2. Funcionamento basico.
3. Extracao de material revisavel.
4. Revisao editorial, visual, acessibilidade, midia e atividades.
5. Relatorio final com localizacao, evidencia, criterio violado e recomendacao.

## Status

Draft inicial. Deve ser refinado com:

- exemplos de relatorios adicionais;
- conversa com quem executa a revisao hoje;
- calibracao de falsos positivos;
- testes em cursos reais.
