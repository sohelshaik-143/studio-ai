# NEXORA AI

# Project Glossary

**Version:** 1.0  
**Status:** Approved

---

# Document Information

| Property | Value |
|----------|--------|
| Document Name | Project Glossary |
| Project | NEXORA AI |
| Version | 1.0 |
| Owner | NEXORA Development Team |
| Status | Approved |
| Last Updated | July 2026 |

---

# Revision History

| Version | Date | Author | Description |
|----------|------|---------|-------------|
| 1.0 | July 2026 | NEXORA Development Team | Initial Project Glossary |

---

# Table of Contents

1. Purpose
2. Business Terms
3. Technical Terms
4. AI Terms
5. Authentication Terms
6. Database Terms
7. API Terms
8. General Project Terms
9. Abbreviations
10. References

---

# 1. Purpose

This glossary defines the terminology used throughout the NEXORA AI project.

It provides a common vocabulary for developers, testers, designers, project managers, and future contributors.

---

# 2. Business Terms

| Term | Definition |
|------|------------|
| Student | A user seeking internships or employment opportunities. |
| Recruiter | A user representing an organization that posts jobs and hires candidates. |
| College | An educational institution managing student placement activities. |
| Administrator | A platform user responsible for managing the application and its users. |
| Job Posting | A published employment opportunity created by a recruiter. |
| Application | A student's submission for a specific job posting. |
| Placement | The successful hiring of a student. |

---

# 3. Technical Terms

| Term | Definition |
|------|------------|
| Backend | The Spring Boot application that provides APIs and business logic. |
| Frontend | The React application used by end users. |
| Module | A self-contained functional area such as Authentication or Resume. |
| DTO | Data Transfer Object used for communication between client and server. |
| Entity | A persistent domain object mapped to a database table. |
| Repository | Data access layer implemented using Spring Data JPA. |
| Service | Business logic layer between controllers and repositories. |
| Controller | REST layer responsible for handling HTTP requests. |

---

# 4. AI Terms

| Term | Definition |
|------|------------|
| Resume Parser | Extracts structured information from uploaded resumes. |
| Resume Score | AI-generated evaluation of resume quality. |
| Skill Gap | Missing skills identified for a target role. |
| Candidate Match Score | AI-generated score representing compatibility between a student and a job. |
| Career Recommendation | AI-generated suggestions for learning paths and career opportunities. |
| Matching Engine | AI component responsible for ranking candidates against job requirements. |

---

# 5. Authentication Terms

| Term | Definition |
|------|------------|
| JWT | JSON Web Token used for stateless authentication. |
| Access Token | Short-lived token used to authorize API requests. |
| Refresh Token | Long-lived token used to obtain new access tokens. |
| RBAC | Role-Based Access Control. |
| Authentication | Verifying a user's identity. |
| Authorization | Determining what a user is allowed to access. |

---

# 6. Database Terms

| Term | Definition |
|------|------------|
| Primary Key | Unique identifier for a database record. |
| Foreign Key | Column establishing a relationship between two tables. |
| Migration | Version-controlled database schema change managed by Flyway. |
| Index | Database structure that improves query performance. |
| Soft Delete | Marking records as deleted without physically removing them. |

---

# 7. API Terms

| Term | Definition |
|------|------------|
| Endpoint | A URL exposed by the backend API. |
| Request DTO | Object received from the client. |
| Response DTO | Object returned to the client. |
| Pagination | Dividing large datasets into manageable pages. |
| Filtering | Restricting returned data based on query parameters. |
| Sorting | Ordering returned data by one or more fields. |

---

# 8. General Project Terms

| Term | Definition |
|------|------------|
| Documentation-First Development | Writing complete design documentation before implementation. |
| Modular Monolith | Architectural style with clearly separated modules inside a single deployable application. |
| CI | Continuous Integration. |
| CD | Continuous Delivery / Continuous Deployment. |
| MVP | Minimum Viable Product. |
| SaaS | Software as a Service. |

---

# 9. Abbreviations

| Abbreviation | Meaning |
|--------------|---------|
| AI | Artificial Intelligence |
| API | Application Programming Interface |
| CI | Continuous Integration |
| CD | Continuous Delivery / Deployment |
| DTO | Data Transfer Object |
| ERD | Entity Relationship Diagram |
| HTTP | Hypertext Transfer Protocol |
| JPA | Java Persistence API |
| JWT | JSON Web Token |
| LTS | Long-Term Support |
| ORM | Object Relational Mapping |
| RBAC | Role-Based Access Control |
| REST | Representational State Transfer |
| SQL | Structured Query Language |
| UI | User Interface |
| UX | User Experience |

---

# 10. References

- PROJECT_VISION.md
- SYSTEM_ARCHITECTURE.md
- DOCUMENTATION_STANDARD.md
- CODING_STANDARD.md
- DATABASE_STANDARD.md
- API_STANDARD.md
- SECURITY_STANDARD.md
- GIT_WORKFLOW.md

---

# Next Document

Continue with:

**10_DECISION_LOG.md**

This document records significant architectural and technical decisions made during the development of NEXORA AI, including the rationale, alternatives considered, and expected impact.
