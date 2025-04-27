# 🏥 API de Sistema de Agenda de Consultas - Spring Boot

Este projeto é uma API REST em Java utilizando Spring Boot para a gestão de Pacientes, Profissionais da Saúde e Consultas.

A API permite:
- Cadastrar, atualizar, consultar e remover pacientes
- Cadastrar, atualizar, consultar e remover profissionais
- (Opcional) Cadastrar, atualizar, consultar e remover consultas médicas

Toda a documentação da API está disponível via Swagger.

---

# ✅ Pré-requisitos
- Java 17 ou superior
- Maven 3.6+ instalado
- IDE de sua preferência (IntelliJ IDEA, Eclipse, VSCode)

---

# ⚙️ Instalação e Configuração

## 1. Clonar o Repositório
Clone o repositório para a sua máquina local:

```bash
git clone <URL-do-repositório>
```

## 2. Build do Projeto
Dentro do diretório do projeto, execute:

```bash
mvn clean package
```

Isso vai gerar a pasta `/target` com os artefatos compilados.

## 3. Rodar o Projeto
Execute a aplicação usando:

```bash
mvn spring-boot:run
```

O servidor será iniciado na porta padrão **8080**.

---

# 📚 Configuração do Swagger

Para ativar o Swagger UI, adicione no seu `application.properties`:

```properties
springdoc.swagger-ui.path=/
springdoc.swagger-ui.disable-swagger-default-url=true
```

Com isso, você poderá acessar a documentação interativa via navegador:

- [http://localhost:8080](http://localhost:8080)

```properties
- http://localhost:8080/swagger-ui.html
```

---

# 🛠 Endpoints da API

## 🡩 Pacientes

- `POST /pacientes` – Cadastrar paciente
- `GET /pacientes` – Listar todos os pacientes
- `GET /pacientes/{id}` – Buscar paciente pelo ID
- `PUT /pacientes/{id}` – Atualizar paciente pelo ID
- `DELETE /pacientes/{id}` – Deletar paciente pelo ID

## 🡩‍⚕️ Profissionais

- `POST /profissionais` – Cadastrar profissional
- `GET /profissionais` – Listar todos os profissionais
- `GET /profissionais/{id}` – Buscar profissional pelo ID
- `PUT /profissionais/{id}` – Atualizar profissional pelo ID
- `DELETE /profissionais/{id}` – Deletar profissional pelo ID

## 🗕️ Consultas (Opcional)

- `POST /consultas` – Agendar nova consulta
- `GET /consultas` – Listar todas as consultas
- `GET /consultas/{id}` – Buscar consulta pelo ID
- `PUT /consultas/{id}` – Atualizar dados da consulta
- `DELETE /consultas/{id}` – Cancelar consulta

**Observação:**  
O valor da consulta é calculado automaticamente conforme o valor por hora do profissional × quantidade de horas da consulta.

---

# 🧹 Estrutura do Projeto

```
src/main/java/br/com/fiap/checkpoint1/
│
├── controller/       # Controladores da API (REST)
├── dto/              # Data Transfer Objects (DTOs) de entrada e saída
├── model/            # Modelos (Entidades) de Paciente, Profissional e Consulta
├── service/          # Serviços de negócios (regras e persistência em memória)
└── Checkpoint1Application.java  # Classe principal (Spring Boot Starter)
```

---

# 🧪 Executar os Testes

Para rodar os testes automatizados (caso implementados):

```bash
mvn test
```

---

# 🔗 Referências

- [Documentação do SpringDoc OpenAPI](https://springdoc.org/)
- [Java 17 Download](https://www.oracle.com/java/technologies/downloads/)
- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Swagger OpenAPI 3.0](https://swagger.io/specification/)

---

# ✨ Observações Finais
- Este projeto é um *checkpoint acadêmico* com persistência **em memória** (não usa banco de dados ainda).
- Foi desenvolvido com base no **MER** fornecido para agendamento de consultas médicas.
- Ideal para aplicações simples de aprendizado com **Java + Spring Boot**.

