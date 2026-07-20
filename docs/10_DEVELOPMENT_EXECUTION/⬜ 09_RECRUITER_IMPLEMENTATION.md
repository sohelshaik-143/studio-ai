# NEXORA AI

# Recruiter Module Implementation

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

Build the Recruiter Module to enable companies to:

- Manage recruiter profiles
- Create job postings
- View applicants
- Search candidates
- Shortlist students
- Schedule interviews

---

# 2. Scope

Included

- Recruiter Profile
- Company Profile
- Job Management
- Candidate Search
- Applicant Management
- Shortlisting

Excluded

- Interview AI
- Offer Letter Generation
- HR Analytics

---

# 3. Architecture

```
RecruiterController
        │
        ▼
RecruiterService
        │
        ▼
RecruiterRepository
        │
        ▼
PostgreSQL
```

---

# 4. Package Structure

```
recruiter/

controller/

service/

service/impl/

repository/

entity/

dto/

mapper/
```

---

# 5. Database Design

## recruiters

```
id
user_id
company_id
first_name
last_name
designation
phone
is_verified
created_at
updated_at
```

---

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

## jobs

```
id
company_id
recruiter_id
title
description
location
employment_type
experience_level
salary_min
salary_max
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

Application Status

```
APPLIED
UNDER_REVIEW
SHORTLISTED
INTERVIEW
SELECTED
REJECTED
WITHDRAWN
```

---

# 6. API Endpoints

```
POST   /api/v1/jobs

GET    /api/v1/jobs

GET    /api/v1/jobs/{id}

PUT    /api/v1/jobs/{id}

DELETE /api/v1/jobs/{id}

GET    /api/v1/jobs/{id}/applications

PATCH  /api/v1/applications/{id}/status

GET    /api/v1/recruiters/profile

PUT    /api/v1/recruiters/profile
```

---

# 7. Business Rules

- Recruiters belong to one company.
- Companies can have multiple recruiters.
- Recruiters manage only their company's jobs.
- Students can apply once per job.
- Closed jobs cannot receive applications.
- Only authorized recruiters can shortlist candidates.

---

# 8. Security

- JWT Authentication
- ROLE_RECRUITER access
- ROLE_ADMIN full access
- Students cannot modify job postings.
- Validate recruiter-company ownership.

---

# 9. Implementation Steps

Step 1

Create Company entity.

Step 2

Create Recruiter entity.

Step 3

Create Job entity.

Step 4

Create Application entity.

Step 5

Implement repositories.

Step 6

Implement services.

Step 7

Implement controllers.

Step 8

Test recruiter workflow.

---

# 10. Definition of Done

- Recruiter profile works.
- Company profile works.
- Job CRUD works.
- Student applications work.
- Shortlisting works.
- APIs tested.
- Authorization verified.

---

# Next Module

10_MATCHING_IMPLEMENTATION.md
