# Contrato De Captura Em Passagem Unica

## Proposito

Evitar revisitar desnecessariamente as mesmas paginas do curso. A passagem principal pelo curso deve capturar, em um unico momento, o maximo de dados necessarios para inventario, funcionamento, revisao editorial, acessibilidade, midia, atividades e relatorio.

## Regra Principal

Ao navegar uma pagina, o agente deve capturar um `pacote de pagina` completo antes de marcar a pagina como visitada.

Fases posteriores devem consumir primeiro os artefatos salvos. Reabrir a pagina e excecao, nao rotina.

## Dados Minimos Do Pacote De Pagina

O arquivo `page.json` deve seguir `docs/evaluations/schemas/page-packet.schema.json`, usando `docs/templates/page-packet.template.json` como ponto de partida.

- identificacao do curso, modulo, secao, pagina e indice;
- URL/rota canonica;
- timestamp;
- viewport;
- metodo de navegacao;
- estado de carregamento e estabilidade;
- screenshot full page, quando possivel;
- screenshot da viewport;
- texto visivel extraido;
- snapshot DOM ou texto estruturado sanitizado;
- imagens detectadas, dimensoes, alt text e estado de carregamento;
- videos/players detectados, duracao/metadados quando disponivel, transcricao e sintese associadas;
- links internos, externos e downloads;
- documentos/anexos detectados e estado de disponibilidade;
- atividades, questoes, alternativas, feedbacks e configuracoes visiveis sem submissao destrutiva;
- recursos interativos e estados capturados;
- console errors;
- network failures relevantes;
- observacoes cruas e lacunas.

## Interacoes Durante A Captura

Durante a passagem unica, o agente deve abrir interacoes revisaveis quando isso for seguro:

- acordeoes;
- abas;
- hotspots;
- botoes de revelar texto;
- caixas de recurso;
- downloads;
- links externos em nova aba;
- players de video para metadados/reproducao curto, se permitido.

Nao executar interacoes que:

- submetem resposta;
- alteram nota;
- consomem tentativa;
- gravam progresso sensivel;
- expõem dados pessoais;
- exigem pagamento, credencial ou autorizacao destrutiva.

Quando uma interacao nao puder ser executada, registrar `blocked` ou `manual_review` com motivo.

## Uso Pelas Fases

### Inventario

Usa `page.json`, `links.json`, `media.json`, `interactions.json` e snapshots para montar o mapa do curso.

### Funcionamento

Usa estado de carregamento, screenshot, console/network, media e links.

### Revisao Editorial

Usa `visible-text.txt`, DOM sanitizado, transcricoes, textos de recursos e textos extraidos de documentos.

### Midia E Acessibilidade

Usa `media.json`, screenshots, alt text, transcricoes, sinteses, OCR quando disponivel e estados interativos capturados.

### Atividades E Avaliacoes

Usa enunciados, alternativas, feedbacks, configuracoes visiveis e screenshots. Se a plataforma exigir submissao para revelar feedback, registrar lacuna ou pedir autorizacao para ambiente seguro.

### Relatorio

Usa achados consolidados e evidencia dos pacotes de pagina. Nenhuma ocorrencia deve entrar no relatorio Betatest sem referencia a pacote, screenshot, URL ou log.

## Evidencia Visual Por Achado

Quando um achado for criado durante ou apos a captura, ele deve apontar para:

- `contextScreenshot`: screenshot contextual obrigatorio, com a area ao redor do erro visivel;
- `focusedScreenshot`: screenshot focado opcional, quando houver detalhe pequeno, texto especifico, icone, botao, imagem ou trecho de layout que precise ampliacao;
- `pagePacket`: pacote da pagina de onde o achado saiu;
- `logEvidence`: log opcional quando o achado for tecnico.

O `contextScreenshot` deve ser maior que o recorte minimo do erro. Preferir incluir o card/bloco completo, titulo da pagina, controles proximos e parte da navegacao quando isso ajudar a localizar o problema. Nao usar screenshot focado como unica evidencia visual de achado.

Se o achado for descoberto offline a partir de texto/DOM/documento e o `pacote de pagina` nao tiver screenshot contextual suficiente, reabrir a pagina e capturar a evidencia visual antes de incluir o achado no relatorio.

## Motivos Validamente Aceitos Para Reabrir Pagina

- pacote de pagina incompleto;
- screenshot ilegivel ou ausente;
- screenshot contextual de achado ausente ou insuficiente;
- erro transitorio que precisa confirmacao;
- recurso interativo nao capturado;
- video precisa teste de reproducao;
- documento baixado precisa validacao;
- correcao foi aplicada e precisa reteste;
- humano pediu verificacao especifica;
- criterio novo foi adicionado depois da captura original.

## Auditoria Final

Antes de gerar relatorio, verificar:

1. Todas as paginas do manifest possuem pacote de pagina ou lacuna registrada.
2. Cada pacote de pagina tem pelo menos metadados, URL, texto ou justificativa, e screenshot ou justificativa.
3. Cada achado aponta para evidencia existente, incluindo screenshot contextual quando for erro visual, textual, editorial, layout, midia, link, recurso ou atividade.
4. Fases offline nao inventaram conclusoes sem suporte nos artefatos.
5. Reaberturas de pagina foram justificadas.
6. `page.json` valida contra `docs/evaluations/schemas/page-packet.schema.json`, ou a divergencia esta documentada.
