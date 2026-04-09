# Banco API Performance

Projeto de testes de performance utilizando JavaScript com k6.

## Introdução

Este projeto tem como objetivo validar o desempenho da API bancária, garantindo que o sistema suporte diferentes níveis de carga e se comporte de forma estável.

## Tecnologias utilizadas

- JavaScript
- Grafana k6

## Estrutura do repositório

```
banco-api-performance/
├── fixtures/      # Dados de entrada dos testes
├── helpers/       # Funções utilitárias para interação com a API
├── tests/         # Casos de testes organizados por módulo da API
├── utils/         # Funções utilitárias e reutilizáveis
├── config/        # Variáveis de ambientes e configurações
└── README.md
```

## Objetivo de cada grupo de arquivos

- **fixtures/**: contém dados mockados utilizados nos testes (ex: login).
- **helpers/**: funções reutilizáveis, como geração de token.
- **tests/**: cenários de teste de performance.
- **utils/**: configurações como base URL.

## Configuração do ambiente

1. Instale o k6:
   https://k6.io/docs/getting-started/installation/

2. Verifique a instalação:
```
k6 --version
```
### 1. Clonar o repositório

```bash
git clone https://github.com/Adrianakellysl/banco-api-performance.git
cd banco-api-performance
```
## Configure as váriaveis de ambiente
Altere o arquivo `config.local.json` e defina a URL base da API a ser testada:
```json
{
  "baseUrl": "http://localhost:3000"
}
```
> Essas variáveis serão usadas dinamicamente nos testes para montar as requisições.

## Execute um teste com:
```
k6 run tests/login.test.js
```
Certifique-se de passar a váriavel de ambiente `BASE_URL`, caso não esteja usando um `config.local.json` ou uma abordagem de carregamento automático.

## Execução com dashboard web

Para gerar relatório HTML:

### Windows (cmd)
```
set "K6_WEB_DASHBOARD=true" && set "K6_WEB_DASHBOARD_EXPORT=html-report.html" && k6 run tests/login.test.js
```

Após a execução, será gerado o arquivo:

```
html-report.html
```
