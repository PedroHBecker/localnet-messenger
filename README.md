# 💬 LocalNet Messenger

Sistema de mensagens em grupo para **rede local**, com uma **API REST em C# (.NET 8)** e uma **interface web em React + TypeScript**. Os usuários se cadastram, entram em grupos e trocam mensagens em um mural compartilhado.

## ✨ Funcionalidades

- **Usuários:** cadastro, acesso pelo e-mail, edição de perfil e exclusão
- **Grupos:** criar, editar, excluir e listar grupos; entrar em um grupo
- **Mensagens:** enviar, editar, excluir e listar as mensagens de cada grupo, com autor e data/hora
- **Consultas:** listar os membros de um grupo e os grupos de um usuário

## 🛠️ Tecnologias

**Back-end (`LocalNet.API`)**
- C# com **ASP.NET Core 8** (Minimal APIs)
- **Entity Framework Core** com **SQLite** e migrations
- CORS configurado para o front-end

**Front-end (`LocalNet.UI`)**
- **React 19** + **TypeScript**
- **React Router** para navegação entre páginas
- **Axios** para consumir a API

## 📁 Estrutura

```
localnet-messenger/
├── LocalNet.API/     # API REST: Program.cs (rotas), Models, Data (DbContext), Migrations
└── LocalNet.UI/      # Front-end React: pages, components, services, models
```

## 🔌 Principais rotas da API

| Método | Rota | Descrição |
|---|---|---|
| POST | `/api/usuario/cadastrar` | Cadastra um usuário |
| GET | `/api/usuario/listar` | Lista os usuários |
| POST | `/api/usuario/entrar-grupo` | Adiciona um usuário a um grupo |
| GET | `/api/grupo` | Lista os grupos |
| POST | `/api/grupo/cadastrar` | Cria um grupo |
| GET | `/api/mensagem/listar/{grupoId}` | Lista as mensagens de um grupo |
| POST | `/api/mensagem/cadastrar` | Envia uma mensagem |

## ▶️ Como executar

**Pré-requisitos:** .NET 8 SDK e Node.js

1. Clone o repositório:
   ```bash
   git clone https://github.com/PedroHBecker/localnet-messenger.git
   cd localnet-messenger
   ```
2. Suba a API (roda em `http://localhost:8080`):
   ```bash
   cd LocalNet.API
   dotnet run --launch-profile http
   ```
3. Em outro terminal, suba o front-end (abre em `http://localhost:3000`):
   ```bash
   cd LocalNet.UI
   npm install
   npm start
   ```

## 👥 Sobre

Projeto desenvolvido em equipe como projeto final da disciplina de **Tópicos Especiais em Sistemas (C#)** do curso de Análise e Desenvolvimento de Sistemas da Universidade Positivo.
