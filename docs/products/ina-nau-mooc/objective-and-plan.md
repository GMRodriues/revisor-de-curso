# INA/NAU MOOC Review - Objetivo E Plano

## Objetivo Final

Transformar uma URL de pagina de curso na plataforma NAU em um relatorio de Betatest parecido com o modelo INA, com o menor trabalho humano possivel.

O fluxo alvo e:

1. Humano fornece a pagina inicial do curso.
2. O agente identifica o curso, a unidade formativa, a competencia, a duracao e a estrutura navegavel.
3. O agente percorre integralmente o curso como formando.
4. O agente coleta evidencias por pagina, modulo, recurso, video, atividade, avaliacao, documento e link.
5. O agente aplica criterios de qualidade pedagogica, funcional, tecnica, acessibilidade, usabilidade e experiencia do formando.
6. O agente gera um relatorio no formato `Cursos MOOC - Registo de Teste Beta`.
7. Humano faz curadoria final do relatorio, validando falso positivo, falso negativo, tom editorial e recomendacoes.

O objetivo nao e eliminar a revisao humana. O objetivo e trocar a maior parte da revisao repetitiva por um fluxo auditavel, em que o humano revisa uma proposta ja preenchida.

## Fontes De Calibracao

- Caderno de encargos: `/Users/gabrielrodrigues/Downloads/Caderno Encargos_TESTAGEM E VALIDAÇÃO DE CURSOS MOOC.pdf`
- Modelo vazio INA: `/Users/gabrielrodrigues/Downloads/INA_MOOC_Betatest_Recap_form_v20241222.docx`
- Exemplo preenchido: `/Users/gabrielrodrigues/Downloads/CEN1_VF.docx`

O nome `ReCAP` aparece em alguns exemplos e no modelo disponibilizado, mas nao deve limitar o projeto. A premissa operacional e: todos os cursos desta frente estao na mesma plataforma NAU e devem passar pelo mesmo pipeline de testagem, ainda que tenham sido produzidos por empresas/equipas diferentes e possam apresentar erros diferentes.

Referencias principais do caderno:

- Pagina 13: finalidade da testagem e criterios tecnicos da clausula 27.
- Pagina 14: execucao integral, checklist INA, relatorios por curso e classificacao de ocorrencias.
- Pagina 15: necessidade de competencias em e-learning, testagem, revisao pedagogica e acessibilidade digital.

## Mudanca De Premissa

Premissa antiga:

- O projeto precisava suportar varios provedores/plataformas desde o inicio.
- O output principal era um relatorio tecnico generico com severidade, cobertura e evidencias.

Premissa nova para a primeira fase:

- O produto principal e INA/NAU MOOC.
- O lote tem muitos cursos, mas compartilha o mesmo tipo de relatorio e criterios.
- A automacao deve ser platform-first e report-first: estrutura NAU, regras INA, formulario Betatest e curadoria humana.
- ReCAP e uma familia/exemplo dentro do escopo, nao a fronteira do escopo.
- Outras plataformas ou provedores ficam fora do caminho critico ate o fluxo INA/NAU estar calibrado.

## Modelo Operacional Proposto

### 1. Intake Do Curso

Entrada minima:

- URL inicial do curso NAU.
- Confirmacao de acesso/login por perfil local.
- Tipo de unidade formativa, quando conhecido.
- Competencia e duracao esperada, quando conhecidas.
- Escopo: curso completo, modulo especifico, reteste de correcoes ou amostra de calibracao.

Saida:

- `course-intake.json`
- riscos conhecidos
- decisao de escopo
- checklist ativo

### 2. Inventario Integral

Antes de julgar qualidade, o agente deve mapear:

- paginas padrao do curso;
- modulos, unidades, sequencias e paginas;
- videos;
- recursos interativos;
- imagens com texto;
- atividades formativas;
- avaliacoes sumativas;
- downloads, transcricoes e documentos;
- links externos;
- paginas finais, certificacao, satisfacao e proximos cursos.

Saida:

- `course-inventory.json`
- mapa de cobertura
- lista de itens nao descobertos ou ambiguos

Na pratica, inventario e captura devem acontecer juntos sempre que o agente ja estiver navegando pagina a pagina. A primeira passagem pelo curso deve produzir `page packets`, para evitar que as fases seguintes precisem abrir novamente a mesma pagina.

### 3. Review Automatizado Por Pagina

Cada pagina deve gerar evidencia minima:

- URL;
- curso, modulo, pagina/secao;
- timestamp;
- screenshot;
- texto extraido do DOM;
- erros de console/network relevantes, quando disponiveis;
- status de imagens;
- status de videos;
- status de links/downloads;
- observacoes cruas do operador.

O agente nao deve concluir que uma pagina esta correta so porque carregou. Ele deve aplicar os criterios do checklist ativo.

As fases de analise devem usar primeiro esses pacotes salvos. Reabrir a pagina deve ser reservado para lacuna de captura, interacao nao testada, reteste apos correcao ou pedido humano especifico.

### 4. Review Por Familias De Criterios

O review deve aplicar, no minimo:

- funcionamento e navegacao;
- sequenciacao e precedencias;
- conteudo, objetivos e atividades;
- clareza linguistica e adequacao pedagogica;
- publico-alvo;
- imagens e contexto AP;
- videos, transcricoes e sinteses;
- recursos interativos;
- acessibilidade e usabilidade;
- atividades formativas e feedbacks;
- avaliacao sumativa, classificacao e certificacao;
- links, documentos e downloads;
- experiencia global do formando.

### 5. Relatorio Betatest

O relatorio final para curadoria humana deve seguir o contrato em `docs/templates/ina-betatest-report-template.md`.

Saidas internas podem continuar em JSON/Markdown para rastreabilidade, mas o output humano deve ser o formulario INA.

A estrutura de artefatos por run deve seguir `docs/templates/ina-nau-run-structure.md`. Cada `page.json` deve seguir `docs/evaluations/schemas/page-packet.schema.json`.

### 6. Curadoria Humana E Calibracao

Depois de cada curso revisado:

- humano valida achados incluidos;
- humano remove falso positivo;
- humano adiciona falso negativo encontrado;
- agente registra ajuste de criterio;
- checklist e rubrica sao atualizados.

Essa calibracao e obrigatoria nos primeiros cursos e deve ser repetida sempre que aparecer novo tipo de erro.

## Alteracoes Recomendadas No Setup

### Agora

- Criar modo operacional `ina-nau-course-review` ou equivalente.
- Tornar `docs/products/ina-nau-mooc/` a fonte de verdade para esta frente.
- Fazer o report builder gerar primeiro Markdown no formato Betatest e depois DOCX, quando o preenchimento estiver estavel.
- Tratar JSON e evidencias como anexos internos, nao como relatorio final primario.

### Depois Do Primeiro Curso Calibrado

- Criar runner dedicado para NAU/Open edX, preferindo estrutura DOM/API a clique por setas.
- Implementar extratores especificos para sequentials/verticals, videos, transcricoes, assets e avaliacoes.
- Implementar gerador DOCX usando o modelo INA.
- Adicionar validacao automatica de que todos os achados do relatorio possuem evidencia.

### Antes Do Lote

- Definir politica de reteste apos correcoes.
- Criar fila de cursos e estado por curso.
- Criar dashboard ou indice consolidado por status.
- Medir tempo medio por curso de 1 hora e 4 horas.
- Congelar criterios aceitos para reduzir variacao entre runs.

## Status Do Projeto Para Esta Meta

O projeto ja tem boa base:

- contratos de evidencia;
- contratos de execucao;
- rubrica de severidade;
- fases de discovery, page review, media review, reporting e calibration;
- docs `evaluations` com criterios semelhantes aos relatorios reais.

O principal gap e que a skill ainda trata o fluxo como generico e, nos docs anteriores, estava mais acoplada ao ReCAP do que deveria. Para a meta atual, ela deve priorizar um pipeline INA/NAU com relatorio Betatest como output principal.
