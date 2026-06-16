# Contrato De Evidencia

## Proposito

Todo resultado de revisao precisa ser verificavel por uma pessoa sem repetir todo o curso manualmente.

## Evidencia Minima Por Pagina

- `courseId` ou nome do curso
- `moduleId` ou nome do modulo
- `lessonId` ou nome da aula
- `pageIndex` ou identificador da pagina
- URL ou rota
- timestamp
- viewport
- caminho da captura de tela
- texto visivel extraido, quando disponivel
- erros de console
- falhas de rede relevantes
- estado de imagens
- estado de videos, quando existirem

Para revisoes INA/NAU, a evidencia minima por pagina deve ser salva como `pacote de pagina`, conforme `docs/contracts/single-pass-capture-contract.md`. O pacote deve ser suficiente para permitir revisao offline de texto, layout, midia, links, documentos, recursos interativos e atividades sempre que possivel.

## Evidencia Minima Por Achado

- severidade
- localizacao exata
- esperado
- observado
- captura de tela contextual obrigatoria, mostrando a area ao redor do erro em tamanho suficiente para entender a pagina
- captura de tela focada do elemento, quando isso ajudar a ver o detalhe do erro
- log, quando o erro for tecnico e nao visual
- passos de reproducao
- criterio violado
- recomendacao
- referencia ao `pacote de pagina` ou artefato interno que suporta o achado

## Capturas De Tela

Capturar pelo menos:

- captura de tela de pagina inteira quando possivel
- captura da viewport para problemas visuais
- captura especifica do elemento quando necessario

Para cada achado, capturar tambem uma captura de tela contextual. Essa captura nao deve cortar apenas o pixel/texto com problema: deve incluir a area visual em volta, como titulo da pagina, bloco de conteudo, controles proximos ou parte da navegacao lateral/topo quando isso ajudar a localizar o erro. A intencao e permitir que uma pessoa entenda o problema visualmente sem reabrir a plataforma.

A captura focada pode existir como complemento, mas nao substitui a captura contextual.

## Registros De Log

Registrar:

- erros JavaScript
- requisicoes com estado 4xx/5xx relevantes
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
