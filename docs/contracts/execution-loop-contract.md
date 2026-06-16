# Contrato De Loop De Execucao

## Proposito

Garantir execucao previsivel, auditavel e facil de retomar para revisoes de curso.

## Regras Obrigatorias

1. Planejar antes de navegar ou revisar.
2. Executar um item de checklist por vez.
3. Registrar evidencia antes de concluir.
4. Manter estado compacto do run.
5. Fazer auditoria final antes do resumo.

## Checklist Inicial

Cada run deve criar checklist com:

- curso alvo
- modo de execucao
- escopo de paginas
- criterios de revisao
- estrategia de evidencia
- estrategia de captura unica por pagina, quando aplicavel
- itens de navegacao
- itens de midia
- itens de relatorio
- `Auditoria Final`

## Loop Por Item

Para cada item:

1. Abrir somente o contexto necessario.
2. Executar a acao.
3. Capturar evidencia.
4. Aplicar contrato objetivo.
5. Registrar resultado.
6. Marcar item como concluido, bloqueado ou revisao humana.

Para revisoes INA/NAU, a unidade primaria do loop deve ser o `pacote de pagina`: a pagina so pode ser marcada como visitada depois de capturados os dados definidos em `single-pass-capture-contract.md` ou depois de registrada uma lacuna explicita.

## Estados

- `pending`
- `in_progress`
- `passed`
- `failed`
- `blocked`
- `manual_review`
- `skipped_with_reason`

## Auditoria Final

Antes de entregar o resultado:

1. Verificar cobertura contra o manifest.
2. Confirmar que cada achado tem evidencia.
3. Confirmar que paginas nao visitadas estao explicitamente listadas.
4. Separar falhas tecnicas de revisoes humanas.
5. Confirmar que fases posteriores reutilizaram artefatos capturados antes de reabrir paginas.
6. Gerar resumo final.
