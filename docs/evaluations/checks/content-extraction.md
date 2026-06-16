# Verificacoes: Extracao De Conteudo

## Objetivo

Extrair o material que sera usado na revisao editorial, de acessibilidade e de qualidade das atividades.

Sem extracao confiavel, o avaliador deve registrar lacuna em vez de concluir que o conteudo esta correto.

## O Que Extrair

### Texto Da Pagina

- titulo;
- subtitulos;
- corpo de texto;
- chamadas/destaques;
- instrucoes;
- feedbacks;
- comentarios ou textos de apoio relevantes.

### Imagens

- URL/arquivo da imagem;
- dimensoes;
- alt-text;
- descricao visivel;
- OCR quando houver texto dentro da imagem;
- indicacao se a imagem e decorativa, informativa ou textual.

### Videos

- titulo;
- duracao;
- transcricao disponivel;
- resumo/sintese disponivel;
- questoes/reflexoes antes do video;
- legenda, se existir;
- amostra de audio/reproducao na fase de midia.

### Recursos Interativos

- texto visivel inicial;
- texto revelado apos interacao;
- instrucoes;
- botoes/controles;
- ordem dos itens;
- texto alternativo/integral para acessibilidade;
- evidencias de conteudo inacessivel ou nao selecionavel.

### Questoes E Atividades

- enunciado;
- alternativas;
- resposta correta quando disponivel;
- feedback correto/incorreto;
- numero de tentativas;
- textos de botao;
- instrucao de reinicio;
- estado apos resposta correta/incorreta quando testado.

### Links E Documentos

- texto do link;
- URL de destino;
- se abre nova aba;
- ficheiro baixado;
- texto extraido do ficheiro quando possivel;
- indicacao se o ficheiro e texto ou imagem escaneada.

## Saida

Salvar em estrutura por pagina:

```json
{
  "pageId": "",
  "url": "",
  "contentTypes": ["text", "video"],
  "visibleText": "",
  "images": [],
  "videos": [],
  "interactiveResources": [],
  "questions": [],
  "links": [],
  "documents": [],
  "extractionGaps": []
}
```

## Lacunas

Registrar `extractionGaps` quando:

- texto esta dentro de imagem e OCR falhou;
- recurso interativo nao permite extrair texto;
- video nao tem transcricao;
- ficheiro nao esta disponivel;
- conteudo aparece somente por hover ou em area inacessivel;
- automacao foi bloqueada.

## Evidencia Minima

- screenshot;
- DOM/texto extraido;
- OCR/transcricao quando aplicavel;
- caminho do arquivo extraido;
- motivo de lacuna.
