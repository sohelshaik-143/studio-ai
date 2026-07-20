# NEXORA AI

# Recruiter Module Implementation

Version: 1.0  
Status: Ready for Development

---

# 1. Objective

Implement recruiter features to allow companies to manage jobs, candidates, and recruitment activities.

---

# 2. Scope

Included:

- Recruiter profile
- Company management
- Job posting
- Candidate applications
- Candidate shortlisting
- Application status tracking

Excluded:

- Interview AI
- Offer generation
- HR payroll

---

# 3. Architecture

```
Recruiter

    ↓

Recruiter Controller

    ↓

Recruiter Service

    ↓

Repository Layer

    ↓

PostgreSQL
```

---

# 4. Package Structure

```
recruiter/

├── controller
├── service
├── service/impl
├── repository
├── entity
├── dto
└── mapper
```

---

# 5. Database Design

## companies

```
id

company_name

industry

website

email

phone

address

description

logo_url

created_at

updated_at
```

---

## recruiters

```
id

user_id

company_id

designation

phone

verified

created_at

updated_at
```

---

## jobs

```
id

company_id

recruiter_id

title

description

skills_required

location

employment_type

experience_level

salary_range

deadline

status

created_at

updated_at
```

---

## applications

```
id

job_id

student_id

resume_id

status

applied_at

updated_at
```

---

# 6. Application Status

```
APPLIED

UNDER_REVIEW

SHORTLISTED

INTERVIEW

SELECTED

REJECTED
```

---

# 7. API Endpoints

Create Job

```
POST /api/v1/jobs
```

---

Get Jobs

```
GET /api/v1/jobs
```

---

Get Job Details

```
GET /api/v1/jobs/{id}
```

---

Update Job

```
PUT /api/v1/jobs/{id}
```

---

Delete Job

```
DELETE /api/v1/jobs/{id}
```

---

View Applicants

```
GET /api/v1/jobs/{id}/applications
```

---

Update Application Status

```
PATCH /api/v1/applications/{id}/status
```

---

# 8. Business Rules

- Recruiter belongs to one company.
- Recruiter manages only own company jobs.
- Students can apply once per job.
- Closed jobs cannot accept applications.
- Shortlisting requires recruiter permission.

---

# 9. Security

```
ROLE_RECRUITER

Manage company jobs
```

```
ROLE_STUDENT

Apply for jobs
```

```
ROLE_ADMIN

Full access
```

---

# 10. Implementation Order

Step 1

Create Company entity.

Step 2

Create Recruiter entity.

Step 3

Create Job entity.

Step 4

Create Application entity.

Step 5

Create repositories.

Step 6

Implement services.

Step 7

Create APIs.

Step 8

Test recruitment flow.

---

# 11. Definition of Done

Completed:

- Company profile works.
- Recruiter profile works.
- Job CRUD works.
- Applications work.
- Shortlisting works.
- Security verified.

---

# Next Step

07_MATCHING_ENGINE_IMPLEMENTATION.md
