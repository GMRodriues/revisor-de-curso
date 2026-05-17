# Report Output V2

## Objetivo

Definir o formato do relatorio que sera enviado ao responsavel pelo curso.

## Secoes Do Relatorio

### 1. Identificacao Do Curso

- Nome do curso.
- Plataforma.
- URL.
- Competencia/area.
- Carga horaria prevista.
- Data da avaliacao.
- Escopo avaliado.

### 2. Resumo Executivo

Deve responder:

- O curso esta funcional?
- Ha bloqueios?
- Ha problemas recorrentes?
- Quais categorias mais aparecem?
- O curso parece pronto, precisa ajustes pontuais ou precisa revisao ampla?

### 3. Cobertura

Tabela:

| Unidade | Esperado | Avaliado | Status | Observacoes |
| --- | ---: | ---: | --- | --- |

### 4. Achados

Tabela minima:

| ID | Severidade | Categoria | Localizacao | Observado | Recomendacao | Evidencia |
| --- | --- | --- | --- | --- | --- | --- |

### 5. Avaliacoes Globais

Baseado nos relatorios reais, manter uma secao semelhante a:

- Clareza e correcao linguistica.
- Adequacao ao publico-alvo.
- Adequacao das atividades.
- Adequacao das imagens.
- Configuracao de atividades formativas e feedbacks.
- Configuracao de atividades sumativas, classificacao e certificacao.

Cada item deve ter:

- `sim`
- `nao`
- `nao_avaliado`
- observacoes

### 6. Experiencia Do Formando

Escala sugerida: 1 a 5.

Itens:

- navegacao/orientacao;
- informacao disponivel;
- documentacao;
- qualidade dos videos com especialistas;
- qualidade de outros videos;
- apreciacao global.

### 7. Outras Observacoes

Espaco para observacoes gerais que nao cabem em achados isolados, por exemplo:

- curso muito longo para a carga horaria;
- excesso de animacoes;
- problemas recorrentes de acessibilidade;
- complexidade inadequada ao publico-alvo;
- necessidade de disponibilizar textos complementares.

## Forma De Escrever Achados

Preferir:

- frase direta;
- problema especifico;
- criterio violado;
- recomendacao objetiva.

Evitar:

- julgamento vago;
- "parece ruim" sem evidencia;
- recomendacao sem explicar o motivo.

## Exemplo De Achado

```json
{
  "id": "EV-001",
  "severity": "major",
  "category": "interactive_resource",
  "location": {
    "course": "Curso exemplo",
    "module": "Modulo 2",
    "page": "Atividade X",
    "url": "https://..."
  },
  "observed": "O recurso usa deslocamento horizontal e parte do texto fica fora da area visivel.",
  "expected": "Recursos com texto longo devem ser apresentados em formato legivel, sem exigir deslocamento horizontal.",
  "evidence": ["screenshots/page-10.png"],
  "recommendation": "Substituir por acordeao ou caixas horizontais com texto integral visivel.",
  "requiresHumanReview": false
}
```
