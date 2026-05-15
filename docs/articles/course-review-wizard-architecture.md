# Course Review Wizard Architecture

## Context

O projeto automatiza revisao de cursos online em uma plataforma web. A plataforma apresenta conteudo em paginas ou slides navegados por setas, podendo incluir texto, imagem, texto dentro de imagem, video e outros componentes.

O objetivo nao e substituir a revisao humana. O objetivo e reduzir trabalho repetitivo, encontrar falhas mecanicas com evidencia e apontar onde revisao humana ainda e necessaria.

## Design Central

Separar duas responsabilidades:

1. Operacao da plataforma: login, navegacao, clique, captura de tela, leitura de DOM, coleta de logs, teste de midia.
2. Criterios de review: regras que dizem se algo carregou corretamente, se texto esta visivel, se midia funciona, se ha overflow, se a pagina esta pronta ou precisa de revisao humana.

Essa separacao permite trocar o operador de navegador sem reescrever a rubrica, e ajustar a rubrica sem mexer no runner.

## Camadas

### Course Manifest

Representa o mapa esperado:

- curso
- modulo
- aula
- pagina ou slide
- URL ou rota
- tipo de conteudo esperado
- criterios especificos

O manifest pode vir de API, DOM, planilha, export manual ou descoberta automatica.

### Browser Runner

Responsavel por executar a plataforma:

- abrir curso
- navegar paginas
- aguardar estabilidade
- capturar screenshot
- coletar console/network errors
- extrair texto visivel
- inspecionar imagens e videos
- registrar passos de reproducao

### Review Engine

Aplica contratos:

- carregamento completo
- navegacao funcionando
- imagens carregadas
- videos iniciam e possuem duracao
- ausencia de erros criticos
- texto nao cortado
- conteudo essencial presente
- layout sem sobreposicao obvia

### Report Builder

Gera saidas:

- relatorio executivo por curso
- tabela de achados
- evidencia por pagina
- lista de bloqueios
- itens para revisao humana

## MVP Recomendado

1. Escolher um curso pequeno.
2. Criar ou descobrir manifest.
3. Rodar revisao automatizada em desktop.
4. Capturar screenshots e logs por pagina.
5. Gerar relatorio markdown.
6. Comparar com revisao manual.
7. Ajustar contratos antes de rodar em lote.

## Riscos

- Falsos positivos por animacoes ou loaders lentos.
- Textos dentro de imagem exigem OCR para revisao real.
- Videos podem carregar mas ter problema depois de varios minutos.
- Layout responsivo pode quebrar apenas em mobile.
- Conteudo pedagogico e didatico exige criterio humano.
- Plataformas com login, anti-bot ou sessao instavel podem exigir perfil de navegador dedicado.

## Decisao Inicial

Comecar com contratos e evidencia. Codigo de automacao deve vir depois que a rubrica e o formato de relatorio estiverem claros o suficiente para validar um curso pequeno.

