# NEXORA AI

# Coding Standards

**Version:** 1.0
**Status:** Approved

---

# Document Information

| Property | Value |
|----------|--------|
| Document Name | Coding Standards |
| Project | NEXORA AI |
| Version | 1.0 |
| Owner | NEXORA Development Team |
| Status | Approved |
| Last Updated | July 2026 |

---

# Revision History

| Version | Date | Author | Description |
|----------|------|---------|-------------|
| 1.0 | July 2026 | NEXORA Development Team | Initial Coding Standards |

---

# Table of Contents

1. Purpose
2. Coding Philosophy
3. Java Standards
4. Spring Boot Standards
5. Package Structure
6. Naming Conventions
7. Controller Standards
8. Service Standards
9. Repository Standards
10. Entity Standards
11. DTO Standards
12. Exception Handling
13. Logging
14. Validation
15. Code Quality
16. Performance
17. Security
18. Git Commit Rules
19. Review Checklist
20. Definition of Done

---

# 1. Purpose

This document defines the official coding standards for the NEXORA AI project.

Following these standards ensures that every contributor writes consistent, maintainable, secure, and production-ready code.

---

# 2. Coding Philosophy

Every line of code should be:

- Readable
- Testable
- Maintainable
- Secure
- Reusable
- Modular
- Documented
- Production Ready

The primary principle is:

> **Write code for humans first, computers second.**

---

# 3. Java Standards

Language Version

```
Java 21 LTS
```

Follow:

- Object-Oriented Programming
- SOLID Principles
- Clean Code
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple)
- YAGNI (You Aren't Gonna Need It)

Avoid:

- God Classes
- Long Methods
- Duplicate Logic
- Deep Nesting
- Magic Numbers

---

# 4. Spring Boot Standards

Framework Version

```
Spring Boot 3.x
```

Preferred Features

- Constructor Injection
- Spring Data JPA
- Spring Security
- Validation
- Flyway
- Actuator
- SLF4J Logging

Avoid

- Field Injection
- Circular Dependencies
- Business Logic in Controllers

---

# 5. Package Structure

```text
com.nexora

├── auth
├── student
├── recruiter
├── college
├── company
├── resume
├── matching
├── dashboard
├── notification
├── config
├── security
├── common
├── exception
└── util
```

Each module should be self-contained.

---

# 6. Naming Conventions

Controllers

```java
StudentController
RecruiterController
```

Services

```java
StudentService
```

Implementations

```java
StudentServiceImpl
```

Repositories

```java
StudentRepository
```

Entities

```java
Student
```

DTOs

```java
StudentRequest
StudentResponse
```

Enums

```java
UserRole
ApplicationStatus
```

---

# 7. Controller Standards

Controllers should:

- Expose REST endpoints
- Validate requests
- Return ResponseEntity
- Never contain business logic
- Delegate work to services

Example

```java
@PostMapping
public ResponseEntity<StudentResponse> createStudent(...)
```

---

# 8. Service Standards

Services should:

- Contain business logic
- Be transactional when required
- Call repositories
- Never return entities directly to controllers

---

# 9. Repository Standards

Repositories should:

- Extend JpaRepository
- Use Specifications when needed
- Avoid native SQL unless necessary
- Return Optional where appropriate

---

# 10. Entity Standards

Each entity should include:

```java
id

createdAt

updatedAt
```

Prefer:

- UUID or BIGSERIAL identifiers
- JPA relationships
- Lazy loading where appropriate

Avoid exposing entities directly through APIs.

---

# 11. DTO Standards

Separate DTOs for:

```text
Request

Response
```

Example

```text
StudentRequest

StudentResponse
```

Never reuse entities as API payloads.

---

# 12. Exception Handling

Use centralized exception handling.

Create custom exceptions such as:

```text
ResourceNotFoundException

BadRequestException

ConflictException

UnauthorizedException
```

All exceptions should be handled by a global exception handler.

---

# 13. Logging

Use

```text
SLF4J
```

Never use

```java
System.out.println()
```

Log:

- Authentication events
- API requests
- Errors
- Warnings
- Important business events

Do not log passwords, tokens, or sensitive personal data.

---

# 14. Validation

Use Jakarta Validation.

Examples

```java
@NotBlank

@Email

@Size

@Pattern
```

Validate all incoming request DTOs before processing.

---

# 15. Code Quality

Maintain:

- Small methods
- Meaningful names
- Single Responsibility
- Low coupling
- High cohesion

Target high unit test coverage for service-layer logic.

---

# 16. Performance

Use:

- Pagination
- Lazy loading
- Database indexes
- Batch processing where appropriate

Avoid:

- N+1 queries
- Unnecessary object creation
- Repeated database calls

---

# 17. Security

Always:

- Encrypt passwords with BCrypt
- Validate JWTs
- Sanitize input
- Use HTTPS in production
- Enforce role-based access

Never:

- Store secrets in source code
- Return stack traces to clients

---

# 18. Git Commit Rules

Follow Conventional Commits.

Examples

```text
feat(auth): implement JWT authentication

fix(student): resolve profile update issue

docs(api): update authentication endpoints

refactor(resume): improve parsing service

test(auth): add login integration tests
```

---

# 19. Review Checklist

Before merging code:

- Code compiles
- Tests pass
- No warnings
- Formatting applied
- Logging added where needed
- Validation implemented
- Security reviewed
- Documentation updated

---

# 20. Definition of Done

Code is considered complete when:

- Standards are followed
- Tests pass
- Documentation is updated
- Code review is approved
- Feature satisfies requirements
- No critical security issues remain

---

# References

- PROJECT_VISION.md
- SYSTEM_ARCHITECTURE.md
- DOCUMENTATION_STANDARD.md

---

# Next Document

Continue with:

**05_DATABASE_STANDARD.md**

This document defines database naming conventions, schema design rules, migration strategy, indexing, relationships, and optimization practices for NEXORA AI.
