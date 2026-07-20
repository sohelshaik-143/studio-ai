# NEXORA AI

# API Standards

**Version:** 1.0
**Status:** Approved

---

# Document Information

| Property | Value |
|----------|--------|
| Document Name | API Standards |
| Project | NEXORA AI |
| Version | 1.0 |
| Owner | NEXORA Development Team |
| Status | Approved |
| Last Updated | July 2026 |

---

# Revision History

| Version | Date | Author | Description |
|----------|------|---------|-------------|
| 1.0 | July 2026 | NEXORA Development Team | Initial API Standards |

---

# Table of Contents

1. Purpose
2. API Design Principles
3. API Versioning
4. URL Standards
5. HTTP Methods
6. Request Standards
7. Response Standards
8. Error Response Format
9. Pagination
10. Filtering
11. Sorting
12. Authentication
13. HTTP Status Codes
14. Rate Limiting
15. Idempotency
16. API Documentation
17. Version Lifecycle
18. Review Checklist
19. Definition of Done

---

# 1. Purpose

This document defines the REST API standards for NEXORA AI.

Every backend endpoint must follow these conventions to ensure consistency, scalability, maintainability, and ease of integration.

---

# 2. API Design Principles

Every API should be:

- RESTful
- Predictable
- Consistent
- Secure
- Versioned
- Stateless
- Well documented

APIs should expose business resources instead of implementation details.

---

# 3. API Versioning

All APIs must be versioned.

Example

```
/api/v1/
```

Examples

```
/api/v1/auth/login

/api/v1/students

/api/v1/jobs

/api/v1/recruiters
```

Breaking changes require a new API version.

---

# 4. URL Standards

Use plural resource names.

Correct

```
/students

/jobs

/recruiters

/companies
```

Avoid

```
/student

/getStudent

/createJob
```

URLs should use lowercase letters and hyphens where necessary.

---

# 5. HTTP Methods

Use methods according to REST conventions.

| Method | Purpose |
|---------|----------|
| GET | Retrieve resources |
| POST | Create resources |
| PUT | Replace resources |
| PATCH | Partially update resources |
| DELETE | Delete resources |

Avoid using POST for updates unless technically required.

---

# 6. Request Standards

Use JSON for request bodies.

Example

```json
{
  "firstName": "Sohel",
  "lastName": "Shaik",
  "email": "student@nexora.ai"
}
```

Validate all incoming requests using Jakarta Validation.

---

# 7. Response Standards

Successful responses should use a consistent structure.

Example

```json
{
  "success": true,
  "message": "Student created successfully.",
  "data": {
    "id": 101,
    "firstName": "Sohel"
  },
  "timestamp": "2026-07-20T10:30:00Z"
}
```

---

# 8. Error Response Format

All errors must follow the same structure.

Example

```json
{
  "success": false,
  "message": "Validation failed.",
  "errors": [
    {
      "field": "email",
      "message": "Email already exists."
    }
  ],
  "timestamp": "2026-07-20T10:31:00Z"
}
```

Never expose stack traces or internal implementation details.

---

# 9. Pagination

Collection endpoints should support pagination.

Example

```
GET /api/v1/students?page=0&size=20
```

Recommended response

```json
{
  "content": [],
  "page": 0,
  "size": 20,
  "totalElements": 150,
  "totalPages": 8
}
```

---

# 10. Filtering

Support filtering using query parameters.

Examples

```
GET /api/v1/jobs?location=Hyderabad

GET /api/v1/students?branch=CSE

GET /api/v1/applications?status=SHORTLISTED
```

Filters should be optional and composable.

---

# 11. Sorting

Sorting should use query parameters.

Examples

```
?sort=createdAt

?sort=createdAt,desc

?sort=resumeScore,desc
```

Support multiple sort fields where practical.

---

# 12. Authentication

Protected endpoints require JWT.

Example

```
Authorization: Bearer <access_token>
```

Public endpoints

```
/api/v1/auth/login

/api/v1/auth/register

/api/v1/auth/refresh
```

---

# 13. HTTP Status Codes

Use standard HTTP status codes.

| Code | Meaning |
|------|---------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 500 | Internal Server Error |

Avoid returning HTTP 200 for failures.

---

# 14. Rate Limiting

Authentication endpoints should be rate limited.

Examples

- Login
- Registration
- Forgot Password
- OTP Verification

This helps mitigate brute-force attacks.

---

# 15. Idempotency

GET

Safe

PUT

Idempotent

DELETE

Idempotent

POST

Non-idempotent unless explicitly designed otherwise.

Consider idempotency keys for future payment or webhook integrations.

---

# 16. API Documentation

Every endpoint must include:

- Description
- Request example
- Response example
- Error responses
- Authentication requirements

Use OpenAPI (Swagger) for API documentation.

---

# 17. Version Lifecycle

Rules

- Never break existing clients without introducing a new version.
- Deprecate old versions before removal.
- Document migration paths between versions.

---

# 18. Review Checklist

Before releasing an API:

- URL follows standards
- HTTP method is correct
- Validation implemented
- Authentication enforced
- Error handling consistent
- Documentation updated
- Tests completed

---

# 19. Definition of Done

An API is complete when:

- It follows this standard.
- Validation passes.
- Security is implemented.
- Documentation is published.
- Tests pass.
- Error responses are standardized.

---

# References

- PROJECT_VISION.md
- SYSTEM_ARCHITECTURE.md
- CODING_STANDARD.md
- DATABASE_STANDARD.md

---

# Next Document

Continue with:

**07_SECURITY_STANDARD.md**

This document defines authentication, authorization, encryption, OWASP compliance, secure coding practices, JWT policies, audit logging, and security engineering standards for NEXORA AI.
