# Evaluation Workflow V2

## Objetivo

Revisar cursos de uma unica plataforma, com foco em funcionamento, padroes de curso, acessibilidade, formato, ortografia, recursos, atividades e relatorio final para quem produziu o curso.

## Escopo Real Atual

- Uma plataforma.
- Um fluxo de login.
- Revisao de todos os cursos dentro da plataforma.
- Sem manutencao direta do conteudo.
- Sem alteracoes destrutivas.
- Saida principal: relatorio de problemas e recomendacoes.

## Fases Propostas

As fases abaixo sao conceituais. Na execucao INA/NAU, as fases 2 a 8 devem aproveitar uma unica passagem rica pelo curso sempre que possivel. Durante essa passagem, cada pagina gera um `page packet` com texto, screenshot, DOM sanitizado, midia, links, recursos, documentos, atividades e logs. As avaliacoes posteriores devem rodar sobre esses artefatos antes de decidir reabrir a plataforma.

### 1. Intake E Login

Objetivo: abrir a plataforma e identificar o curso.

Coletar:

- curso;
- URL;
- usuario/perfil usado;
- data da avaliacao;
- escopo;
- restricoes conhecidas.

### 2. Inventario Do Curso

Objetivo: mapear tudo que existe no curso antes de julgar qualidade.

Coletar:

- trilhas/modulos;
- aulas/paginas;
- tipo de conteudo por pagina;
- videos;
- imagens;
- recursos interativos;
- atividades/questoes;
- links externos;
- ficheiros/anexos;
- paginas padrao iniciais/finais.

Saida:

- `course-inventory.json`
- mapa de cobertura.
- page packets iniciais por pagina, quando a descoberta ja passar pelas paginas.

### 3. Funcionamento Basico

Objetivo: verificar se o curso esta navegavel e consumivel.

Checks:

- pagina abre;
- navegacao anterior/proxima funciona;
- conteudo principal aparece;
- video/player aparece;
- imagem carrega;
- recurso interativo aparece;
- atividade renderiza;
- link abre;
- ficheiro esta disponivel;
- nao ha erro bloqueante.

### 4. Extracao De Material Revisavel

Objetivo: obter material para analise editorial e de acessibilidade.

Extrair:

- texto visivel do DOM;
- texto de imagens via OCR;
- transcricoes disponiveis;
- resumo/sintese de videos;
- enunciados, alternativas e feedbacks de questoes;
- textos de recursos interativos;
- texto de ficheiros/anexos quando possivel.

Esta extracao deve acontecer preferencialmente na passagem principal por pagina, nao como navegacao separada.

### 5. Avaliacao De Padroes Do Curso

Objetivo: verificar se o curso respeita padroes globais definidos.

Checks:

- nomenclatura oficial;
- mensagem final de pagina;
- menu superior;
- paginas iniciais e finais;
- rodape/logotipos;
- links de certificado/progresso;
- glossario/material de apoio;
- botoes e nomes de atividades.

### 6. Avaliacao Editorial E Visual

Objetivo: detectar problemas de texto, formato e legibilidade.

Checks:

- ortografia;
- pontuacao;
- espacos indevidos;
- maiusculas/minusculas;
- termos em ingles;
- siglas;
- fluidez;
- complexidade;
- texto cortado;
- excesso de texto em uma tela;
- formato fora de padrao.

### 7. Avaliacao De Midia E Acessibilidade

Objetivo: validar condicoes de consumo por diferentes formandos.

Checks:

- video toca;
- audio e audivel;
- transcricao existe;
- sintese/resumo existe;
- imagem tem alt-text/descricao;
- imagem de texto e legivel;
- recurso interativo tem texto alternativo/integral;
- ficheiro baixado e legivel e nao apenas imagem;
- navegacao nao depende apenas de hover ou leitura visual complexa.

### 8. Avaliacao De Atividades E Questoes

Objetivo: revisar configuracao e qualidade minima das atividades.

Checks:

- enunciado claro;
- alternativas plausiveis;
- alternativa correta nao e obvia por tamanho;
- quantidade de tentativas correta;
- feedback presente e consistente;
- espacamento de alternativas;
- instrucao do recurso correta;
- botao de reinicio padronizado;
- progressao condiz com objetivo da atividade.

### 9. Relatorio Final

Objetivo: entregar ao responsavel pelo curso um relatorio acionavel.

Cada achado deve conter:

- localizacao exata;
- categoria;
- severidade;
- observado;
- esperado;
- evidencia;
- recomendacao;
- status;
- se precisa revisao humana.

## Saidas Do Avaliador

- `course-inventory.json`
- `pages/<page-id>/page.json`
- `extracted-content/`
- `evaluation-findings.json`
- `evaluation-report.md`
- screenshots/logs/evidencias por pagina
- resumo executivo por curso
