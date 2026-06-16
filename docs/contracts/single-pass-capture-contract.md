# Single Pass Capture Contract

## Proposito

Evitar revisitar desnecessariamente as mesmas paginas do curso. A passagem principal pelo curso deve capturar, em um unico momento, o maximo de dados necessarios para inventario, funcionamento, revisao editorial, acessibilidade, midia, atividades e relatorio.

## Regra Principal

Ao navegar uma pagina, o agente deve capturar um `page packet` completo antes de marcar a pagina como visitada.

Fases posteriores devem consumir primeiro os artefatos salvos. Reabrir a pagina e excecao, nao rotina.

## Dados Minimos Do Page Packet

O arquivo `page.json` deve seguir `docs/evaluations/schemas/page-packet.schema.json`, usando `docs/templates/page-packet.template.json` como ponto de partida.

- identificacao do curso, modulo, secao, pagina e indice;
- URL/rota canonica;
- timestamp;
- viewport;
- metodo de navegacao;
- status de carregamento e estabilidade;
- screenshot full page, quando possivel;
- screenshot da viewport;
- texto visivel extraido;
- snapshot DOM ou texto estruturado sanitizado;
- imagens detectadas, dimensoes, alt text e status de carregamento;
- videos/players detectados, duracao/metadata quando disponivel, transcricao e sintese associadas;
- links internos, externos e downloads;
- documentos/anexos detectados e status de disponibilidade;
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
- players de video para metadata/playback curto, se permitido.

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

Usa status de carregamento, screenshot, console/network, media e links.

### Revisao Editorial

Usa `visible-text.txt`, DOM sanitizado, transcricoes, textos de recursos e textos extraidos de documentos.

### Midia E Acessibilidade

Usa `media.json`, screenshots, alt text, transcricoes, sinteses, OCR quando disponivel e estados interativos capturados.

### Atividades E Avaliacoes

Usa enunciados, alternativas, feedbacks, configuracoes visiveis e screenshots. Se a plataforma exigir submissao para revelar feedback, registrar lacuna ou pedir autorizacao para ambiente seguro.

### Relatorio

Usa achados consolidados e evidencia dos page packets. Nenhuma ocorrencia deve entrar no relatorio Betatest sem referencia a pacote, screenshot, URL ou log.

## Motivos Validamente Aceitos Para Reabrir Pagina

- page packet incompleto;
- screenshot ilegivel ou ausente;
- erro transitorio que precisa confirmacao;
- recurso interativo nao capturado;
- video precisa teste de playback;
- documento baixado precisa validacao;
- correcao foi aplicada e precisa reteste;
- humano pediu verificacao especifica;
- criterio novo foi adicionado depois da captura original.

## Final Audit

Antes de gerar relatorio, verificar:

1. Todas as paginas do manifest possuem page packet ou lacuna registrada.
2. Cada page packet tem pelo menos metadados, URL, texto ou justificativa, e screenshot ou justificativa.
3. Cada achado aponta para evidencia existente.
4. Fases offline nao inventaram conclusoes sem suporte nos artefatos.
5. Reaberturas de pagina foram justificadas.
6. `page.json` valida contra `docs/evaluations/schemas/page-packet.schema.json`, ou a divergencia esta documentada.
