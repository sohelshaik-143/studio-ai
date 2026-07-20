# NEXORA AI

# Backend Project Setup

Version: 1.0  
Status: Ready for Implementation

---

# 1. Objective

Initialize the NEXORA AI backend using Java 21 and Spring Boot 3.x.

After completion:

- Backend runs successfully
- PostgreSQL connection works
- Project structure is ready
- Dependencies are configured
- Initial commit is created

---

# 2. Technology Stack

```
Java 21

Spring Boot 3.x

Maven

PostgreSQL

Spring Data JPA

Spring Security

Flyway

Lombok
```

---

# 3. Project Creation

Spring Initializr Configuration:

```
Project:
Maven

Language:
Java

Java Version:
21

Group:
com.nexora

Artifact:
backend

Name:
nexora-backend

Packaging:
Jar
```

---

# 4. Dependencies

Add:

```
Spring Web

Spring Security

Spring Data JPA

Validation

PostgreSQL Driver

Flyway Migration

Lombok

Spring Boot DevTools

Spring Boot Actuator
```

---

# 5. Backend Structure

```
src/main/java/com/nexora

├── auth
├── student
├── recruiter
├── company
├── resume
├── matching
├── dashboard
├── config
├── security
├── common
├── exception
├── util
└── NexoraApplication.java
```

---

# 6. Resource Configuration

Create:

```
src/main/resources

├── application.yml
├── application-dev.yml
├── application-test.yml
├── application-prod.yml
└── db/migration
```

---

# 7. Database Configuration

Development database:

```
Database:
nexora_dev

Username:
postgres

Port:
5432
```

Configuration:

```
spring:
  datasource:
    url:
    username:
    password:
```

---

# 8. Initial Verification

Run:

```
mvn clean install
```

Start application:

```
mvn spring-boot:run
```

Verify:

```
Application starts successfully
```

---

# 9. Initial Git Commit

Commit:

```
feat: initialize nexora backend project
```

---

# 10. Definition of Done

Completed:

- Spring Boot project created
- Dependencies installed
- Package structure created
- Database configuration prepared
- Application starts successfully
- Initial commit pushed

---

# Next Step

02_DATABASE_MIGRATION_SETUP.md
