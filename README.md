# Blog API TypeScript ✍️

Uma API RESTful para gerenciamento de blogs, permitindo a criação de postagens e comentários. Desenvolvida com **Node.js**, **TypeScript** e **SQLite**, com foco em uma estrutura de diretórios organizada por domínios DDD.

## 🚀 Funcionalidades

* **Postagens**: Criar, listar e visualizar posts específicos.
* **Comentários**: Adicionar e listar comentários vinculados a postagens específicas.
* **Auto-setup**: Criação automática das tabelas do banco de dados ao iniciar a aplicação.
* **Identificadores Únicos**: Uso de `uuid` para IDs de recursos.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** [TypeScript](https://www.typescriptlang.org/)
* **Framework:** [Express](https://expressjs.com/)
* **Banco de Dados:** [SQLite](https://www.sqlite.org/) (via `sqlite3` e `sqlite`)
* **Gerenciamento de IDs:** [UUID](https://github.com/uuidjs/uuid)
* **Ferramentas de Dev:** [ts-node-dev](https://github.com/wclr/ts-node-dev) (recarregamento automático)

## 📁 Estrutura de Domínios

O projeto organiza o código por "domínios" (posts e comments), facilitando a manutenção:

```text
src/
├── db/                # Configuração e inicialização do SQLite
├── domain/            # Lógica de negócio dividida por recursos
│   ├── posts/         # Rotas e Controllers de Postagens
│   └── comments/      # Rotas e Controllers de Comentários
└── index.ts           # Ponto de entrada da API

```

## 🔧 Instalação e Execução

1. **Clone o repositório:**
```bash
git clone https://github.com/jotor-dev/blog-api-ts.git
cd blog-api-ts
```
2. **Instale as dependências:**
```bash
npm install
```
3. **Inicie o servidor (Modo Desenvolvimento):**
O script `start` já está configurado com `ts-node-dev`:
```bash
npm start
```
A API estará disponível em `http://localhost:3000`.

## 🛣️ Endpoints da API

Todos os endpoints são prefixados com `/api`.

### Postagens

| Método | Rota | Descrição |
| --- | --- | --- |
| **GET** | `/api/posts` | Lista todos os posts |
| **GET** | `/api/posts/:id` | Detalhes de um post específico |
| **POST** | `/api/users` | Cria um novo post (Nota: rota atual no código) |

### Comentários

| Método | Rota | Descrição |
| --- | --- | --- |
| **GET** | `/api/posts/:id/comments` | Lista comentários de um post |
| **POST** | `/api/posts/:id/comments` | Adiciona comentário a um post |

## 📝 Observações 

* **Persistência:** O banco de dados SQLite é inicializado no arquivo `src/db/database.ts`.
* **Ids:** Ao criar posts ou comentários, o sistema gera automaticamente um `v4 UUID`.
