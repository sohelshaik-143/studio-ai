# NEXORA AI

# Student Module Implementation

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

Implement the Student module to manage student profiles, academic details, skills, projects, certifications, and career information.

---

# 2. Scope

Included

- Student Profile
- Academic Details
- Skills Management
- Projects
- Certifications
- Social Links
- Profile Update
- Profile View

Excluded

- Resume AI
- Job Matching
- Applications

---

# 3. Architecture

```
StudentController
        │
        ▼
StudentService
        │
        ▼
StudentRepository
        │
        ▼
PostgreSQL
```

---

# 4. Package Structure

```
student/

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

## Table

```
students
```

Columns

```
id

user_id

first_name

last_name

roll_number

college

branch

year

cgpa

phone

github_username

linkedin_url

leetcode_username

codeforces_username

portfolio_url

bio

profile_image

created_at

updated_at
```

---

# 6. API Endpoints

```
GET    /api/v1/students/profile

PUT    /api/v1/students/profile

GET    /api/v1/students/{id}

GET    /api/v1/students

DELETE /api/v1/students/{id}
```

---

# 7. Business Rules

- Every student must have one user account.
- Roll number must be unique.
- GitHub username is optional.
- CGPA must be between 0.0 and 10.0.
- Only the profile owner or Admin can update student details.

---

# 8. Security

- JWT Authentication
- ROLE_STUDENT can update own profile.
- ROLE_ADMIN has full access.
- Validate all request data.

---

# 9. Implementation Steps

Step 1

Create Student entity.

Step 2

Create StudentRepository.

Step 3

Create DTOs.

Step 4

Implement StudentService.

Step 5

Implement StudentController.

Step 6

Add validations.

Step 7

Test APIs.

---

# 10. Definition of Done

- Student profile created.
- Profile updated successfully.
- Profile retrieved successfully.
- Validation works.
- Authorization works.
- APIs tested.

---

# Next Module

08_RESUME_AI_IMPLEMENTATION.md
