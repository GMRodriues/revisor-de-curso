# Mode: Batch Review

## Objetivo

Revisar varios cursos ou modulos com isolamento por unidade de trabalho.

## Pre-Requisito

Usar somente depois que `ina-nau-course-review` ou `single-course-review` estiver calibrado em pelo menos um curso pequeno.

## Checklist

- [ ] Normalizar lista de cursos
- [ ] Confirmar escopo por curso
- [ ] Criar manifest ou validar manifest existente por curso
- [ ] Definir ordem e limites de concorrencia
- [ ] Rodar review por curso com isolamento de run directory e page packets
- [ ] Consolidar achados
- [ ] Consolidar cobertura
- [ ] Gerar resumo executivo
- [ ] Final Audit

## Guardrails

- Nao misturar evidencias de cursos diferentes.
- Nao declarar sucesso global se algum curso ficou sem cobertura clara.
- Nao rodar concorrencia contra a mesma sessao/pagina sem isolamento.
- Nao reutilizar page packets de outro curso, outra versao ou outro reteste sem registrar a origem.

## Saida

- status por curso
- achados agregados
- bloqueios por curso
- proximas acoes priorizadas
