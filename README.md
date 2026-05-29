# Open Brewery API QA

Projeto de automação de testes de API utilizando Postman e Newman com a API pública Open Brewery DB.

## Tecnologias utilizadas

* Postman
* Newman
* Node.js
* Open Brewery DB API

---

# Estrutura do projeto

```text
openbrewery-api-qa/
│
├── collections/
│   └── openbrewery_collection.json
│
├── environments/
│   └── openbrewery_environment.json
│
├── reports/
│
├── package.json
│
└── README.md
```

---

# Pré-requisitos

Instalar:

* Node.js
* Postman

## Download Node.js

[https://nodejs.org](https://nodejs.org)

## Download Postman

[https://www.postman.com/downloads/](https://www.postman.com/downloads/)

---

# Instalação do Newman

Após instalar o Node.js, execute:

```bash
npm install -g newman
```

Para validar a instalação:

```bash
newman -v
```

---

# Importar no Postman

## 1. Abrir o Postman

Clique em:

```text
Import
```

---

## 2. Importar Collection

Importe o arquivo:

```text
collections/openbrewery_collection.json
```

---

## 3. Importar Environment

Importe o arquivo:

```text
environments/openbrewery_environment.json
```

---

## 4. Selecionar Environment

No canto superior direito do Postman selecione:

```text
Open Brewery Environment
```

---

# Executar os testes no Postman

## Executar Collection

1. Clique na Collection:

```text
Open Brewery API QA
```

2. Clique em:

```text
Run collection
```

3. Clique em:

```text
Run Open Brewery API QA
```

---

# Executar os testes com Newman

## Instalar dependências locais

```bash
npm install
```

---

## Executar via npm

```bash
npm test
```

---

## Executar diretamente com Newman

```bash
newman run collections/openbrewery_collection.json -e environments/openbrewery_environment.json
```

---

# Gerar relatório HTML

## Instalar reporter

```bash
npm install -g newman-reporter-htmlextra
```

---

## Executar com relatório

### Windows

```bash
newman run collections/openbrewery_collection.json ^
-e environments/openbrewery_environment.json ^
-r cli,htmlextra ^
--reporter-htmlextra-export reports/report.html
```

---

### Linux/Mac

```bash
newman run collections/openbrewery_collection.json \
-e environments/openbrewery_environment.json \
-r cli,htmlextra \
--reporter-htmlextra-export reports/report.html
```

---

# Testes implementados

## Cenários cobertos

* Validação de status code
* Tempo de resposta
* Quantidade de registros
* Validação de campos obrigatórios
* Validação de estrutura JSON

---

# Endpoint utilizado

API pública:

[https://api.openbrewerydb.org/v1/breweries](https://api.openbrewerydb.org/v1/breweries)

---

# Exemplo de saída esperada

```text
✓ Status code is 200
✓ Response time is below 2000ms
✓ Response contains 3 breweries
✓ First brewery has required fields
```

---

# Melhorias futuras

* Schema validation
* Data-driven testing
* Integração CI/CD
* GitHub Actions
* Docker
* Testes negativos
* Relatórios automatizados
