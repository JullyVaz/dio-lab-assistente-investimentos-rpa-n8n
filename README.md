# Assistente de Investimentos — RPA com n8n e IA Generativa

## Sobre o projeto

Este projeto foi desenvolvido a partir do laboratório da Digital Innovation One (DIO), com o objetivo de automatizar a extração de dados de clientes, integrar sistemas por meio de Webhooks e gerar mensagens personalizadas de recomendação de investimentos.

A implementação combina Python, n8n, JavaScript e Inteligência Artificial Generativa para demonstrar um fluxo de automação de ponta a ponta.

## Objetivos

- Automatizar a extração de dados de clientes fictícios.
- Integrar Python e n8n por meio de um Webhook HTTP.
- Consultar opções de investimentos organizadas por perfil.
- Processar o perfil do investidor e o saldo disponível.
- Gerar recomendações compatíveis com os critérios definidos no workflow.
- Utilizar IA generativa para produzir mensagens personalizadas.
- Organizar os resultados em formato JSON.

## Tecnologias utilizadas

- **Python:** extração de dados e integração HTTP.
- **Google Colab:** execução e testes do notebook Python.
- **BeautifulSoup:** extração de informações da página HTML.
- **n8n Cloud:** orquestração do workflow de automação.
- **Webhook HTTP (POST):** recebimento dos dados dos clientes.
- **HTTP Request:** consulta de dados externos.
- **JavaScript:** processamento, combinação e validação dos dados.
- **CSV:** armazenamento das opções de investimento.
- **IA generativa (LLM):** geração de mensagens personalizadas.
- **Git e GitHub:** versionamento e documentação do projeto.

## Arquitetura da solução

O fluxo de automação é composto pelas seguintes etapas:

1. **Extração dos dados:** o notebook Python acessa a página de clientes e extrai nome, e-mail, saldo e perfil do investidor.
2. **Integração via Webhook:** os dados extraídos são enviados do Google Colab para o n8n por meio de uma requisição HTTP POST.
3. **Consulta de investimentos:** o workflow consulta as opções disponíveis e seus critérios, incluindo perfil e aplicação mínima.
4. **Combinação e processamento:** os nós Merge e Code organizam e processam os dados recebidos.
5. **Análise de compatibilidade:** a lógica JavaScript relaciona o perfil e o saldo de cada cliente às opções disponíveis.
6. **Geração de mensagens:** o agente de IA utiliza o contexto do cliente e os dados processados para elaborar mensagens personalizadas.
7. **Organização da resposta:** os resultados são estruturados em JSON, com informações do cliente e conteúdo da mensagem gerada.

## Regras de recomendação

O processamento considera três perfis de investidores:

- **Conservador:** prioriza opções compatíveis com uma abordagem mais conservadora.
- **Moderado:** considera opções adequadas ao perfil moderado.
- **Arrojado:** considera opções adequadas ao perfil arrojado.

A seleção também considera o saldo disponível e o valor mínimo de aplicação informado nos dados de investimentos.

As recomendações são baseadas nos dados fictícios e nas regras implementadas no workflow. As mensagens geradas por IA têm caráter informativo e não constituem aconselhamento financeiro individualizado.

## Estrutura do projeto

- `docs/index.html`: página de clientes fictícios disponibilizada pelo projeto original.
- `docs/data.csv`: dados das opções de investimento.
- `src/extrair_clientes.ipynb`: notebook Python para extração e envio dos dados.
- `n8n/workflow.json`: arquivo previsto para a exportação do workflow do n8n.
- `docs/evidencias/`: diretório destinado às capturas de tela das execuções.

> Observação: os arquivos `n8n/workflow.json` e `docs/evidencias/` devem ser adicionados ao repositório caso ainda não estejam presentes.

## Como executar

1. Abra o notebook `src/extrair_clientes.ipynb` no Google Colab.
2. Configure a URL do Webhook de acordo com o ambiente n8n.
3. Abra o workflow no n8n e prepare-o para receber a requisição.
4. Execute o notebook Python para extrair e enviar os dados dos clientes.
5. Acompanhe a execução dos nós no n8n.
6. Confira os resultados processados e as mensagens geradas pela IA.

Para reproduzir o projeto, configure as credenciais e os parâmetros necessários no seu próprio ambiente. Não publique chaves de API, tokens ou outras informações confidenciais.

## Resultados e evidências

Os testes realizados demonstraram:

- Extração de 10 clientes fictícios pelo notebook Python.
- Comunicação entre o Google Colab e o Webhook do n8n.
- Processamento de dados de clientes e opções de investimento.
- Retorno de resultados estruturados em JSON.
- Geração de mensagens personalizadas com assunto, corpo em texto e corpo HTML pela IA generativa.

As capturas de tela das execuções devem ser adicionadas ao repositório para documentar visualmente essas etapas.

## Aprendizados

O desenvolvimento permitiu praticar web scraping, integração entre sistemas, requisições HTTP, processamento de dados em JavaScript, automação de workflows e integração com modelos de linguagem.

O projeto também demonstra como a combinação de RPA e IA generativa pode automatizar tarefas de integração e personalização de mensagens.

## Créditos

Projeto original: **Digital Innovation One (DIO)**.

Repositório-base: [dio-lab-assistente-investimentos-rpa-n8n](https://github.com/digitalinnovationone/dio-lab-assistente-investimentos-rpa-n8n).

Implementação, testes e documentação das extensões realizados neste fork.
