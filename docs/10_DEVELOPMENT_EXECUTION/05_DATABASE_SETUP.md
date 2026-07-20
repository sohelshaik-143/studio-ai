# NEXORA AI

# Database Setup Guide

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

This document defines the database architecture, configuration, and migration strategy for the NEXORA AI backend.

At the end of this phase, the database should:

- Connect successfully with Spring Boot
- Support Flyway migrations
- Be normalized
- Be production-ready
- Support future scalability
- Be optimized for AI-based recruitment workflows

---

# 2. Database Technology

Database

```
PostgreSQL 16+
```

ORM

```
Spring Data JPA (Hibernate)
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

# 3. Database Configuration

Configure

```
application.yml
```

Include

```
Database URL

Username

Password

Driver

Dialect

Connection Pool

DDL Mode

Flyway
```

---

# 4. Database Naming Standards

Tables

```
snake_case
```

Examples

```
users

students

companies

jobs

resumes

applications
```

Columns

```
snake_case
```

Primary Keys

```
id
```

Foreign Keys

```
student_id

company_id

job_id
```

---

# 5. Initial Database Structure

Core Tables

```
users

roles

students

colleges

companies

recruiters

jobs

skills

resumes

resume_skills

applications

interviews

notifications

ai_scores

audit_logs
```

---

# 6. Relationships

Users

↓

Student

↓

Resume

↓

Applications

↓

Jobs

↓

Company

Recruiter

↓

Company

College

↓

Students

---

# 7. Flyway Migration Structure

Create

```
V1__initial_schema.sql

V2__roles.sql

V3__users.sql

V4__students.sql

V5__colleges.sql

V6__companies.sql

V7__recruiters.sql

V8__jobs.sql

V9__skills.sql

V10__resume.sql

V11__applications.sql

V12__notifications.sql

V13__audit_logs.sql
```

---

# 8. Indexing Strategy

Create indexes on

```
email

username

student_id

company_id

job_id

created_at

updated_at

status
```

Purpose

Improve search performance.

---

# 9. Constraints

Use

```
Primary Keys

Foreign Keys

Unique Constraints

Not Null

Check Constraints
```

Examples

```
Email must be unique

Phone number unique

GitHub username unique
```

---

# 10. Soft Delete Strategy

Instead of deleting records permanently

Use

```
is_deleted

deleted_at
```

Advantages

- Data recovery
- Audit history
- Analytics support

---

# 11. Audit Fields

Every major table should contain

```
created_at

updated_at

created_by

updated_by
```

---

# 12. Enum Strategy

Store enums for

```
Role

Gender

Job Type

Application Status

Interview Status

Notification Type
```

---

# 13. Performance Optimization

Use

```
Indexes

Pagination

Batch Fetching

Lazy Loading

Connection Pooling
```

Avoid

```
N+1 Queries

Unnecessary Joins

SELECT *
```

---

# 14. Backup Strategy

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

---

# 15. Security

Enable

```
SSL Connections

Encrypted Passwords

Least Privilege Access

Separate Database User

Environment Variables
```

Never store

```
Passwords

Secrets

API Keys
```

inside SQL scripts.

---

# 16. Testing

Verify

```
Connection

Migration Success

Rollback

Indexes

Relationships

Constraints
```

---

# 17. Initial Git Commit

Commit message

```
feat: configure PostgreSQL database and Flyway migrations
```

---

# 18. Definition of Done

Database connected

Flyway working

Migration scripts created

Indexes added

Relationships defined

Naming standards followed

Application starts successfully

---

# 19. Deliverables

PostgreSQL configured

Flyway initialized

Migration folder created

Database schema prepared

Ready for Authentication module

---

# 20. Next Phase

Begin implementing Authentication using Spring Security and JWT.

The database foundation created in this phase will support all future modules including Students, Recruiters, Companies, AI Matching, and Resume Intelligence.
