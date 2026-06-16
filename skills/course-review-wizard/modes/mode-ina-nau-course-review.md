# Mode: INA/NAU Course Review

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
6. `docs/products/ina-nau-mooc/objective-and-plan.md`
7. `docs/products/ina-nau-mooc/requirements-and-checklist.md`
8. `docs/templates/ina-nau-run-structure.md`
9. `docs/templates/page-packet.template.json`
10. `docs/templates/ina-betatest-report-template.md`

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
- [ ] Criar run directory
- [ ] Criar checklist ativo Betatest
- [ ] Inventariar estrutura do curso
- [ ] Capturar cada pagina com pacote completo
- [ ] Capturar variacoes/interacoes essenciais por pagina
- [ ] Capturar links, downloads, transcricoes e documentos
- [ ] Capturar atividades, avaliacoes, tentativas e feedbacks sem acao destrutiva
- [ ] Registrar lacunas de captura e itens `manual_review`
- [ ] Rodar checks offline sobre page packets
- [ ] Classificar ocorrencias em critica/relevante/melhoria/manual_review
- [ ] Preencher relatorio Betatest
- [ ] Validar que cada ocorrencia tem evidencia
- [ ] Listar paginas/itens nao cobertos
- [ ] Final Audit

## Page Packet Obrigatorio

Para cada pagina, salvar um pacote em `artifacts/<run-id>/pages/<page-id>/` com:

- `page.json`: metadados, localizacao, URL, timestamps, viewport, status e checks basicos.
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

## Saidas

- `course-intake.json`
- `course-inventory.json`
- `pages/<page-id>/` com page packets
- `evaluation-findings.json`
- `ina-betatest-report.md`
- opcional: DOCX preenchido a partir do modelo INA
- `coverage.json`
- lista de retestes ou revisoes humanas necessarias

## Guardrails

- Nao corrigir conteudo diretamente na plataforma.
- Nao submeter avaliacao, tentativa ou resposta que possa alterar progresso real sem autorizacao explicita.
- Nao persistir senha, cookie, token ou dado pessoal.
- Nao marcar curso como revisado se a cobertura nao cobrir todo o manifest ou nao listar lacunas.
- Nao usar o relatorio tecnico interno como substituto do formulario Betatest INA.
