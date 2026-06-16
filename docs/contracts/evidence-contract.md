# Evidence Contract

## Proposito

Todo resultado de review precisa ser verificavel por uma pessoa sem repetir todo o curso manualmente.

## Evidencia Minima Por Pagina

- courseId ou nome do curso
- moduleId ou nome do modulo
- lessonId ou nome da aula
- pageIndex ou identificador da pagina
- URL ou rota
- timestamp
- viewport
- screenshot path
- texto visivel extraido, quando disponivel
- console errors
- network failures relevantes
- status de imagens
- status de videos, quando existirem

Para revisoes INA/NAU, a evidencia minima por pagina deve ser salva como `page packet`, conforme `docs/contracts/single-pass-capture-contract.md`. O pacote deve ser suficiente para permitir revisao offline de texto, layout, midia, links, documentos, recursos interativos e atividades sempre que possivel.

## Evidencia Minima Por Achado

- severidade
- localizacao exata
- esperado
- observado
- screenshot ou log
- passos de reproducao
- criterio violado
- recomendacao
- referencia ao `page packet` ou artefato interno que suporta o achado

## Screenshots

Capturar pelo menos:

- screenshot de pagina inteira quando possivel
- screenshot viewport para problemas visuais
- screenshot especifico do elemento quando necessario

## Logs

Registrar:

- erros JavaScript
- requests com status 4xx/5xx relevantes
- recursos quebrados de imagem, video, fonte ou CSS
- tempo de carregamento quando for anormal

## Reutilizacao De Evidencia

Fases de avaliacao devem consultar primeiro os artefatos ja salvos. Repetir navegacao e permitido apenas quando a evidencia estiver incompleta, obsoleta, ilegivel, bloqueada ou quando houver reteste apos correcao.

## Seguranca

Nao persistir:

- senha
- cookie
- token
- dados pessoais sensiveis
- respostas de alunos reais
