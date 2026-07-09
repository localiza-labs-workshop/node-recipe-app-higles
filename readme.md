# Aplicativo de Receitas (Recipe App)

Este é um pequeno aplicativo de receitas, intencionalmente incompleto, criado para ser utilizado em workshops do GitHub Copilot.

- Desenvolvido com **Node.js**, **Express**, **Handlebars** e **SQLite**.
- Cria e popula o banco de dados automaticamente na primeira execução.
- Suporta criação, listagem e edição de receitas.

---

## Sumário

- [Visão Geral](#visão-geral)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Pré-requisitos](#pré-requisitos)
- [Como Executar](#como-executar)
- [Endpoints da API](#endpoints-da-api)
- [Testes](#testes)
- [Ideias de Melhorias](#ideias-de-melhorias)
- [Licença](#licença)
- [Suporte e Contribuições](#suporte-e-contribuições)

---

## Visão Geral

O **Aplicativo de Receitas** é uma aplicação web simples para gerenciar receitas culinárias. Ele foi projetado para ser usado como base em workshops do GitHub Copilot, onde os participantes podem explorar e ampliar suas funcionalidades com o auxílio da IA.

---

## Tecnologias Utilizadas

| Tecnologia | Descrição |
|---|---|
| [Node.js](https://nodejs.org/) | Ambiente de execução JavaScript no servidor |
| [Express](https://expressjs.com/) | Framework web para Node.js |
| [Express Handlebars](https://github.com/express-handlebars/express-handlebars) | Motor de templates para renderização de páginas HTML |
| [SQLite](https://www.sqlite.org/) | Banco de dados leve e sem servidor |
| [Jest](https://jestjs.io/) | Framework de testes |
| [Supertest](https://github.com/ladjs/supertest) | Biblioteca para testes de integração HTTP |

---

## Estrutura do Projeto

```
node-recipe-app/
├── __tests__/           # Testes automatizados
│   ├── database.test.js
│   ├── routes.test.js
│   ├── test-database.js
│   └── test-setup.js
├── public/              # Arquivos estáticos (CSS, imagens)
├── src/
│   ├── database/        # Conexão, esquema e dados iniciais do banco
│   │   ├── connection.js
│   │   ├── index.js
│   │   ├── schema.js
│   │   └── seedData.js
│   └── routes.js        # Definição das rotas da aplicação
├── views/               # Templates Handlebars
│   ├── layouts/
│   ├── home.hbs
│   ├── recipe.hbs
│   └── recipes.hbs
├── index.js             # Ponto de entrada da aplicação
├── package.json
└── readme.md
```

---

## Pré-requisitos

- [Node.js](https://nodejs.org/) (versão 16 ou superior recomendada)
- [npm](https://www.npmjs.com/) (incluso com o Node.js)

---

## Como Executar

### Opção 1: GitHub Codespaces (recomendado para workshops)

**Clique com o botão direito no botão abaixo para abrir o Codespace em uma nova aba:**

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1026168589)

### Opção 2: Dev Containers (localmente)

Você também pode executar a aplicação localmente usando [Dev Containers](https://containers.dev/) com o Visual Studio Code.

### Opção 3: Execução local sem contêiner

Execute os seguintes comandos no terminal:

```bash
# Instalar dependências
npm install

# Iniciar a aplicação
npm start
```

Acesse `http://localhost:3000` para começar a gerenciar suas receitas.

#### Modo de desenvolvimento (com reinicialização automática)

```bash
npm run dev
```

---

## Endpoints da API

| Método | Rota | Descrição |
|--------|------|-----------|
| `GET` | `/` | Página inicial |
| `GET` | `/recipes` | Lista todas as receitas |
| `GET` | `/recipes/:id` | Exibe os detalhes de uma receita |
| `POST` | `/recipes` | Cria uma nova receita |
| `POST` | `/recipes/:id/edit` | Atualiza uma receita existente |

### Exemplo de corpo da requisição para criar/editar uma receita

```json
{
  "title": "Bolo de Cenoura",
  "ingredients": "2 cenouras\n2 ovos\n1 xícara de óleo\n2 xícaras de farinha\n1 xícara de açúcar",
  "method": "Bata as cenouras, ovos e óleo no liquidificador\nMisture os ingredientes secos\nUna as misturas e asse a 180°C por 40 minutos"
}
```

---

## Testes

Para executar os testes automatizados:

```bash
npm test
```

Para executar os testes em modo observador (útil durante o desenvolvimento):

```bash
npm run test:watch
```

---

## Ideias de Melhorias

Sugestões de funcionalidades que podem ser implementadas como exercício nos workshops:

- Endpoint `/recipes/random` para selecionar uma receita aleatória.
- Funcionalidade de exclusão de receitas pela interface web.
- Busca de receitas por nome ou ingrediente.
- Suporte a múltiplas unidades de medida nas receitas.
- Paginação na listagem de receitas.
- Sistema de categorias ou tags para organizar as receitas.
- Upload de imagens para as receitas.

---

## Licença

Este projeto está licenciado sob os termos da licença de código aberto MIT. Consulte o arquivo [LICENSE](https://github.com/github-samples/node-recipe-app/blob/main/LICENSE) para obter os termos completos.

---

## Suporte e Contribuições

Este repositório não possui suporte oficial. Ele é atualizado periodicamente conforme as necessidades dos workshops onde é utilizado. No momento, não aceitamos contribuições externas.
