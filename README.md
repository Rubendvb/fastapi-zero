# FastAPI Zero

Uma API REST simples construída com FastAPI para gerenciamento de usuários.

## 📋 Descrição

Este projeto é uma implementação básica de uma API REST usando FastAPI que permite:

- Criar usuários
- Listar todos os usuários
- Atualizar usuários existentes
- Validação de dados com Pydantic
- Testes automatizados com pytest

## 🚀 Tecnologias

- **FastAPI** - Framework web moderno para APIs
- **Pydantic** - Validação de dados e serialização
- **Poetry** - Gerenciamento de dependências
- **pytest** - Framework de testes
- **Ruff** - Linter e formatação de código

## 📦 Instalação

### Pré-requisitos

- Python 3.12 ou superior
- Poetry

### Passos para instalação

1. Clone o repositório:

```bash
git clone <url-do-repositorio>
cd fastapi_zero
```

2. Instale as dependências:

```bash
poetry install
```

3. Ative o ambiente virtual:

```bash
poetry shell
```

## 🏃‍♂️ Como executar

### Desenvolvimento

Para executar o servidor de desenvolvimento:

```bash
poetry run task run
```

Ou diretamente:

```bash
fastapi dev fastapi_zero/app.py
```

O servidor estará disponível em: `http://localhost:8000`

### Documentação da API

Após iniciar o servidor, você pode acessar:

- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

## 📚 Endpoints da API

### GET `/`

Retorna uma mensagem de boas-vindas.

**Resposta:**

```json
{
  "message": "Olá mundo!"
}
```

### POST `/users/`

Cria um novo usuário.

**Corpo da requisição:**

```json
{
  "username": "alice",
  "email": "alice@example.com",
  "password": "secret"
}
```

**Resposta:**

```json
{
  "id": 1,
  "username": "alice",
  "email": "alice@example.com"
}
```

### GET `/users/`

Lista todos os usuários cadastrados.

**Resposta:**

```json
{
  "users": [
    {
      "id": 1,
      "username": "alice",
      "email": "alice@example.com"
    }
  ]
}
```

### PUT `/users/{user_id}`

Atualiza um usuário existente.

**Corpo da requisição:**

```json
{
  "username": "bob",
  "email": "bob@example.com",
  "password": "secret123"
}
```

**Resposta:**

```json
{
  "id": 1,
  "username": "bob",
  "email": "bob@example.com"
}
```

## 🧪 Testes

### Executar todos os testes

```bash
poetry run task test
```

### Executar apenas os testes

```bash
pytest -s -x --cov=fastapi_zero -vv
```

### Gerar relatório de cobertura

```bash
coverage html
```

## 🔧 Comandos disponíveis

O projeto utiliza `taskipy` para gerenciar comandos. Aqui estão os comandos disponíveis:

- `poetry run task lint` - Executa o linter (Ruff)
- `poetry run task pre_format` - Corrige problemas de linting automaticamente
- `poetry run task format` - Formata o código
- `poetry run task run` - Executa o servidor de desenvolvimento
- `poetry run task pre_test` - Executa o linter antes dos testes
- `poetry run task test` - Executa os testes com cobertura
- `poetry run task post_test` - Gera relatório HTML de cobertura

## 📁 Estrutura do projeto

```
fastapi_zero/
├── fastapi_zero/
│   ├── __init__.py
│   ├── app.py          # Aplicação principal
│   └── schemas.py      # Modelos Pydantic
├── tests/
│   ├── __init__.py
│   ├── conftest.py     # Configuração dos testes
│   └── test_app.py     # Testes da aplicação
├── pyproject.toml      # Configuração do Poetry
└── README.md
```

## 👨‍💻 Desenvolvimento

### Adicionando novas dependências

```bash
poetry add nome-do-pacote
```

### Adicionando dependências de desenvolvimento

```bash
poetry add --group dev nome-do-pacote
```

### Verificando qualidade do código

```bash
poetry run task lint
poetry run task format
```

## 📝 Licença

Este projeto está sob a licença MIT.

## 👤 Autor

**Rubendvb** - []()
