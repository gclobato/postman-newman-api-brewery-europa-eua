# Open Brewery API QA

Projeto de automação de testes de API utilizando Postman e Newman.

## Tecnologias
- Postman
- Newman
- Open Brewery DB API

## Estrutura
```text
openbrewery-api-qa/
│
├── collections/
├── environments/
├── reports/
└── README.md
```

## Instalação do Newman

```bash
npm install -g newman
```

## Executar os testes

```bash
newman run collections/openbrewery_collection.json -e environments/openbrewery_environment.json
```

## Gerar relatório HTML

Instalar reporter:

```bash
npm install -g newman-reporter-htmlextra
```

Executar:

```bash
newman run collections/openbrewery_collection.json ^
-r cli,htmlextra ^
--reporter-htmlextra-export reports/report.html
```

## Cobertura dos testes
- Status code
- Tempo de resposta
- Estrutura do JSON
- Paginação
- Campos obrigatórios
