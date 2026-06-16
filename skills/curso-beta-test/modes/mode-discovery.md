# Modo: Descoberta

## Objetivo

Descobrir a estrutura do curso e produzir um manifest inicial.

Quando a descoberta exigir navegar pagina por pagina, ela deve capturar `pacotes de pagina` completos conforme `docs/contracts/single-pass-capture-contract.md`. Nao descarte texto, screenshots, DOM, midia ou links coletados durante a descoberta; esses artefatos devem alimentar as fases seguintes.

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
- [ ] Salvar pacotes de pagina para paginas visitadas durante descoberta
- [ ] Criar manifest inicial
- [ ] Listar lacunas e ambiguidades
- [ ] Auditoria Final

## Saida

- manifest inicial
- pacotes de pagina das paginas visitadas
- estrategia de navegacao
- riscos de cobertura
- recomendacao para `single-course-review`
