# NEXORA AI

# Database Standards

**Version:** 1.0
**Status:** Approved

---

# Document Information

| Property | Value |
|----------|--------|
| Document Name | Database Standards |
| Project | NEXORA AI |
| Version | 1.0 |
| Owner | NEXORA Development Team |
| Status | Approved |
| Last Updated | July 2026 |

---

# Revision History

| Version | Date | Author | Description |
|----------|------|---------|-------------|
| 1.0 | July 2026 | NEXORA Development Team | Initial Database Standards |

---

# Table of Contents

1. Purpose
2. Database Philosophy
3. Database Technology
4. Naming Standards
5. Table Standards
6. Column Standards
7. Primary Keys
8. Foreign Keys
9. Relationships
10. Constraints
11. Indexing Strategy
12. Audit Columns
13. Soft Delete Strategy
14. Migration Standards
15. Performance Standards
16. Backup Strategy
17. Security
18. Review Checklist
19. Definition of Done

---

# 1. Purpose

This document defines the official database engineering standards for the NEXORA AI platform.

The objective is to ensure consistency, maintainability, scalability, and performance across all database objects and migrations.

---

# 2. Database Philosophy

The database is a core business asset.

Every schema change must be:

- Version controlled
- Reviewed
- Backward compatible where possible
- Documented
- Tested before deployment

Database design should prioritize:

- Data integrity
- Performance
- Scalability
- Simplicity
- Maintainability

---

# 3. Database Technology

Primary Database

```
PostgreSQL 16+
```

ORM

```
Spring Data JPA
```

Migration Tool

```
Flyway
```

Connection Pool

```
HikariCP
```

---

# 4. Naming Standards

Tables

```
snake_case
```

Examples

```
users

students

companies

job_posts

applications
```

Columns

```
snake_case
```

Examples

```
first_name

last_name

created_at

updated_at

resume_score
```

---

# 5. Table Standards

Every table should:

- Represent a single business concept.
- Use meaningful names.
- Avoid abbreviations.
- Include audit fields.
- Define appropriate constraints.

---

# 6. Column Standards

Column names should be descriptive.

Examples

```
email

phone_number

profile_image_url

github_username

linkedin_url
```

Avoid generic names like

```
value

data

temp
```

---

# 7. Primary Keys

Preferred strategy

```
BIGSERIAL
```

Future versions may adopt UUIDs for distributed systems.

Primary key name

```
id
```

Every table must have exactly one primary key.

---

# 8. Foreign Keys

Foreign key naming

```
student_id

company_id

job_id

resume_id
```

Always enforce referential integrity.

---

# 9. Relationships

Supported relationships

```
One-to-One

One-to-Many

Many-to-One

Many-to-Many
```

Use join tables only when necessary.

Document every relationship in the corresponding module documentation.

---

# 10. Constraints

Use

- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- NOT NULL
- CHECK

Examples

```
Email UNIQUE

Phone UNIQUE

Resume Score CHECK >= 0
```

Constraints should enforce business rules whenever possible.

---

# 11. Indexing Strategy

Create indexes for:

- Email
- Username
- Foreign Keys
- Status
- Created Date
- Updated Date

Composite indexes should be used only when justified by query patterns.

Regularly review query execution plans.

---

# 12. Audit Columns

Every major table should contain

```
created_at

updated_at
```

Where applicable, also include

```
created_by

updated_by
```

Audit fields support traceability and reporting.

---

# 13. Soft Delete Strategy

Business entities should avoid physical deletion.

Preferred columns

```
is_deleted

deleted_at
```

Benefits

- Data recovery
- Historical reporting
- Compliance
- Auditability

---

# 14. Migration Standards

Use Flyway.

Migration naming

```
V1__initial_schema.sql

V2__roles.sql

V3__users.sql
```

Rules

- Never modify an executed migration.
- Create a new migration for every schema change.
- Keep migrations small and focused.
- Test migrations before release.

---

# 15. Performance Standards

Optimize for

- Indexed searches
- Pagination
- Batch operations
- Efficient joins

Avoid

- SELECT *
- Unbounded queries
- Duplicate indexes
- N+1 query problems

---

# 16. Backup Strategy

Daily

```
Incremental Backup
```

Weekly

```
Full Backup
```

Monthly

```
Archive Backup
```

Backups should be tested regularly through restoration exercises.

---

# 17. Security

Protect the database by:

- Enforcing least-privilege access
- Encrypting credentials
- Using SSL connections
- Storing secrets in environment variables
- Rotating database passwords periodically

Sensitive data should never be logged.

---

# 18. Review Checklist

Before approving database changes:

- Naming standards followed
- Constraints validated
- Indexes reviewed
- Migrations tested
- Rollback considered
- Documentation updated

---

# 19. Definition of Done

Database work is complete when:

- Schema follows standards.
- Migrations execute successfully.
- Performance is acceptable.
- Documentation is updated.
- Security review is completed.

---

# References

- PROJECT_VISION.md
- SYSTEM_ARCHITECTURE.md
- CODING_STANDARD.md

---

# Next Document

Continue with:

**06_API_STANDARD.md**

This document defines REST API design conventions, request and response formats, versioning, pagination, filtering, error handling, and API documentation standards for NEXORA AI.
