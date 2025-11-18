# Trilha NET API - Desafio

Sistema gerenciador de tarefas desenvolvido como desafio da trilha .NET da DIO. Uma API REST completa com operações CRUD para gerenciar tarefas do dia a dia.

**Acesse em:** www.dio.me

## 🚀 Status do Projeto

✅ **COMPLETO E FUNCIONAL**

Todos os endpoints foram implementados e testados com sucesso!

## 📋 Tecnologias Utilizadas

- **.NET 8.0**
- **Entity Framework Core 8.0**
- **SQLite** (Banco de dados)
- **Swagger/OpenAPI** (Documentação interativa)
- **C#**

## 🎯 Funcionalidades Implementadas

A aplicação oferece um CRUD completo para tarefas:

- ✅ **Criar** nova tarefa (POST)
- ✅ **Listar** todas as tarefas (GET)
- ✅ **Buscar** tarefa por ID (GET)
- ✅ **Buscar** tarefas por título (GET)
- ✅ **Buscar** tarefas por data (GET)
- ✅ **Buscar** tarefas por status (GET)
- ✅ **Atualizar** tarefa existente (PUT)
- ✅ **Deletar** tarefa (DELETE)

## 📦 Estrutura do Projeto

```
trilha-net-api-desafio/
├── Controllers/
│   └── TarefaController.cs          # Endpoints da API
├── Models/
│   ├── Tarefa.cs                    # Modelo principal
│   └── EnumStatusTarefa.cs          # Enum de status
├── Context/
│   └── OrganizadorContext.cs        # DbContext do EF Core
├── Migrations/
│   └── [arquivos de migração]       # Histórico de alterações no BD
├── appsettings.json                 # Configurações gerais
├── appsettings.Development.json     # Configurações de desenvolvimento
├── Program.cs                       # Setup da aplicação
└── README.md                        # Este arquivo
```

## 🚀 Como Executar

### Pré-requisitos

- .NET 8.0 SDK instalado
- Git (opcional)

### Passos

1. **Clone o repositório:**

```bash
git clone https://github.com/GtxSantos/TRILHA-NET-API-DESAFIO.git
cd TRILHA-NET-API-DESAFIO
```

2. **Restaure os pacotes NuGet:**

```bash
dotnet restore
```

3. **Execute a aplicação:**

```bash
dotnet run
```

4. **Acesse o Swagger:**

- HTTPS: https://localhost:7295/swagger/index.html
- HTTP: http://localhost:5181/swagger/index.html

## 📡 Endpoints da API

| Método | Endpoint | Descrição | Parâmetro |
|--------|----------|-----------|-----------|
| GET | `/Tarefa/{id}` | Obter tarefa por ID | id (int) |
| GET | `/Tarefa/ObterTodos` | Listar todas as tarefas | - |
| GET | `/Tarefa/ObterPorTitulo` | Buscar por título | titulo (string) |
| GET | `/Tarefa/ObterPorData` | Buscar por data | data (DateTime) |
| GET | `/Tarefa/ObterPorStatus` | Buscar por status | status (enum) |
| POST | `/Tarefa` | Criar nova tarefa | Objeto Tarefa |
| PUT | `/Tarefa/{id}` | Atualizar tarefa | id (int), Objeto Tarefa |
| DELETE | `/Tarefa/{id}` | Deletar tarefa | id (int) |

## 📝 Schema da Tarefa

```json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2025-11-18T00:00:00.000Z",
  "status": "Pendente"
}
```

### Campos

- **id**: Identificador único (auto-incremental)
- **titulo**: Título da tarefa (obrigatório)
- **descricao**: Descrição detalhada da tarefa
- **data**: Data da tarefa (não pode ser vazia)
- **status**: Status da tarefa (Pendente ou Finalizado)

## 📊 Status da Tarefa

A tarefa pode ter dois status:

- `Pendente` - Tarefa ainda não concluída
- `Finalizado` - Tarefa concluída

## 🔍 Exemplos de Uso

### Criar uma Tarefa

```bash
POST /Tarefa
Content-Type: application/json

{
  "titulo": "Estudar C#",
  "descricao": "Aprender conceitos avançados de C#",
  "data": "2025-11-20",
  "status": "Pendente"
}
```

### Buscar Tarefa por ID

```bash
GET /Tarefa/1
```

### Listar Todas as Tarefas

```bash
GET /Tarefa/ObterTodos
```

### Buscar por Título

```bash
GET /Tarefa/ObterPorTitulo?titulo=Estudar
```

### Atualizar Tarefa

```bash
PUT /Tarefa/1
Content-Type: application/json

{
  "titulo": "Estudar C# Avançado",
  "descricao": "Aprender conceitos avançados de C#",
  "data": "2025-11-21",
  "status": "Finalizado"
}
```

### Deletar Tarefa

```bash
DELETE /Tarefa/1
```

## 🗄️ Banco de Dados

O projeto utiliza **SQLite** para persistência de dados. O arquivo `TrilhaApiDesafio.db` é criado automaticamente na raiz do projeto durante a primeira execução.

### Tabela: Tarefas

| Coluna | Tipo | Restrições |
|--------|------|-----------|
| Id | INTEGER | PRIMARY KEY, AUTOINCREMENT |
| Titulo | TEXT | NULL |
| Descricao | TEXT | NULL |
| Data | TEXT | NOT NULL |
| Status | INTEGER | NOT NULL |

## 🛠️ Configuração

### appsettings.Development.json

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "ConnectionStrings": {
    "ConexaoPadrao": "Data Source=TrilhaApiDesafio.db"
  }
}
```

## 📚 Dependências do Projeto

- Microsoft.EntityFrameworkCore.Design (8.0.0)
- Microsoft.EntityFrameworkCore.Sqlite (8.0.0)
- Swashbuckle.AspNetCore (6.2.3)

## 🎓 Conceitos Implementados

- ✅ Entity Framework Core (ORM)
- ✅ Injeção de Dependência
- ✅ CRUD Operations
- ✅ RESTful API
- ✅ Validação de Dados
- ✅ Migrations
- ✅ Swagger Documentation
- ✅ Tratamento de Erros HTTP (200, 201, 204, 400, 404)
- ✅ LINQ

## 🔧 Comandos Úteis

```bash
# Restaurar dependências
dotnet restore

# Build do projeto
dotnet build

# Executar a aplicação
dotnet run

# Criar nova migration
dotnet ef migrations add NomeDaMigration

# Aplicar migrations ao banco de dados
dotnet ef database update
```

## 👤 Autor

**GtxSantos**

- GitHub: https://github.com/GtxSantos

## 🤝 Contribuições

Sugestões e melhorias são bem-vindas!

---

**Desenvolvido com ❤️ para a comunidade DIO**

Desafio concluído com sucesso! ✨
