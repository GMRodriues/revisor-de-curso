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

## Evidencia Minima Por Achado

- severidade
- localizacao exata
- esperado
- observado
- screenshot ou log
- passos de reproducao
- criterio violado
- recomendacao

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

## Seguranca

Nao persistir:

- senha
- cookie
- token
- dados pessoais sensiveis
- respostas de alunos reais

