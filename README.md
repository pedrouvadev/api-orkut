# API Orkut

**Uma API RESTful inspirada na rede social Orkut, recriando as funcionalidades core de uma das redes sociais mais icônicas do Brasil.**

## **Tecnologias Utilizadas**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![bcrypt](https://img.shields.io/badge/bcrypt-4E0C7C?style=for-the-badge&logo=bcrypt&logoColor=white)
![Joi](https://img.shields.io/badge/Joi-3A5B8A?style=for-the-badge&logo=joi&logoColor=white)

## **Funcionalidades (Features)**

- **Autenticação de Usuários**: Sistema completo de registro e login com JWT
- **CRUD de Usuários**: Criação, leitura e gerenciamento de perfis
- **Sistema de Postagens**: Criar, editar, visualizar e deletar posts
- **Validação de Dados**: Validação robusta de entrada com Joi
- **Segurança**: Hash de senhas com bcrypt e autenticação por token
- **API RESTful**: Arquitetura REST com métodos HTTP adequados

## **Documentação da API**

### **Endpoints**

| Método | Rota | Descrição | Autenticação |
|--------|------|-----------|--------------|
| `GET` | `/` | Rota principal - mensagem de boas-vindas | Não |
| `POST` | `/usuarios` | Criar novo usuário | Não |
| `POST` | `/login` | Autenticar usuário e gerar token | Não |
| `GET` | `/usuarios` | Listar todos os usuários | Não |
| `GET` | `/posts` | Listar todas as postagens | Não |
| `POST` | `/posts` | Criar nova postagem | Sim |
| `PUT` | `/posts/:id` | Atualizar postagem existente | Sim |
| `DELETE` | `/posts/:id` | Deletar postagem | Sim |

### **Exemplos de Requisição e Resposta**

#### **Criar Usuário**
```bash
POST /usuarios
```

**Request Body:**
```json
{
  "nome": "João Silva",
  "email": "joao@exemplo.com",
  "senha": "123456"
}
```

**Response (201):**
```json
{
  "mensagem": "Usuário criado com sucesso",
  "usuario": {
    "id": 1,
    "nome": "João Silva",
    "email": "joao@exemplo.com",
    "created_at": "2024-01-01T00:00:00.000Z"
  }
}
```

#### **Login**
```bash
POST /login
```

**Request Body:**
```json
{
  "email": "joao@exemplo.com",
  "senha": "123456"
}
```

**Response (200):**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### **Criar Postagem**
```bash
POST /posts
Authorization: Bearer <token_jwt>
```

**Request Body:**
```json
{
  "titulo": "Meu primeiro post",
  "conteudo": "Olá mundo! Este é meu primeiro post na API Orkut."
}
```

**Response (201):**
```json
{
  "mensagem": "Post criado com sucesso",
  "post": {
    "id": 1,
    "titulo": "Meu primeiro post",
    "conteudo": "Olá mundo! Este é meu primeiro post na API Orkut.",
    "usuario_id": 1,
    "criado_em": "2024-01-01T00:00:00.000Z"
  }
}
```

#### **Listar Postagens**
```bash
GET /posts
```

**Response (200):**
```json
[
  {
    "id": 1,
    "nome": "João Silva",
    "titulo": "Meu primeiro post",
    "conteudo": "Olá mundo! Este é meu primeiro post na API Orkut.",
    "criado_em": "2024-01-01T00:00:00.000Z",
    "post_id": 1
  }
]
```

## **Como Executar o Projeto Localmente**

### **Pré-requisitos**
- Node.js (versão 18 ou superior)
- PostgreSQL
- Git

### **Passos**

1. **Clone o repositório:**
```bash
git clone https://github.com/pedrouvadev/api-orkut.git
cd api-orkut
```

2. **Instale as dependências:**
```bash
npm install
```

3. **Configure as variáveis de ambiente:**
```bash
cp .env.example .env
```

Edite o arquivo `.env` com suas configurações:
```env
PORT=3000
DATABASE_URL=postgresql://usuario:senha@localhost:5432/nome_do_banco
JWT_SECRET=sua_chave_secreta_aqui
```

4. **Execute o projeto:**
```bash
# Modo desenvolvimento
npm run dev

# Modo produção
npm start
```

5. **Acesse a API:**
- Local: `http://localhost:3000`
- Produção: `https://api-orkut-qe4l.onrender.com`

## **Deploy**

A API está hospedada na plataforma **Render** e disponível para acesso através da URL:

**https://api-orkut-qe4l.onrender.com**

## **Autor**

**Pedro Henrique Uva de Vasconcelos**

- **GitHub:** [pedrouvadev](https://github.com/pedrouvadev)
- **Email:** pedrouvadev@gmail.com

---

**Desenvolvido com Node.js, Express e PostgreSQL** | **API RESTful completa para rede social**
