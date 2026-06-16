# Modo: Teste Beta De Curso INA/NAU

## Objetivo

Revisar integralmente um curso MOOC INA na plataforma NAU e gerar um relatorio no formato `Cursos MOOC - Registo de Teste Beta`, com evidencias suficientes para curadoria humana.

## Quando Usar

Use este modo quando:

- o usuario fornecer URL de curso NAU/INA;
- o usuario pedir relatorio Betatest INA;
- o trabalho estiver ligado ao caderno de encargos de testagem e validacao de cursos MOOC;
- o curso estiver na mesma plataforma NAU, ainda que seja de familia/produto diferente de ReCAP.

## Entradas

- URL inicial do curso.
- Perfil/login local autorizado.
- Escopo: curso completo, modulo, reteste ou calibracao.
- Modelo Betatest esperado, quando houver variante.
- Regras adicionais de familia/produto, quando conhecidas.

## Contratos E Referencias

Ler antes de operar navegador:

1. `docs/contracts/execution-loop-contract.md`
2. `docs/contracts/evidence-contract.md`
3. `docs/contracts/single-pass-capture-contract.md`
4. `docs/contracts/browser-operator-contract.md`
5. `docs/contracts/review-rubric-contract.md`
6. `docs/glossario-operacional.md`
7. `docs/products/ina-nau-mooc/objective-and-plan.md`
8. `docs/products/ina-nau-mooc/requirements-and-checklist.md`
9. `docs/templates/ina-nau-run-structure.md`
10. `docs/templates/page-packet.template.json`
11. `docs/templates/ina-betatest-report-template.md`

## Estrategia

Fazer uma passagem principal pelo curso, em ordem de formando, capturando dados suficientes para as fases seguintes.

O agente deve evitar navegar o curso varias vezes para tarefas que poderiam ser resolvidas com artefatos ja coletados. Reabrir pagina somente quando:

- houve falha ou lacuna de captura;
- a evidencia visual ficou insuficiente;
- uma interacao especifica nao foi aberta na primeira passagem;
- o curso foi corrigido e precisa reteste;
- a decisao exige estado vivo da plataforma.

## Checklist

- [ ] Resolver contexto INA/NAU e escopo do curso
- [ ] Confirmar acesso/login sem persistir credenciais
- [ ] Criar diretorio de execucao
- [ ] Criar checklist ativo Betatest
- [ ] Inventariar estrutura do curso
- [ ] Capturar cada pagina com pacote completo
- [ ] Capturar variacoes/interacoes essenciais por pagina
- [ ] Capturar links, downloads, transcricoes e documentos
- [ ] Capturar atividades, avaliacoes, tentativas e feedbacks sem acao destrutiva
- [ ] Registrar lacunas de captura e itens `manual_review`
- [ ] Rodar verificacoes offline sobre pacotes de pagina
- [ ] Classificar ocorrencias em critica/relevante/melhoria/manual_review
- [ ] Capturar screenshot contextual para cada ocorrencia
- [ ] Preencher relatorio Betatest
- [ ] Validar que cada ocorrencia tem evidencia
- [ ] Listar paginas/itens nao cobertos
- [ ] Auditoria Final

## Pacote De Pagina Obrigatorio

Para cada pagina, salvar um pacote em `artifacts/<run-id>/pages/<page-id>/` com:

- `page.json`: metadados, localizacao, URL, timestamps, viewport, estado e verificacoes basicas.
- `visible-text.txt`: texto visivel extraido.
- `dom-snapshot.html` ou `dom-snapshot.txt`: snapshot sanitizado do conteudo revisavel.
- `fullpage.png`: screenshot de pagina inteira, quando possivel.
- `viewport.png`: screenshot da viewport.
- `media.json`: imagens, videos, audios, iframes e players detectados.
- `links.json`: links internos, externos, downloads e destino esperado.
- `interactions.json`: recursos interativos detectados e estados capturados.
- `console.json`: erros de console relevantes, quando disponiveis.
- `network.json`: falhas de rede relevantes, quando disponiveis.
- `notes.md`: observacoes cruas e lacunas.

O arquivo `page.json` deve seguir `docs/evaluations/schemas/page-packet.schema.json`. A estrutura geral do run deve seguir `docs/templates/ina-nau-run-structure.md`.

Quando existirem recursos interativos, capturar tambem screenshots e texto dos estados abertos, se isso nao alterar progresso, resposta de aluno, nota ou dado sensivel.

## Evidencia Por Ocorrencia

Cada ocorrencia/achado incluido no relatorio deve ter evidencia visual contextual:

- salvar screenshot contextual em `artifacts/<run-id>/findings/<finding-id>/context.png`;
- quando necessario, salvar tambem screenshot focado em `artifacts/<run-id>/findings/<finding-id>/focused.png`;
- o screenshot contextual deve mostrar a area ao redor do erro, nao apenas o recorte minimo do texto/icone;
- para erro textual, incluir contexto suficiente para ler a frase e reconhecer a pagina/bloco;
- para erro de layout, incluir o bloco inteiro e elementos vizinhos suficientes para perceber corte, sobreposicao ou alinhamento;
- para erro tecnico sem manifestacao visual, manter o log, mas ainda capturar a tela contextual quando houver pagina associada.

Se o erro for identificado por analise offline de texto, DOM, transcricao ou documento, reabrir a pagina apenas para capturar `context.png` antes de entregar o relatorio.

## Saidas

- `course-intake.json`
- `course-inventory.json`
- `pages/<page-id>/` com pacotes de pagina
- `evaluation-findings.json`
- `findings/<finding-id>/context.png` para cada achado
- `ina-betatest-report.md`
- opcional: DOCX preenchido a partir do modelo INA
- `coverage.json`
- lista de retestes ou revisoes humanas necessarias

## Protecoes

- Nao corrigir conteudo diretamente na plataforma.
- Nao submeter avaliacao, tentativa ou resposta que possa alterar progresso real sem autorizacao explicita.
- Nao persistir senha, cookie, token ou dado pessoal.
- Nao marcar curso como revisado se a cobertura nao cobrir todo o manifest ou nao listar lacunas.
- Nao usar o relatorio tecnico interno como substituto do formulario Betatest INA.
