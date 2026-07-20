# NEXORA AI

# Backend Bootstrap Guide

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

This document defines how to initialize the Spring Boot backend and prepare the foundation for all future modules.

At the end of this phase, the backend should:

- Compile successfully
- Connect to PostgreSQL
- Run without errors
- Expose a health endpoint
- Be ready for Authentication development

---

# 2. Technology Stack

Java 21

Spring Boot 3.x

Spring Security

Spring Data JPA

PostgreSQL

Flyway

Maven

Lombok

Validation

---

# 3. Spring Initializr Configuration

Project

```
Maven
```

Language

```
Java
```

Java Version

```
21
```

Group

```
com.nexora
```

Artifact

```
backend
```

Name

```
nexora-backend
```

Package

```
com.nexora
```

Packaging

```
Jar
```

---

# 4. Required Dependencies

Spring Web

Spring Security

Spring Data JPA

Validation

PostgreSQL Driver

Flyway

Lombok

Spring Boot DevTools

Actuator

---

# 5. Initial Package Structure

```
com.nexora

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

# 6. Configuration Files

Create:

```
application.yml

application-dev.yml

application-test.yml

application-prod.yml
```

Purpose:

application.yml

Common configuration

application-dev.yml

Local development

application-test.yml

Testing

application-prod.yml

Production

---

# 7. Resource Structure

```
src/main/resources/

db/

migration/

static/

templates/
```

---

# 8. First Flyway Migration

Create

```
V1__initial_schema.sql
```

Initially keep it empty.

Future migrations:

```
V2__users.sql

V3__students.sql

V4__companies.sql

V5__jobs.sql

V6__resume.sql
```

---

# 9. Common Package

Create

```
common/

constants/

enums/

response/

request/
```

Purpose

Store reusable application classes.

---

# 10. Exception Package

Create

```
exception/

GlobalExceptionHandler

ResourceNotFoundException

BadRequestException

UnauthorizedException

ConflictException
```

---

# 11. Security Package

Create empty classes only.

```
SecurityConfig

JwtFilter

JwtService

AuthenticationEntryPoint

UserPrincipal
```

Implementation comes later.

---

# 12. Configuration Package

Create

```
SwaggerConfig

CorsConfig

JacksonConfig

ModelMapperConfig
```

Only empty configuration classes for now.

---

# 13. Health Module

Purpose

Verify application status.

Create

```
HealthController
```

Endpoint

```
GET /api/v1/health
```

Expected Response

```
{
    "status":"UP",
    "service":"NEXORA Backend",
    "version":"1.0.0"
}
```

---

# 14. Logging

Use SLF4J.

Rules

Never use

```
System.out.println()
```

Instead

```
Logger

LoggerFactory
```

---

# 15. Code Standards

Use:

Constructor Injection

DTO Pattern

ResponseEntity

Lombok

@NoArgsConstructor

@AllArgsConstructor

@RequiredArgsConstructor

@Builder

---

# 16. Naming Standards

Controller

```
StudentController
```

Service

```
StudentService
```

Implementation

```
StudentServiceImpl
```

Repository

```
StudentRepository
```

Entity

```
Student
```

DTO

```
StudentRequest

StudentResponse
```

---

# 17. Initial Git Commit

Commit message

```
feat: initialize Spring Boot backend foundation
```

---

# 18. Definition of Done

Backend project created

Dependencies added

Folder structure created

Configuration files created

Health endpoint working

Application starts successfully

Database configuration prepared

Flyway configured

---

# 19. Deliverables

Project compiles

No warnings

No failing tests

Ready for Authentication module

---

# 20. Next Phase

After backend bootstrap, begin implementing Authentication.

No business logic should be added before the security foundation is complete.
