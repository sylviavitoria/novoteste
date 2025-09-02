# Sistema de Gerenciamento Acadêmico - Automação com Cypress
[![Cypress](https://img.shields.io/badge/Cypress-13.7.0-04C38E?style=flat&logo=cypress&logoColor=white)](https://www.cypress.io/)
[![Node.js](https://img.shields.io/badge/Node.js-20-43853d?style=flat&logo=node.js&logoColor=white)](https://nodejs.org/)
[![NPM](https://img.shields.io/badge/NPM-10-CB3837?style=flat&logo=npm&logoColor=white)](https://www.npmjs.com/)

Este projeto contém testes automatizados usando Cypress para um sistema de gerenciamento de faculdade. A automação realiza testes end-to-end para verificar o funcionamento correto das principais funcionalidades do sistema.

## 📌 Cenários de Teste

### 🔑 Login

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [SF] Login de usuário (admin) | Verifica se é possível fazer login com credenciais válidas | Com sucesso |
| [SF] Login com usuário inválido | Verifica se não é possível logar com um usuário inexistente | Com falha |
| [SF] Login com senha incorreta | Verifica se não é possível logar com senha incorreta | Com falha |
| [SF] Login com campos em branco | Verifica se não é possível logar sem preencher os campos | Com falha |
| [SF] Login com usuário em branco | Verifica se o campo usuário é obrigatório | Com falha |
| [SF] Login com senha em branco | Verifica se o campo senha é obrigatório | Com falha |

---

### 👨‍🎓 Aluno

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [SF] Cadastro de novo aluno com dados válidos | Verifica se é possível cadastrar um aluno corretamente | Com sucesso |
| [SF] Cadastro de aluno sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [SF] Cadastro de aluno sem email | Verifica se o campo email é obrigatório | Com falha |
| [SF] Cadastro de aluno sem senha | Verifica se o campo senha é obrigatório | Com falha |

---

### 👨‍🏫 Professor

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [SF] Cadastro de novo professor com dados válidos | Verifica se é possível cadastrar um professor corretamente | Com sucesso |
| [SF] Cadastro de professor sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [SF] Cadastro de professor sem email | Verifica se o campo email é obrigatório | Com falha |
| [SF] Cadastro de professor sem senha | Verifica se o campo senha é obrigatório | Com falha |
| [SF] Cadastro de professor com email já existente | Verifica se não é possível cadastrar professor com email duplicado | Com falha |

---

### 📚 Disciplina

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [SF] Cadastro de nova disciplina com código único | Verifica se é possível cadastrar uma disciplina corretamente | Com sucesso |
| [SF] Cadastro de disciplina sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [SF] Cadastro de disciplina sem código | Verifica se o campo código é obrigatório | Com falha |
| [SF] Cadastro de disciplina com código já existente | Verifica se não é possível cadastrar disciplina com código duplicado | Com falha |

---

### 📝 Matrícula

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [SF] Matrícula com dados válidos | Verifica se é possível matricular um aluno em disciplina corretamente | Com sucesso |
| [SF] Matrícula sem seleção de aluno | Verifica se o campo aluno é obrigatório | Com falha |
| [SF] Matrícula sem seleção de disciplina | Verifica se o campo disciplina é obrigatório | Com falha |
| [SF] Matrícula duplicada em disciplina | Verifica se não é possível matricular o mesmo aluno duas vezes na mesma disciplina | Com falha |

---

## 📁 Estrutura do Projeto

```
cypress/
│
├── e2e/
│   └── tests/
│       ├── Aluno.cy.js       # Testes de cadastro de alunos
│       ├── Disciplina.cy.js  # Testes de cadastro de disciplinas
│       ├── Login.cy.js       # Testes de login
│       ├── Matricula.cy.js   # Testes de matrícula de alunos em disciplinas
│       └── Professor.cy.js   # Testes de cadastro de professores
│
│
└── support/
    ├── commands.js           # Comandos personalizados do Cypress
    └── e2e.js                # Configurações globais para testes e2e
```
---

# 🌬️ Como Executar

### 🛠️ Pré-requisitos

- [Node.js](https://nodejs.org/) (versão recomendada: 14 ou superior)
- NPM (geralmente instalado com o Node.js)
- Configuração do ambiente completo:  
  - [faculdade-backend](https://github.com/sylviavitoria/faculdade-backend)  
  - [faculdade-frontend](https://github.com/sylviavitoria/faculdade-frontend)  

> ⚠️ É necessário ter **BACKEND** e **FRONTEND** rodando para execução correta dos testes end-to-end.

## 💻 Passo a passo para Execução

1. Clone o repositório:
```bash
git clone https://github.com/sylviavitoria/CypressFaculdade.git
```
> ⚠️ Para a funcionalidade completa, é necessário configurar também o **BACKEND** e o **FRONTEND**.  
> Siga as instruções dos repositórios: [faculdade-backend](https://github.com/sylviavitoria/faculdade-backend) e [faculdade-frontend](https://github.com/sylviavitoria/faculdade-frontend)

2. Suba o backend e o frontend seguindo os comandos de execução nos respectivos repositórios.

3. Após subir backend e o frontend navegue até o diretório do projeto:
```bash
cd CypressFaculdade
```

4. Instale as dependências:
```bash
npm install
```

5. Você pode executar os testes da seguinte forma:

   - **Interface do Cypress**  
     
     Para abrir a interface do Cypress e executar os testes manualmente:  
```bash
npx cypress open
```

   - **Linha de Comando**  
     
     Para executar todos os testes via linha de comando:
```bash
npx cypress run
```





