# Browser Operator Contract

## Proposito

Definir como o projeto deve operar a plataforma web de cursos sem misturar navegacao, coleta de evidencia e julgamento de qualidade.

## Superficies Permitidas

O runner pode usar uma destas superficies, conforme disponibilidade:

- navegador local com perfil logado
- browser automation por Playwright
- plugin/browser control da sessao atual
- API ou manifest da plataforma, quando existir

Preferir dados estruturados da plataforma quando existirem. Usar clique por setas como fallback, nao como primeira opcao.

## Regras De Navegacao

1. Resolver curso, modulo, aula e pagina antes de revisar.
2. Aguardar estabilidade antes de capturar screenshot.
3. Registrar o metodo de navegacao usado.
4. Nao rodar dois comandos concorrentes na mesma pagina/sessao.
5. Detectar loops, paginas duplicadas e indices inconsistentes.
6. Parar com blocker quando a plataforma exigir acao destrutiva, pagamento ou dado sensivel.

## Coleta Por Pagina

Capturar:

- URL ou rota atual
- titulo/indice visivel
- screenshot
- texto visivel do DOM
- console errors
- network failures relevantes
- estado de imagens
- estado de videos ou players
- tempo ate estabilidade quando possivel

## Wait/Stability

Uma pagina so esta pronta para review quando:

- navegacao terminou
- loaders principais sumiram ou estabilizaram
- imagens essenciais terminaram de carregar ou falharam explicitamente
- videos tiveram metadata carregada quando presentes
- nao houve mudanca visual relevante durante uma janela curta de estabilidade

Se a pagina fica instavel, registrar `blocked` ou `manual_review` em vez de adivinhar.

## Midia

### Imagem

- verificar `naturalWidth` e `naturalHeight`
- verificar falha de request
- capturar screenshot quando imagem parece quebrada, cortada ou fora do layout

### Video

- verificar player
- verificar metadata/duracao
- testar inicio de playback quando permitido
- registrar se autoplay, bloqueio de browser ou permissao impede teste

## Seguranca

Nunca persistir em artefatos:

- senha
- token
- cookie
- dados pessoais sensiveis
- respostas reais de alunos
- informacao de pagamento

Se credenciais forem necessarias, usar perfil local ou mecanismo seguro definido pelo humano.

## Saida Do Operador

O operador deve retornar fatos, nao julgamento final:

- `visited`
- `loaded`
- `navigationWorked`
- `mediaStatuses`
- `consoleErrors`
- `networkFailures`
- `screenshots`
- `rawObservations`

O julgamento final pertence ao Review Engine e a rubrica.

