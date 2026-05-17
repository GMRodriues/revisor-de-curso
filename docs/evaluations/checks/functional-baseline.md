# Checks: Functional Baseline

## Objetivo

Confirmar que o curso esta funcional antes de entrar na revisao editorial mais fina.

Esta etapa nao tenta julgar qualidade pedagogica. Ela responde: o formando consegue abrir, navegar e consumir o que esta na pagina?

## Unidade De Revisao

Aplicar por:

- curso;
- trilha/modulo;
- aula/pagina;
- recurso dentro da pagina.

## Checks Por Pagina

- URL abre.
- Titulo ou identificador da pagina aparece.
- Conteudo principal carregou.
- Nao ficou preso em loader.
- Nao ha erro visual bloqueante.
- Navegacao anterior/proxima funciona ou esta corretamente ausente.
- Sidebar/menu/lista de aulas aparece quando esperado.
- Pagina nao redireciona para local errado.

## Checks Por Tipo De Conteudo

### Texto

- Texto principal aparece.
- Texto nao esta cortado.
- Texto nao esta oculto atras de outro elemento.
- Texto pode ser copiado quando isso for necessario para revisao.

### Imagem

- Imagem carrega.
- Imagem nao aparece quebrada.
- Imagem nao esta ilegivel.
- Imagem nao esta fora de contexto visual obvio.

### Video

- Player aparece.
- Thumbnail ou frame inicial aparece.
- Controles aparecem.
- Duracao aparece quando a plataforma exibe duracao.
- Playback fica para fase de midia.

### Recurso Interativo

- Recurso aparece.
- Instrucoes aparecem.
- Recurso responde ao clique/acao basica.
- Nao exige comportamento impossivel ou nao explicado.

### Atividade/Questao

- Enunciado aparece.
- Alternativas/campos aparecem.
- Botao de resposta/submissao aparece.
- Feedback aparece quando testado em fase especifica.

### Link/Ficheiro

- Link aparece.
- Link tem texto identificavel.
- Download ou abertura funciona quando testado.

## Saida

Cada pagina recebe um status:

- `passed`: funcional nos checks basicos.
- `failed`: falha mecanica verificavel.
- `blocked`: nao foi possivel acessar/testar.
- `manual_review`: carregou, mas precisa julgamento humano.

## Evidencia Minima

- URL.
- Screenshot.
- DOM/texto visivel quando disponivel.
- Logs relevantes.
- Tipo de conteudo esperado.
- Tipo de conteudo observado.
