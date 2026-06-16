# INA/NAU MOOC - Requisitos E Checklist

## Escopo Contratual

Fonte: caderno de encargos, Parte II, paginas 13 a 15.

O servico deve assegurar que cursos MOOC do INA, a disponibilizar na plataforma NAU, cumprem requisitos de qualidade antes do lancamento publico.

O checklist deve ser tratado como especificacao da frente INA/NAU, nao apenas de cursos ReCAP. Quando um curso tiver particularidades de familia, fornecedor ou equipa produtora, essas regras devem entrar como extensoes do checklist sem quebrar o pipeline comum.

O universo previsto no caderno e:

- 210 cursos;
- 318 horas de formacao;
- 174 cursos de 1 hora;
- 36 cursos de 4 horas;
- cursos assicronos, sem presenca de formador;
- conteudos multimedia;
- atividades formativas;
- avaliacoes automaticas.

## Criterios Tecnicos Obrigatorios

O agente deve verificar:

1. Alinhamento entre objetivos de aprendizagem, conteudos e atividades de avaliacao.
2. Clareza, correcao linguistica e adequacao pedagogica dos conteudos.
3. Navegacao, sequenciacao e precedencias das paginas do curso.
4. Funcionamento tecnico de videos, atividades interativas, avaliacoes e downloads.
5. Configuracao correta de avaliacoes, tentativas, feedback e criterios de aprovacao.
6. Cumprimento de requisitos de acessibilidade e usabilidade.
7. Experiencia global do utilizador enquanto formando.
8. Alinhamento da linguagem, imagens e atividades ao publico-alvo.
9. Configuracao de atividades de avaliacao formativa e respetivos feedbacks.
10. Configuracao de atividades de avaliacao sumativa, classificacao e certificacao.
11. Erros, inconformidades e oportunidades de melhoria antes do lancamento.

## Regras De Execucao

Fonte: caderno de encargos, pagina 14.

O agente deve:

- realizar a frequencia integral do curso, simulando a experiencia real do formando;
- executar testagem sistematica com checklist INA validada;
- testar todos os modulos, paginas, conteudos, recursos multimedia, atividades e avaliacoes;
- registrar todas as ocorrencias;
- classificar ocorrencias por tipologia;
- identificar localizacao exata de cada ocorrencia: curso, modulo e pagina;
- gerar relatorios claros e estruturados de beta testing;
- apoiar revalidacao apos correcoes.

## Classificacao INA Das Ocorrencias

O caderno usa:

- `critica`
- `relevante`
- `melhoria`

Mapeamento recomendado para a rubrica interna:

| INA | Rubrica interna | Uso |
| --- | --- | --- |
| critica | blocking | Impede lancamento, acesso, progressao, consumo de conteudo obrigatorio ou certificacao. |
| relevante | major | Afeta significativamente a experiencia ou a aprendizagem, mas tem workaround. |
| melhoria | minor | Ajuste de polimento, clareza, consistencia ou oportunidade de melhoria. |
| exige validacao | manual_review | Depende de criterio humano ou ainda nao ha regra formal. |

## Checklist Do Modelo Betatest

Fonte: modelo INA e exemplo preenchido.

### Verificacoes Padrao

1. Menu de topo segue a ordem padrao definida.
2. Publico-alvo inserido antes dos objetivos gerais na pagina `Sobre o curso`.
3. Objetivos gerais aparecem no Modulo 1 e objetivos especificos nos modulos UFE/UFC.
4. Rodape com logotipos INA/PRR proporcional e consistente na primeira e ultima pagina.
5. Inquerito de Caracterizacao eliminado, quando existente no Modulo 1.
6. Mensagem de navegacao explicita o botao `Seguinte >` no fim das paginas.
7. Icones revistos, padronizados e acessiveis em todas as paginas.
8. Videos possuem transcricao descarregavel.
9. Videos possuem resumo/sintese abaixo do video.
10. Recursos com texto em imagem possuem alternativa textual descarregavel.
11. Feedback de atividades pode ser relido sem refazer exercicio.
12. Ligacoes externas abrem em novo separador com aviso textual.
13. Texto do Inquerito de Satisfacao aplicado.
14. Texto de Proximos cursos aplicado sem `UFC padrao`.
15. Logotipos da pagina Programa alinhados numa unica linha, quando aplicavel.

### Avaliacao Global Do Curso

Preencher `SIM`, `NAO` ou observacao para:

- clareza e correcao linguistica;
- adequacao da linguagem aos publicos-alvo de cada Unidade Formativa;
- adequacao das atividades ao publico-alvo;
- adequacao das imagens ao contexto AP;
- configuracao das atividades de avaliacao formativa e respetivos feedbacks;
- configuracao das atividades de avaliacao sumativa, classificacao e certificacao.

### Experiencia Do Formando

Avaliar de 1 a 5:

- navegacao/orientacao na plataforma;
- informacao disponivel;
- documentacao;
- qualidade dos videos com especialistas;
- qualidade de outros videos, incluindo animacoes e tutoriais;
- apreciacao global sobre o curso.

Quando a nota for 1 ou 2, justificar com evidencia. Para as primeiras calibracoes, tambem justificar notas 3 para ajudar a calibrar criterio.

## Evidencia Minima Por Ocorrencia

Cada ocorrencia que entrar no relatorio deve ter:

- localizacao exata;
- URL ou identificacao da pagina/secao;
- screenshot contextual obrigatorio, mostrando a area ao redor do erro;
- screenshot focado opcional, quando o detalhe precisar de ampliacao;
- log, quando o erro for tecnico;
- comportamento observado;
- criterio violado;
- recomendacao objetiva;
- classificacao;
- indicacao de revisao humana, quando aplicavel.

## Tipos De Erro Esperados

O exemplo preenchido mostra que os erros nao se limitam a falhas mecanicas. O agente deve procurar tambem:

- ausencia de transcricao ou link de download;
- ausencia de botao, icone ou instrucao clara;
- variacao inconsistente em nomes de competencias e comportamentos;
- imagem pequena, ilegivel ou com contraste fraco;
- aviso ausente para links que abrem nova aba;
- espacamento inadequado em documentos de transcricao;
- recurso interativo que mistura texto com imagem ou corta caixas;
- termo de interface inadequado, como chamar abas de botoes;
- textos de apoio sem contexto suficiente;
- documentos com nome de curso incorreto;
- mensagem final de navegacao incompleta;
- links desnecessarios para Progresso/Certificado;
- atividades com texto ou checkboxes pequenos;
- arquivos de transcricao incompletos ou pouco acessiveis;
- marcadores, pontuacao, aspas e maiusculas/minusculas inconsistentes.

## Gates Para Marcar Curso Como Revisado

Um curso so pode seguir para curadoria humana quando:

1. Inventario cobre todas as paginas encontradas.
2. Todas as paginas foram visitadas ou lacunas estao listadas.
3. Todos os videos foram pelo menos verificados quanto a player, transcricao e sintese.
4. Todos os recursos interativos foram abertos ou marcados como bloqueados.
5. Todas as avaliacoes/atividades foram inspecionadas.
6. Documentos baixados e links externos foram testados quando possivel.
7. Todas as ocorrencias no relatorio possuem evidencia.
8. Itens que dependem de criterio humano estao marcados como `manual_review`.
9. O relatorio esta no formato Betatest e nao somente em formato tecnico interno.
