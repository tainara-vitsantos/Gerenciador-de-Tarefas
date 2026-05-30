# TaskManager 📝

> Um ecossistema completo e moderno para gerenciamento de tarefas (To-Do List), desenvolvido com uma API desacoplada em **C# (.NET 10)** e uma interface Single Page Application (SPA) dinâmica em **React**.

Esta aplicação foi construída seguindo o modelo cliente-servidor (Client/Server), apresentando um fluxo completo de autenticação, controle de estados globais via Context API, persistência de dados e uma interface moderna com Dark Mode nativo.

---

## 🛠️ Tecnologias e Dependências

### Back-end (Web API)
* **C# / .NET 10** - Plataforma de alta performance para a construção da API.
* **Scalar API Client** - Documentação interativa de última geração para testes de endpoints integrados (substituindo o Swagger clássico).
* **Entity Framework Core** - ORM para mapeamento objeto-relacional e persistência no banco de dados.

### Front-end (Web App)
* **React** - Biblioteca baseada em componentes reutilizáveis para a criação da interface.
* **Context API** - Gerenciamento nativo de estado global (sessão do usuário, autenticação e sincronização das tarefas).
* **Tailwind CSS** - Framework utilitário para estilização rápida e responsiva otimizada para o tema escuro.

---

## 📋 Mapeamento de Endpoints (Scalar)

A API organiza suas rotas por domínios e pode ser testada localmente em `http://localhost:5000/scalar`:

| Domínio | Método | Rota Básica | Descrição |
| :--- | :---: | :--- | :--- |
| **Auth** | `GET` | `/api/Auth/{id}` | Recupera o perfil e metadados do usuário logado. |
| **Auth** | `POST` | `/api/Auth/register` | Registra uma nova conta no sistema. |
| **Auth** | `POST` | `/api/Auth/login` | Autentica as credenciais e inicia a sessão. |
| **Tarefa** | `CRUD` | `/api/Tarefa` | Criação, listagem, edição e exclusão de tarefas. |
| **Comentario**| `CRUD` | `/api/Comentario` | Gerenciamento de anotações internas vinculadas às tarefas. |
| **Usuarios** | `CRUD` | `/api/Usuarios` | Administração de perfis de usuários do sistema. |

---

## 🎯 Funcionalidades Principais

* **Autenticação Completa:** Cadastro e login de usuários com persistência de dados de sessão.
* **Dashboard de Métricas:** Indicadores visuais na interface do usuário que calculam:
  * Total de tarefas criadas.
  * Quantidade de tarefas concluídas vs. pendentes.
  * Barra de progresso percentual dinâmica.
* **Interface Responsiva:** Alinhamento de cards, badges de status para prazos das tarefas (ex: *"estudar para p2"*) e botão de logout assistido.

---

## 📦 Como Executar o Projeto

### Pré-requisitos
Você precisará do **.NET 10 SDK** e do **Node.js** instalados globalmente na sua máquina.

### 1. Configurar e Rodar o Back-end (API)

Primeiro, instale a ferramenta do Entity Framework globalmente (caso ainda não tenha instalado em sua máquina):
```bash
dotnet tool install --global dotnet-ef