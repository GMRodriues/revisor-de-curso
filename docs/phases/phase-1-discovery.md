# Fase 1: Descoberta

## Objetivo

Descobrir a estrutura navegavel do curso antes do revisao completa.

## Ordem Recomendada

1. Procurar manifest/API/DOM estruturado.
2. Mapear cursos, modulos, aulas e paginas.
3. Confirmar padrao de navegacao.
4. Registrar URLs, indices e titulos.
5. Detectar tipos de conteudo por pagina.

## Saidas

- course manifest
- mapa de navegacao
- paginas inacessiveis
- riscos de cobertura

## Protecoes

- Nao depender de clique cego se houver mapa estruturado.
- Nao inferir que uma pagina existe sem conseguir navegar ou encontra-la no manifest.
- Nao marcar descoberta completa se houver loop, pagina duplicada ou indice inconsistente sem registrar.

