# Gerenciador de Produtos - CRUD Web

Sistema completo de gerenciamento de produtos com frontend e backend em JavaScript/Node.js. Implementa as operações CREATE, READ, UPDATE e DELETE (CRUD).

## 📋 Funcionalidades

- **Listar Produtos**: Visualize todos os produtos cadastrados
- **Filtros Avançados**: Pesquise por nome, descrição, tipo e status
- **Criar Produto**: Adicione novos produtos ao sistema
- **Editar Produto**: Modifique dados de produtos existentes
- **Deletar Produto**: Remova produtos com confirmação
- **Feedback Visual**: Mensagens de sucesso/erro após cada operação

## 🛠️ Requisitos

- [Bun](https://bun.sh) (versão 1.0 ou superior)
- Navegador moderno (Chrome, Firefox, Safari, Edge)

## 📦 Instalação

### 1. Clonar ou baixar o projeto

```bash
cd sua-pasta-do-projeto/code/11-05-2026
```

### 2. Instalar dependências

```bash
bun install
```

Este comando irá instalar todas as dependências necessárias:
- `express`: Framework web para Node.js
- `cors`: Middleware para CORS (Cross-Origin Resource Sharing)

## 🚀 Executando o Projeto

### Backend

Na pasta do projeto, execute:

```bash
bun run dev
```

O servidor iniciará em `http://localhost:3000` com hot-reload ativado.

Você deve ver a mensagem:
```
Server is running on port 3000
```

### Frontend

Abra o arquivo `frontend/index.html` no navegador:

- Duplo-clique em `frontend/index.html` ou
- Clique com botão direito → Abrir com → Seu navegador favorito

> **Dica**: Para melhor experiência, use um servidor local como Live Server (extensão do VS Code)

## 📱 Como Usar

### Criar Produto
1. Preencha o formulário "Cadastro / Edição de Produto"
2. Clique em "Salvar"
3. O produto aparecerá na tabela abaixo

### Editar Produto
1. Clique no botão "Editar" na linha do produto desejado
2. O formulário preencherá automaticamente
3. Modifique os dados
4. Clique em "Atualizar"

### Deletar Produto
1. Clique no botão "Excluir" na linha do produto
2. Confirme a exclusão
3. O produto será removido

### Filtrar Produtos
1. Preencha um ou mais filtros (Nome, Descrição, Tipo, Status)
2. Clique em "Filtrar"
3. A tabela mostrará apenas produtos que correspondem aos critérios

## 🏗️ Estrutura do Projeto

```
11-05-2026/
├── backend/
│   ├── server.js          # Servidor Express com rotas CRUD
│   ├── package.json       # Dependências do projeto
│   └── README.md          # Este arquivo
├── frontend/
│   ├── index.html         # Interface HTML
│   ├── main.js            # Lógica JavaScript do frontend
│   └── main.css           # Estilos CSS
└── README.md
```

## 📡 API REST

### GET `/produtos`
Lista todos os produtos com filtros opcionais.

**Parâmetros de Query**:
- `tipo`: filtra por tipo (notebook, projetor)
- `status`: filtra por status (disponivel, emprestado, manutencao)
- `busca`: filtra por nome
- `descricao`: filtra por descrição

**Exemplo**:
```
GET http://localhost:3000/produtos?tipo=notebook&status=disponivel
```

### GET `/produtos/:id`
Retorna um produto específico pelo ID.

**Exemplo**:
```
GET http://localhost:3000/produtos/1
```

### POST `/produtos`
Cria um novo produto.

**Body** (JSON):
```json
{
  "nome": "Notebook Dell",
  "tipo": "notebook",
  "status": "disponivel",
  "descricao": "Notebook para desenvolvimento"
}
```

### PUT `/produtos/:id`
Atualiza um produto existente.

**Body** (JSON):
```json
{
  "nome": "Notebook Atualizado",
  "status": "emprestado"
}
```

### DELETE `/produtos/:id`
Remove um produto.

**Exemplo**:
```
DELETE http://localhost:3000/produtos/1
```

## 🌐 Rotas Implementadas

O backend implementa as seguintes operações REST:

- **Listar** (`GET /produtos`): Retorna todos os produtos, com suporte a filtros por tipo, status, nome e descrição
- **Buscar** (`GET /produtos/:id`): Retorna um produto específico pelo ID
- **Criar** (`POST /produtos`): Cria um novo produto com ID gerado automaticamente
- **Atualizar** (`PUT /produtos/:id`): Modifica um produto existente
- **Deletar** (`DELETE /produtos/:id`): Remove um produto do sistema

## ✅ Validações

- **Nome**: Obrigatório
- **Tipo**: Obrigatório (valores válidos: `notebook`, `projetor`)
- **Status**: Aceita `disponivel`, `emprestado` ou `manutencao`
- **ID**: Gerado automaticamente pelo servidor

## 🐛 Solução de Problemas

### "Erro ao buscar produtos"
Certifique-se de que o servidor está rodando com `bun run dev`.

### "Erro de conexão com o servidor"
Verifique se o servidor está em `http://localhost:3000`.

### Porta 3000 em uso
Se a porta 3000 estiver ocupada, você pode alterar a porta no arquivo `backend/server.js`:
```javascript
const PORT = 3001; // Altere para outra porta disponível
```

## 📝 Notas

- Os dados são armazenados em memória e serão perdidos ao reiniciar o servidor
- Para persistência real, seria necessário implementar um banco de dados
- O projeto utiliza JavaScript vanilla (sem frameworks)

## 👨‍💻 Desenvolvido para

**DSW 2026/1 - UNEMAT**  
Andrew Gabrel Dariva Silva

---

**Última atualização**: Maio de 2026
