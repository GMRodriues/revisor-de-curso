# INA/NAU Estrutura De Execucao

Use esta estrutura para cada execucao de curso INA/NAU.

```text
artifacts/
  <run-id>/
    run.json
    course-intake.json
    course-inventory.json
    coverage.json
    checklist.md
    findings/
      evaluation-findings.json
      finding-index.md
      <finding-id>/
        context.png
        focused.png
        source.json
    pages/
      <page-id>/
        page.json
        visible-text.txt
        dom-snapshot.html
        fullpage.png
        viewport.png
        media.json
        links.json
        interactions.json
        console.json
        network.json
        notes.md
    downloads/
      <download-id>/
        source.json
        original-file
        extracted-text.txt
        notes.md
    reports/
      ina-betatest-report.md
      ina-betatest-report.docx
      internal-audit.md
```

## ID Da Execucao

Formato recomendado:

```text
ina-nau-<course-slug>-YYYY-MM-DD
```

Se houver reteste:

```text
ina-nau-<course-slug>-YYYY-MM-DD-retest-01
```

## Arquivos Raiz

### `run.json`

Resumo da execucao. Deve seguir `docs/evaluations/schemas/evaluation-run.schema.json`.

### `course-intake.json`

Dados fornecidos ou inferidos antes da revisao:

- URL inicial;
- curso;
- tipo de unidade formativa;
- competencia;
- duracao esperada;
- perfil de acesso usado, sem credenciais;
- escopo;
- restricoes conhecidas;
- data/hora de inicio.

### `course-inventory.json`

Mapa do curso:

- modulos;
- secoes;
- paginas;
- videos;
- recursos interativos;
- atividades;
- avaliacoes;
- documentos;
- links externos;
- paginas padrao.

### `coverage.json`

Cobertura efetiva:

- paginas esperadas;
- paginas capturadas;
- paginas bloqueadas;
- videos esperados/capturados;
- atividades esperadas/capturadas;
- downloads esperados/capturados;
- lacunas aceitas ou pendentes.

## Pacotes De Pagina

Cada pasta em `pages/<page-id>/` representa uma pagina ou unidade navegavel.

O arquivo `page.json` deve seguir `docs/evaluations/schemas/page-packet.schema.json`.

IDs de pagina devem ser estaveis e legiveis:

```text
modulo-01-sobre-o-curso
modulo-02-video-introducao
modulo-03-atividade-reflexao
```

Quando houver identificador da plataforma, registrar em `platformUnitId`, mas nao depender dele como unico nome humano.

## Achados

Cada achado listado em `findings/evaluation-findings.json` deve ter uma pasta propria em `findings/<finding-id>/`.

Arquivos esperados:

- `context.png`: obrigatorio. Screenshot contextual com a area ao redor do erro.
- `focused.png`: opcional. Recorte mais proximo quando o detalhe precisa de ampliacao.
- `source.json`: metadados do achado, pagina de origem, URL, `pacote de pagina`, criterio violado e arquivos de evidencia.

O screenshot contextual deve mostrar mais do que o trecho exato do erro. Incluir o bloco completo, titulo, controles proximos ou parte da navegacao quando isso ajudar uma pessoa a entender e corrigir a ocorrencia.

## Documentos Baixados

Salvar documentos baixados quando isso for permitido e necessario para revisar acessibilidade, transcricoes, materiais de apoio ou ficheiros anexos.

Cada download deve ter:

- `source.json`: URL, pagina de origem, tipo, estado, hash quando disponivel;
- arquivo original;
- `extracted-text.txt`, quando for possivel extrair texto;
- `notes.md` com lacunas e observacoes.

Nao salvar documentos com dados pessoais, credenciais ou informacao sensivel.

## Relatorios

### `ina-betatest-report.md`

Relatorio humano principal, no formato `docs/templates/ina-betatest-report-template.md`.

### `ina-betatest-report.docx`

Opcional ate o gerador DOCX estar calibrado. Quando gerado, deve preservar o formato INA e passar por QA visual quando o ambiente permitir.

### `internal-audit.md`

Auditoria interna:

- cobertura contra manifest;
- lacunas;
- achados sem evidencia, se houver;
- paginas reabertas e motivo;
- itens de revisao humana.

## Regra De Uso

O agente deve preencher a estrutura conforme navega. Nao deixar para reconstruir evidencias no final a partir de memoria da sessao.
