# NEXORA AI

# Student Module Implementation

Version: 1.0  
Status: Ready for Development

---

# 1. Objective

Implement the Student module to manage student career profiles, academic information, skills, projects, and professional details.

---

# 2. Scope

Included:

- Student profile management
- Academic details
- Skills
- Projects
- Certifications
- Coding profiles
- Social links
- Profile completion tracking

Excluded:

- Resume AI processing
- Job matching
- Applications

---

# 3. Architecture

```
Student Controller

        ↓

Student Service

        ↓

Student Repository

        ↓

Student Database
```

---

# 4. Package Structure

```
student/

├── controller
│
├── service
│
├── service/impl
│
├── repository
│
├── entity
│
├── dto
│
└── mapper
```

---

# 5. Database Design

## students

```
id

user_id

college_id

roll_number

first_name

last_name

branch

specialization

current_year

cgpa

graduation_year

bio

career_objective

preferred_job_role

preferred_location

expected_salary

availability

github_username

leetcode_username

codechef_username

hackerrank_username

linkedin_url

portfolio_url

profile_completed

is_verified

created_at

updated_at
```

---

# 6. Entity Relationship

```
User

 1

 |

 1

Student
```

Each student belongs to one authenticated user.

---

# 7. DTO Design

## StudentRequest

Contains:

```
Personal Details

Academic Details

Career Preferences

Coding Profiles

Social Links
```

---

## StudentResponse

Returns:

```
Student Information

Skills

Projects

Profile Status
```

---

# 8. API Endpoints

## Get Own Profile

```
GET /api/v1/students/profile
```

---

## Update Profile

```
PUT /api/v1/students/profile
```

---

## Get Student By ID

```
GET /api/v1/students/{id}
```

---

## Search Students

```
GET /api/v1/students
```

---

# 9. Business Rules

- Roll number must be unique.
- Student must have a registered user account.
- CGPA must be between 0 and 10.
- Profile completion is calculated automatically.
- Only profile owner can update details.
- Admin can manage all students.

---

# 10. Security

Rules:

```
ROLE_STUDENT

Can update own profile
```

```
ROLE_RECRUITER

Can view shortlisted student profiles
```

```
ROLE_ADMIN

Full access
```

---

# 11. Implementation Order

Step 1

Create Student Entity.

Step 2

Create Student DTOs.

Step 3

Create Repository.

Step 4

Implement Service Layer.

Step 5

Implement Controller APIs.

Step 6

Add Validation.

Step 7

Test APIs.

---

# 12. Definition of Done

Completed:

- Student profile creation works.
- Profile update works.
- Student information retrieval works.
- Validation implemented.
- Authorization verified.
- APIs tested.

---

# Next Step

05_RESUME_AI_IMPLEMENTATION.md
