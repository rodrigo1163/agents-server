# NLW Agents

Projeto desenvolvido durante o evento **NLW (Next Level Week)** da [Rocketseat](https://rocketseat.com.br), focado na criação de uma aplicação backend com Node.js e integração com inteligência artificial.

## 🤖 Sobre o Projeto

O **NLW Agents** é uma plataforma backend robusta que alimenta uma aplicação web moderna para criação e gerenciamento de salas interativas com integração de inteligência artificial. Este servidor backend fornece:

- **API REST completa** para gerenciamento de salas e perguntas
- **Processamento de áudio** com conversão para texto e análise por IA
- **Integração com Google Gemini** para respostas inteligentes automatizadas
- **Armazenamento vetorial** utilizando pgvector para funcionalidades de IA/ML
- **Sistema de tempo real** para interações síncronas entre usuários

### Funcionalidades Principais

- **Criação e gerenciamento de salas temáticas**
- **Sistema de perguntas em tempo real**
- **Processamento de áudio** com transcrição automática
- **Integração com IA** para geração de respostas contextuais
- **Armazenamento otimizado** com PostgreSQL e extensões vetoriais
- **API type-safe** com validação completa de dados

O backend serve como a base sólida para uma experiência de usuário fluida e responsiva, demonstrando na prática como construir APIs escaláveis integradas com inteligência artificial moderna.

> **📋 Projeto Backend**: Esta é a API do NLW Agents. Para uma experiência completa, recomenda-se também configurar o frontend web que consome esta API.

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

### Inteligência Artificial

- **Google Gemini API** - Modelo de linguagem para processamento de texto e áudio
- **Embeddings vetoriais** - Armazenamento e busca semântica com pgvector
- **Processamento de áudio** - Transcrição automática e análise contextual

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
- `GET /rooms` - Lista todas as salas disponíveis
- `POST /rooms` - Cria uma nova sala temática
- `GET /rooms/:roomId/questions` - Lista as perguntas de uma sala específica
- `POST /rooms/:roomId/questions` - Cria uma nova pergunta em uma sala
- `POST /upload-audio` - Upload e processamento de áudio com transcrição automática

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
