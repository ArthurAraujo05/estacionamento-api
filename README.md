# Demo Park API

API RESTful desenvolvida com **Spring Boot** para gestão de estacionamentos, incluindo controle de clientes, vagas e autenticação segura via **JWT**.

## 🚀 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.2.1**
- **Spring Data JPA**
- **Spring Security (JWT)**
- **MySQL**
- **Lombok**
- **ModelMapper**
- **Swagger/OpenAPI**
- **JasperReports**

## 📂 Estrutura do Projeto

```
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.mballem.demoparkapi
│   │   │       ├── config          # Configurações (segurança, JPA, Swagger)
│   │   │       ├── entity          # Entidades JPA
│   │   │       ├── exception       # Tratamento de exceções
│   │   │       ├── jwt             # Configurações de autenticação JWT
│   │   │       ├── repository      # Repositórios JPA
│   │   │       ├── service         # Camada de serviços
│   │   │       └── web             # Controllers e DTOs
│   │   └── resources
│   │       ├── application.properties  # Configurações da aplicação
│   │       ├── messages.properties     # Mensagens i18n
│   │       └── reports                 # Relatórios Jasper
│   └── test                           # Testes automatizados
└── pom.xml                             # Dependências Maven
```

## ⚙️ Configuração do Ambiente

### 1. **Pré-requisitos**

- **Java 17**
- **Maven**
- **MySQL**

### 2. **Configuração do Banco de Dados**

Crie o banco de dados:

```sql
CREATE DATABASE demo_park;
```

Altere `src/main/resources/application.properties` se necessário:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/demo_park
spring.datasource.username=root
spring.datasource.password=root
```

### 3. **Executando o Projeto**

```bash
# Instalar dependências
./mvnw clean install

# Rodar a aplicação
./mvnw spring-boot:run
```

A aplicação estará disponível em: `http://localhost:8080`

### 4. **Documentação da API**

- **Swagger UI:** [http://localhost:8080/docs-park.html](http://localhost:8080/docs-park.html)

## 🔑 Autenticação (JWT)

Para acessar endpoints protegidos:

1. **Login:**

   ```http
   POST /api/v1/auth/login
   {
       "username": "admin",
       "password": "123456"
   }
   ```

2. **Resposta:**

   ```json
   {
       "token": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
   }
   ```

3. **Usar o Token:**

   ```http
   Authorization: Bearer <seu_token_aqui>
   ```

## 📝 Endpoints Principais

- **POST** `/api/v1/auth/login` → Autenticação
- **GET** `/api/v1/clientes` → Listar clientes
- **POST** `/api/v1/vagas` → Criar vaga
- **POST** `/api/v1/estacionamento/checkin` → Check-in de veículo

## ✅ Testes Automatizados

Execute os testes com:

```bash
./mvnw test
```

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Sinta-se livre para usar e modificar!
