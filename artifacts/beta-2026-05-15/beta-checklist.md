# Beta Checklist

## Escopo

- Curso alvo: `Além da Genética 2.0 - Por Fabrício Pacholok`
- Plataforma/URL: `https://hotmart.com/pt-br/club/alem-da-genetica-20/products/6315578`
- Login/perfil: authenticated Hotmart account supplied by human; credentials not persisted in artifacts
- Modo de execucao: `discovery`
- Viewport inicial: browser default desktop `1280x720`
- Destino de evidencias: `artifacts/beta-2026-05-15/evidence/`
- Destino de relatorio: `artifacts/beta-2026-05-15/review-report.beta.md`

## Checklist De Intake

- [x] Identificar plataforma e ambiente.
- [x] Confirmar forma segura de login.
- [x] Definir curso alvo.
- [x] Definir menor escopo verificavel.
- [x] Confirmar viewport inicial.
- [x] Confirmar criterios obrigatorios.
- [x] Confirmar fora de escopo do beta.

## Checklist De Discovery

- [x] Abrir plataforma.
- [x] Confirmar login.
- [x] Localizar curso alvo.
- [x] Detectar estrutura de modulos/aulas/paginas visivel na listagem.
- [x] Preferir DOM/API/manifest quando disponivel.
- [ ] Validar navegacao anterior/proximo.
- [x] Criar manifest inicial.
- [x] Listar lacunas e ambiguidades.
- [x] Final Audit.

Resultado: discovery concluido para o link interno do produto. O link publico inicial exibiu compra, mas o link `/products/6315578` abriu a area interna com 25 trilhas e progresso `4/116 conteúdos`.

## Checklist De Review Unico

- [x] Resolver escopo.
- [x] Validar manifest.
- [x] Preparar navegador/perfil.
- [x] Revisar paginas em ordem no recorte beta.
- [x] Capturar evidencia por pagina revisada.
- [x] Aplicar checks de carregamento.
- [x] Aplicar checks de navegacao.
- [x] Aplicar checks de layout.
- [ ] Aplicar checks de imagem.
- [ ] Aplicar checks de video quando existir.
- [x] Registrar itens de manual review.
- [x] Gerar relatorio.
- [x] Final Audit.

Resultado: `single-course-review` / Phase 2 iniciado em recorte pequeno: trilha `COMECE POR AQUI`, modulo `BOAS VINDAS`, 5 paginas revisadas de 8 detectadas. Paginas 6-8 ficaram bloqueadas porque a automacao do navegador foi bloqueada na pagina `INTERVALO`; nenhum workaround foi tentado.

## Criterios De Sucesso Do Beta

- Manifest inicial criado ou lacunas documentadas.
- Pelo menos uma aula/modulo pequeno revisado de ponta a ponta.
- Evidencia salva por pagina revisada.
- Achados classificados por severidade.
- Itens subjetivos separados como `manual_review`.
- Relatorio final com cobertura e paginas nao visitadas.

## Criterios De Bloqueio

- Login exige credencial, token, cookie ou dado sensivel para persistir.
- Plataforma exige acao destrutiva, pagamento ou alteracao de conteudo.
- Nao ha forma confiavel de identificar curso/modulo/aula/pagina.
- Pagina fica instavel e impede captura verificavel.
