# Glossario Operacional

Este projeto deve ser operado em portugues. Termos em ingles so devem permanecer quando forem nomes de arquivos, campos JSON, enums ou identificadores tecnicos que podem ser usados por automacao.

## Termos Humanos

| Termo tecnico | Termo operacional em portugues |
| --- | --- |
| course review | teste beta de curso |
| review | revisao |
| finding | achado ou ocorrencia |
| evidence | evidencia |
| coverage | cobertura |
| report | relatorio |
| run | execucao |
| runner | executor |
| page packet | pacote de pagina |
| single-pass capture | captura em passagem unica |
| browser operator | operador de navegador |
| review engine | motor de revisao |
| report builder | gerador de relatorio |
| course manifest | manifest do curso |
| checks | verificacoes |
| guardrails | protecoes |
| final audit | auditoria final |
| manual review | revisao humana |

## Identificadores Mantidos Em Ingles

Manter em ingles por enquanto:

- nomes de arquivos ja referenciados, como `evaluation-run.schema.json`, `page-packet.schema.json` e `mode-ina-nau-course-review.md`;
- campos JSON, como `runId`, `pageId`, `coverage`, `findings`, `artifacts`, `contextScreenshot`;
- enums tecnicos, como `blocking`, `major`, `minor`, `manual_review`, `passed`, `failed`, `blocked`;
- nomes de diretorios que ja funcionam como contrato tecnico, como `checks/`, `findings/`, `pages/` e `downloads/`.

Se uma automacao futura exigir nomes em portugues tambem para campos JSON ou arquivos, criar uma versao nova de schema e um plano de migracao. Nao renomear campos tecnicos de forma avulsa.

