# VollMed API 🏥

API para cadastro de médicos, pacientes e consultas; documentação Swagger com exemplos.

<p align="left">
  <img src="https://img.shields.io/badge/Java-21-f89820?logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring_Boot-3-6DB33F?logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/Build-GitHub_Actions-000000?logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/Docs-Swagger-85EA2D?logo=swagger&logoColor=white" />
  <img src="https://img.shields.io/badge/DB-MySQL-4479A1?logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Licence-MIT-pink" />
</p>

## ✨ Highlights
- Autenticação **JWT** com Spring Security  
- **JPA/Hibernate** + **Flyway** para migrações  
- **Bean Validation** + **Exception Handler** fofo (mensagens amigáveis)  
- **Swagger/OpenAPI** com exemplos prontos  

## 🚀 Quick start
```bash
# 1) Rodar banco local (Docker)
docker run -d --name mysql -e MYSQL_DATABASE=app -e MYSQL_ROOT_PASSWORD=secret -p 3306:3306 mysql:8

# 2) Rodar a API
./mvnw spring-boot:run

# 3) Acessar docs
# -> http://localhost:8080/swagger-ui/index.html
```

## ⚙️ Config
Crie um arquivo `src/main/resources/application-local.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/app?createDatabaseIfNotExist=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=secret
spring.jpa.hibernate.ddl-auto=validate
spring.flyway.enabled=true
api.security.jwt.secret=change-me
```

## 🧪 Testes
```bash
./mvnw -q test
```

## 🧱 Estrutura
```
src/main/java
└── com.jess.vollmed/
    ├── controller
    ├── dto
    ├── entity
    ├── repository
    ├── service
    └── security
```
> Pacote base sugerido: **com.jess.vollmed**

## 🔗 Endpoints (exemplos)
- `POST /auth/login` → autentica e retorna JWT  
- `GET  /v1/resources?page=0&size=20` → paginação fofinha  
- `POST /v1/resources` → cria

## 🐳 Docker
```bash
./mvnw -DskipTests package
docker build -t vollmed-api:latest .
docker run -p 8080:8080 --env-file .env vollmed-api:latest
```

## 📝 Licença
MIT — use à vontade e me marque no LinkedIn 😊

---
<sub>feito com carinho por Jessica • 2025-08-28</sub>

[⬅️ Voltar ao README principal](README1.md)

**Você está em: VollMed API**  
[Ir para: Financial Transactions API](README-financial-transactions.md) |  
[Orders API](README-orders-api.md)  | 
[Tour Booking Microservices](README-tour-microservices.md)  | 
[Forum Hub API](README-forum-hub.md)

---