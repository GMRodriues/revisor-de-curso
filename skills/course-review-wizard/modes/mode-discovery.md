# Mode: Discovery

## Objetivo

Descobrir a estrutura do curso e produzir um manifest inicial.

Quando a descoberta exigir navegar pagina por pagina, ela deve capturar `page packets` completos conforme `docs/contracts/single-pass-capture-contract.md`. Nao descarte texto, screenshots, DOM, midia ou links coletados durante discovery; esses artefatos devem alimentar as fases seguintes.

## Entradas

- URL da plataforma
- curso alvo ou criterio de selecao
- estado de login/perfil de navegador
- escopo desejado

## Checklist

- [ ] Abrir plataforma
- [ ] Confirmar login
- [ ] Localizar curso alvo
- [ ] Detectar estrutura de modulos/aulas/paginas
- [ ] Preferir dados estruturados do DOM/API quando disponiveis
- [ ] Validar navegacao anterior/proximo
- [ ] Salvar page packets para paginas visitadas durante descoberta
- [ ] Criar manifest inicial
- [ ] Listar lacunas e ambiguidades
- [ ] Final Audit

## Saida

- manifest inicial
- page packets das paginas visitadas
- estrategia de navegacao
- riscos de cobertura
- recomendacao para `single-course-review`
