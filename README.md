# Curso Beta Test

Projeto para automatizar beta testing e revisao de cursos online em uma plataforma web.

O objetivo inicial e criar um fluxo de Curso Beta Test: navegar cursos, aulas e paginas; coletar evidencia; aplicar contratos objetivos de qualidade; e gerar relatorios que ajudem uma revisora humana a decidir se o material esta pronto para lancamento.

## Objetivos

- Automatizar revisao mecanica de carregamento, navegacao, formatacao e midia.
- Preservar evidencia verificavel: screenshots, logs, URLs e passos de reproducao.
- Separar criterios de revisao da operacao do navegador.
- Permitir calibracao com exemplos reais de revisao humana.
- Rodar em lote sem perder rastreabilidade por curso, modulo, aula e pagina.

## Fora de Escopo Inicial

- Corrigir conteudo diretamente na plataforma.
- Julgar qualidade pedagogica profunda sem revisao humana.
- Assistir integralmente todos os videos no MVP.
- Criar integracao permanente com repositorios ou sistemas de terceiros antes do fluxo estar validado.

## Estrutura

- `AGENTS.md`: instrucoes locais para agentes trabalhando neste projeto.
- `docs/articles/curso-beta-test-architecture.md`: artigo de arquitetura e abordagem.
- `docs/contracts/`: contratos de execucao, evidencia, navegador e rubrica.
- `docs/glossario-operacional.md`: vocabulario em portugues e excecoes tecnicas mantidas em ingles.
- `docs/phases/`: fases do fluxo de revisao.
- `docs/templates/`: modelos de manifest e relatorio.
- `skills/curso-beta-test/`: skill roteadora e modos de execucao.
- `artifacts/`: destino futuro para saidas de runs, screenshots e relatorios.
- `scripts/`: reservado para runners de navegador e utilitarios.

## Primeiro MVP

1. Revisar um curso ou modulo pequeno.
2. Descobrir a estrutura navegavel da plataforma.
3. Capturar screenshot, texto visivel, erros de console/network e estado de midia por pagina.
4. Gerar relatorio com achados objetivos e evidencias.
5. Comparar com revisao manual e ajustar a rubrica.
