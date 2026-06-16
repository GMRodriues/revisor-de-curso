# Curso Beta Test Agent Instructions

Estas instrucoes valem dentro deste projeto. Este projeto e independente do Gravity e nao deve depender de arquivos, runtime, schemas ou convencoes privadas do monorepo MindCloud, exceto quando um humano pedir explicitamente para importar uma ideia como referencia.

## Principios

- Evidencia antes de conclusao: todo achado precisa ter URL, pagina/slide, screenshot contextual obrigatorio e, quando aplicavel, screenshot focado ou log associado.
- Contratos objetivos antes de julgamento subjetivo: separar falhas mecanicas de opinioes editoriais.
- Navegacao deterministica: preferir manifest/API/DOM estruturado a clicar setas cegamente.
- Menor escopo verificavel: validar primeiro um curso pequeno antes de rodar lote.
- Revisao humana no loop: calibrar falsos positivos e falsos negativos com exemplos reais.
- Nao gravar credenciais, cookies, tokens ou dados pessoais em docs permanentes.

## Execucao Padrao

1. Classificar a tarefa em uma fase ou modo.
2. Criar plano antes de operar navegador ou gerar artefatos.
3. Executar um item de checklist por vez.
4. Salvar evidencia por curso/modulo/aula/pagina.
5. Gerar relatorio com severidade, reproducao e evidencia.
6. Encerrar com resumo claro de pronto, bloqueado e precisa de revisao humana.

## Qualidade Da Revisao

Classificar cada achado como:

- `blocking`: impede lancamento ou acesso ao conteudo.
- `major`: problema relevante para aluno, mas com workaround.
- `minor`: polimento, typo visual, desalinhamento leve.
- `manual_review`: exige julgamento humano ou criterio ainda nao formalizado.

Todo achado deve indicar:

- localizacao exata
- comportamento esperado
- comportamento observado
- evidencia
- screenshot contextual mostrando a area ao redor do erro
- severidade
- recomendacao

## Fronteiras

- Nao criar automacoes destrutivas na plataforma.
- Nao alterar conteudo do curso sem pedido explicito.
- Nao assumir que uma pagina esta correta so porque nao houve erro tecnico.
- Nao marcar curso como pronto sem cobrir todas as paginas exigidas pelo manifest ou sem registrar lacunas.
