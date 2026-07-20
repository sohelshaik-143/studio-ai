# NEXORA AI

# Resume AI Implementation

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

Build an AI-powered Resume Module capable of:

- Resume Upload
- Resume Parsing
- Resume Scoring
- Skill Extraction
- Project Extraction
- Education Extraction
- Experience Extraction
- AI Feedback
- Resume Version Management

---

# 2. Scope

Included

- PDF Upload
- DOCX Upload
- Resume Storage
- AI Parsing
- Resume Score
- Skill Detection
- Resume Analysis
- Resume History

Excluded

- Interview AI
- ATS Optimization
- Video Resume
- AI Resume Builder

---

# 3. Architecture

```
Client
   │
   ▼
ResumeController
   │
   ▼
ResumeService
   │
   ▼
AI Parsing Service
   │
   ▼
Resume Repository
   │
   ▼
PostgreSQL
```

---

# 4. Package Structure

```
resume/

controller/

service/

service/impl/

repository/

entity/

dto/

mapper/

parser/

ai/

storage/
```

---

# 5. Database Design

## Table

```
resumes
```

Columns

```
id

student_id

file_name

file_type

file_size

storage_path

resume_text

resume_score

ai_feedback

version

status

uploaded_at

updated_at
```

---

## Table

```
resume_skills
```

Columns

```
id

resume_id

skill_name

skill_category

confidence_score
```

---

## Table

```
resume_projects
```

Columns

```
id

resume_id

project_title

description

technologies
```

---

## Table

```
resume_education
```

Columns

```
id

resume_id

institution

degree

branch

cgpa

start_year

end_year
```

---

## Table

```
resume_experience
```

Columns

```
id

resume_id

company

role

duration

description
```

---

# 6. API Endpoints

```
POST   /api/v1/resumes/upload

GET    /api/v1/resumes/{id}

GET    /api/v1/resumes/student

PUT    /api/v1/resumes/{id}

DELETE /api/v1/resumes/{id}

POST   /api/v1/resumes/analyze
```

---

# 7. Business Rules

- One student can upload multiple resume versions.
- Only PDF and DOCX files are allowed.
- Maximum file size: 10 MB.
- Resume score ranges from 0–100.
- AI feedback is regenerated after every new upload.
- Only the owner or Admin can access a resume.

---

# 8. Security

- JWT Authentication
- ROLE_STUDENT upload access
- ROLE_RECRUITER read access (shortlisted candidates only)
- ROLE_ADMIN full access
- Validate file type and size
- Sanitize uploaded files

---

# 9. AI Features

Resume Parsing

- Personal Information
- Education
- Skills
- Projects
- Experience
- Certifications

Resume Analysis

- Resume Score
- Skill Gap
- Missing Sections
- ATS Compatibility
- Improvement Suggestions

Future AI

- Resume Builder
- ATS Optimization
- Career Recommendation
- Interview Readiness Score

---

# 10. Implementation Steps

Step 1

Create Resume entity.

Step 2

Implement file upload service.

Step 3

Extract text from PDF/DOCX.

Step 4

Implement AI parsing service.

Step 5

Generate Resume Score.

Step 6

Store extracted data.

Step 7

Expose REST APIs.

Step 8

Test upload and analysis flow.

---

# 11. Definition of Done

- Resume upload works.
- Resume stored successfully.
- AI parsing completed.
- Skills extracted.
- Resume score generated.
- AI feedback generated.
- APIs tested.
- Security verified.

---

# Next Module

09_RECRUITER_IMPLEMENTATION.md
