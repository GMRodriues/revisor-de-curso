# Review Rubric Contract

## Proposito

Definir como classificar problemas encontrados nos cursos.

## Severidades

### blocking

Impede lancamento ou impede o aluno de consumir o conteudo.

Exemplos:

- pagina nao carrega
- botao proximo nao funciona
- video obrigatorio nao toca
- imagem principal quebrada
- erro bloqueia progresso

### major

Afeta seriamente a experiencia, mas nao bloqueia totalmente.

Exemplos:

- texto importante cortado
- layout sobrepoe conteudo
- video demora muito ou falha intermitente
- imagem errada ou muito pixelada
- navegacao inconsistente

### minor

Problema de polimento.

Exemplos:

- espacamento visual estranho
- typo pequeno
- alinhamento leve
- imagem com margem inconsistente

### manual_review

Precisa de julgamento humano ou criterio ainda nao formalizado.

Exemplos:

- qualidade pedagogica
- tom do texto
- clareza da explicacao
- adequacao de exemplo
- qualidade subjetiva de imagem ou video

## Categorias

- `load`
- `navigation`
- `layout`
- `text`
- `image`
- `video`
- `audio`
- `accessibility`
- `content`
- `platform_error`
- `manual_review`

## Regra De Pronto

Um curso so pode ser marcado como `ready_candidate` quando:

1. todas as paginas do escopo foram visitadas ou lacunas foram aceitas por humano
2. nao ha achados `blocking`
3. achados `major` restantes foram aceitos ou corrigidos
4. itens `manual_review` obrigatorios foram revisados
5. relatorio inclui evidencia suficiente

