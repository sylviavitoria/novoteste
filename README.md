# Automação de Testes - Sistema de Faculdade
[![RestAssured](https://img.shields.io/badge/RestAssured-4.5.0-00BFFF?style=flat&logo=java&logoColor=white)](https://rest-assured.io/)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5.4-6DB33F?style=flat&logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)

Este projeto contém testes automatizados para um sistema de gestão de faculdade, utilizando RestAssured para testar a API do sistema.

## Tecnologias Utilizadas

- Java
- JUnit 5
- RestAssured
- Maven

## Estrutura do Projeto

O projeto está organizado em pacotes de testes separados por domínio:

- `AuthApiTest`: Testes relacionados à autenticação e autorização
- `AlunoApiTest`: Testes relacionados aos endpoints de alunos
- `ProfessorApiTest`: Testes relacionados aos endpoints de professores
- `DisciplinaApiTest`: Testes relacionados aos endpoints de disciplinas
- `MatriculaApiTest`: Testes relacionados aos endpoints de matrículas

## Levantamento de Testes

### Autenticação e Permissões

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [API] Login de usuário (admin, professor, aluno) | Verifica se é possível fazer login com diferentes perfis | Com sucesso |
| [API] Login com senha incorreta | Verifica se a autenticação falha com senha incorreta | Com falha |
| [API] Acesso a endpoint protegido sem token | Verifica se não é possível acessar recursos protegidos sem token | Com falha |
| [API] Acesso a endpoint protegido com token inválido ou sem permissão | Verifica se não é possível acessar recursos protegidos com token inválido | Com falha |

### Aluno

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [API] Cadastro de novo aluno com dados válidos | Verifica se é possível cadastrar um aluno com todos os dados corretos | Com sucesso |
| [API] Cadastro de novo aluno com email ou matrícula já existente | Verifica se não é possível cadastrar aluno com dados duplicados | Com falha |
| [API] Listagem paginada de alunos | Verifica se é possível listar alunos com paginação | Com sucesso |
| [API] Aluno tentando criar disciplina | Verifica se alunos não podem criar disciplinas | Com falha |
| [API] Aluno tentando criar professor | Verifica se alunos não podem criar professores | Com falha |
| [API] Aluno tentando criar outro aluno | Verifica se alunos não podem criar outros alunos | Com falha |
| [API] Cadastro de aluno sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [API] Cadastro de aluno sem email | Verifica se o campo email é obrigatório | Com falha |
| [API] Cadastro de aluno sem senha | Verifica se o campo senha é obrigatório | Com falha |

### Professor

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [API] Cadastro de novo professor com dados válidos | Verifica se é possível cadastrar um professor com todos os dados corretos | Com sucesso |
| [API] Cadastro de novo professor com email já existente | Verifica se não é possível cadastrar professor com email duplicado | Com falha |
| [API] Listagem paginada de professores | Verifica se é possível listar professores com paginação | Com sucesso |
| [API] Professor tentando criar disciplina | Verifica se professores não podem criar disciplinas | Com falha |
| [API] Professor tentando criar aluno | Verifica se professores não podem criar alunos | Com falha |
| [API] Professor tentando criar outro professor | Verifica se professores não podem criar outros professores | Com falha |
| [API] Cadastro de professor sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [API] Cadastro de professor sem email | Verifica se o campo email é obrigatório | Com falha |
| [API] Cadastro de professor sem senha | Verifica se o campo senha é obrigatório | Com falha |

### Disciplina

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [API] Cadastro de nova disciplina com código único | Verifica se é possível cadastrar uma disciplina com dados válidos | Com sucesso |
| [API] Cadastro de disciplina com código já existente | Verifica se não é possível cadastrar disciplina com código duplicado | Com falha |
| [API] Listagem de disciplinas (admin, professor e aluno) | Verifica se todos os perfis podem listar disciplinas | Com sucesso |
| [API] Cadastro de disciplina sem nome | Verifica se o campo nome é obrigatório | Com falha |
| [API] Cadastro de disciplina sem código | Verifica se o campo código é obrigatório | Com falha |
| [API] Cadastro de disciplina sem professorId | Verifica se o campo professorId é obrigatório | Com falha |
| [API] Professor tentando criar disciplina | Verifica se professores não podem criar disciplinas | Com falha |
| [API] Aluno tentando criar disciplina | Verifica se alunos não podem criar disciplinas | Com falha |

### Matrícula

| Teste | Descrição | Resultado |
|-------|-----------|-----------|
| [API] Matrícula de aluno em disciplina (válida) | Verifica se é possível matricular aluno em disciplina | Com sucesso |
| [API] Matrícula duplicada em disciplina | Verifica se não é possível cadastrar matrícula duplicada | Com falha |
| [API] Professor tentando cadastrar matrícula | Verifica se professores não podem cadastrar matrículas | Com falha |
| [API] Cadastro de matrícula sem alunoId | Verifica se o campo alunoId é obrigatório | Com falha |
| [API] Cadastro de matrícula sem disciplinaId | Verifica se o campo disciplinaId é obrigatório | Com falha |

## Como Executar os Testes

Para executar os testes, certifique-se de que a aplicação esteja em execução na porta 8080 e execute:

```bash
mvn test
```

Para executar uma classe de teste específica:

```bash
mvn -Dtest=AlunoApiTest test
```

## Requisitos

- Java 11 ou superior
- Maven 3.6 ou superior
- API do sistema de faculdade em execução na porta 8080
