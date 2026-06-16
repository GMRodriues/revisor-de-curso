# Contrato Do Operador De Navegador

## Proposito

Definir como o projeto deve operar a plataforma web de cursos sem misturar navegacao, coleta de evidencia e julgamento de qualidade.

## Superficies Permitidas

O executor pode usar uma destas superficies, conforme disponibilidade:

- navegador local com perfil logado
- automacao de navegador por Playwright
- plugin/controle de navegador da sessao atual
- API ou manifest da plataforma, quando existir

Preferir dados estruturados da plataforma quando existirem. Usar clique por setas como alternativa, nao como primeira opcao.

## Regras De Navegacao

1. Resolver curso, modulo, aula e pagina antes de revisar.
2. Aguardar estabilidade antes de capturar screenshot.
3. Registrar o metodo de navegacao usado.
4. Nao rodar dois comandos concorrentes na mesma pagina/sessao.
5. Detectar loops, paginas duplicadas e indices inconsistentes.
6. Parar com blocker quando a plataforma exigir acao destrutiva, pagamento ou dado sensivel.
7. Em revisoes INA/NAU, tratar a primeira passagem por pagina como captura principal: coletar pacote de pagina completo antes de avancar.

## Coleta Por Pagina

Capturar:

- URL ou rota atual
- titulo/indice visivel
- captura de tela
- texto visivel do DOM
- erros de console
- falhas de rede relevantes
- estado de imagens
- estado de videos ou players
- tempo ate estabilidade quando possivel
- links e downloads detectados
- recursos interativos detectados
- dados de atividades e avaliacoes visiveis sem submissao destrutiva

## Espera E Estabilidade

Uma pagina so esta pronta para revisao quando:

- navegacao terminou
- loaders principais sumiram ou estabilizaram
- imagens essenciais terminaram de carregar ou falharam explicitamente
- videos tiveram metadados carregados quando presentes
- nao houve mudanca visual relevante durante uma janela curta de estabilidade

Se a pagina fica instavel, registrar `blocked` ou `manual_review` em vez de adivinhar.

## Midia

### Imagem

- verificar `naturalWidth` e `naturalHeight`
- verificar falha de requisicao
- capturar tela quando imagem parece quebrada, cortada ou fora do layout

### Video

- verificar player
- verificar metadados/duracao
- testar inicio de reproducao quando permitido
- registrar se autoplay, bloqueio de navegador ou permissao impede teste

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
- `pagePacketPath`
- `visibleTextPath`
- `domSnapshotPath`
- `links`
- `interactions`
- `rawObservations`

Os nomes dos campos acima permanecem em ingles por serem contrato tecnico de saida do operador.

O julgamento final pertence ao Motor De Revisao e a rubrica.
