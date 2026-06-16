# Verificacoes: Questoes E Atividades

## Objetivo

Avaliar configuracao, clareza e qualidade minima de questoes e atividades.

## Configuracao

Verificacoes:

- quantidade de tentativas segue padrao;
- feedback aparece quando esperado;
- atividade permite ou bloqueia progressao conforme objetivo;
- botao de reinicio segue padrao;
- instrucoes explicam a interacao;
- layout permite executar a atividade sem perder opcoes fora do ecran.

Problemas recorrentes:

- atividade com 3 tentativas quando o esperado era uma;
- feedback ausente;
- botao `Avancar` disponivel mesmo com resposta errada;
- nomes diferentes para a mesma acao: `Repor atividade`, `Reiniciar`, `Reiniciar atividade`;
- atividade longa demais para a area visivel.

## Enunciado

Verificacoes:

- enunciado claro;
- instrucao corresponde ao que aparece na tela;
- instrucao cita barra colorida ou mecanismo visual quando necessario;
- nao ha informacao repetida ou desnecessaria;
- exemplos sao adequados ao publico-alvo.

## Alternativas

Verificacoes:

- alternativas tem tamanho semelhante ou justificativa para diferenca;
- alternativa correta nao fica obvia por ser mais longa;
- alternativas erradas sao plausiveis;
- nao ha palavra que induz resposta por descarte sem intencao pedagogica;
- espacamento entre alternativas e regular.

Indicador recorrente:

- quando a resposta correta e muito mais comprida e explicada que as erradas, marcar como `manual_review` ou `major` conforme impacto.

## Feedback

Verificacoes:

- existe feedback quando esperado;
- feedback correto/incorreto tem estilo consistente;
- feedback nao tem espaco inicial;
- feedback nao repete instrucao desnecessaria;
- feedback usa termos oficiais corretamente;
- feedback nao contradiz o enunciado.

## Evidencia Minima

- URL da atividade.
- Screenshot antes da interacao.
- Screenshot/DOM do feedback quando testado.
- Enunciado.
- Alternativas.
- Gabarito quando disponivel.
- Configuracao de tentativas quando disponivel.

## Classificacao Sugerida

- `blocking`: atividade impossivel de responder ou concluir.
- `major`: gabarito/feedback/configuracao prejudica aprendizagem.
- `minor`: espacamento, texto pequeno, padronizacao simples.
- `manual_review`: qualidade pedagogica, plausibilidade de alternativas ou adequacao ao publico.
