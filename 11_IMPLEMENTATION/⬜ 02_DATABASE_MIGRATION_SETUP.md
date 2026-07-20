# NEXORA AI

# Database Migration Setup

Version: 1.0  
Status: Ready for Implementation

---

# 1. Objective

Configure database version control using PostgreSQL and Flyway.

After completion:

- Database connection works
- Migration system is active
- Schema changes are version controlled
- Backend is ready for entity development

---

# 2. Technology

```
PostgreSQL

Flyway

Spring Data JPA
```

---

# 3. Database Configuration

Development Database:

```
Name:
nexora_dev

Engine:
PostgreSQL

Port:
5432
```

---

# 4. Flyway Structure

Create:

```
src/main/resources/

└── db

    └── migration

        └── V1__initial_schema.sql
```

---

# 5. Migration Naming Rules

Format:

```
V{version}__{description}.sql
```

Example:

```
V1__initial_schema.sql

V2__create_users_table.sql

V3__create_student_table.sql
```

Rules:

- Version must be unique
- Never modify completed migrations
- Create new migration files for changes

---

# 6. Initial Migration

File:

```
V1__initial_schema.sql
```

Purpose:

- Verify Flyway connection
- Prepare migration pipeline

Initial content:

```
-- Initial database migration
-- Tables will be added in future migrations
```

---

# 7. Application Configuration

Enable Flyway:

```
spring:
  flyway:
    enabled: true
    locations: classpath:db/migration
```

---

# 8. Database Development Flow

```
Developer

↓

Create Migration File

↓

Run Application

↓

Flyway Executes Migration

↓

Database Updated

↓

Commit Migration
```

---

# 9. Future Migration Plan

```
V1__initial_schema.sql

V2__users.sql

V3__roles.sql

V4__students.sql

V5__companies.sql

V6__jobs.sql

V7__resumes.sql

V8__matching.sql
```

---

# 10. Verification

Run:

```
mvn spring-boot:run
```

Verify:

```
Flyway migration successful
Database connection successful
Application starts
```

---

# 11. Git Commit

Commit:

```
feat: configure database migration with flyway
```

---

# 12. Definition of Done

Completed:

- PostgreSQL connected
- Flyway configured
- Migration folder created
- Initial migration added
- Database versioning ready

---

# Next Step

03_AUTHENTICATION_IMPLEMENTATION.md
