# Mode: Batch Review

## Objetivo

Revisar varios cursos ou modulos com isolamento por unidade de trabalho.

## Pre-Requisito

Usar somente depois que `single-course-review` estiver calibrado em pelo menos um curso pequeno.

## Checklist

- [ ] Normalizar lista de cursos
- [ ] Confirmar escopo por curso
- [ ] Criar manifest ou validar manifest existente por curso
- [ ] Definir ordem e limites de concorrencia
- [ ] Rodar review por curso
- [ ] Consolidar achados
- [ ] Consolidar cobertura
- [ ] Gerar resumo executivo
- [ ] Final Audit

## Guardrails

- Nao misturar evidencias de cursos diferentes.
- Nao declarar sucesso global se algum curso ficou sem cobertura clara.
- Nao rodar concorrencia contra a mesma sessao/pagina sem isolamento.

## Saida

- status por curso
- achados agregados
- bloqueios por curso
- proximas acoes priorizadas

