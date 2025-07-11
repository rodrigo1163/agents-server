# NLW Agents

Projeto desenvolvido durante o evento **NLW (Next Level Week)** da [Rocketseat](https://rocketseat.com.br), focado na criação de uma aplicação backend com Node.js e integração com inteligência artificial.

## 🚀 Tecnologias Utilizadas

### Backend

- **Node.js** - Runtime JavaScript/TypeScript
- **TypeScript** - Tipagem estática (com experimental strip types)
- **Fastify** - Framework web performático
- **Drizzle ORM** - ORM type-safe para TypeScript
- **Zod** - Validação de schemas e dados
- **PostgreSQL** - Banco de dados relacional

### Infraestrutura

- **Docker** - Containerização
- **pgvector** - Extensão PostgreSQL para vetores (AI/ML)

## 🏗️ Padrões de Projeto

- **Modular Architecture** - Separação em módulos (db, http, routes)
- **Type-safe API** - Integração Fastify + Zod para tipagem completa
- **Schema-first** - Definição de schemas com Drizzle ORM
- **Environment Configuration** - Configuração via variáveis de ambiente

## 📋 Pré-requisitos

- Node.js (versão 18+)
- Docker e Docker Compose
- Git

## ⚙️ Configuração e Setup

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd server
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
```

### 4. Inicie o banco de dados

```bash
docker-compose up -d
```

### 5. Execute as migrações

```bash
npx drizzle-kit migrate
```

### 6. Popule o banco (opcional)

```bash
npm run db:seed
```

## 🔧 Scripts Disponíveis

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm start` - Inicia o servidor em modo produção
- `npm run db:seed` - Popula o banco com dados iniciais

## 📡 Endpoints

A API estará disponível em `http://localhost:3333`

### Principais rotas:

- `GET /health` - Health check da aplicação
- `GET /rooms` - Lista as salas disponíveis

## 🐳 Docker

O projeto utiliza Docker Compose para facilitar o setup do ambiente de desenvolvimento:

- **PostgreSQL** com extensão pgvector na porta 5432
- Dados persistidos em volume local
- Script de inicialização automática

## 🚀 Como executar

1. Execute o setup completo conforme as instruções acima
2. Inicie o servidor: `npm run dev`
3. Acesse `http://localhost:3333/health` para verificar se a API está funcionando

---

Desenvolvido com ❤️ durante o **NLW Agents** da [Rocketseat](https://rocketseat.com.br)
