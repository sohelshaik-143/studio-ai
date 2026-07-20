# NEXORA AI

# Resume AI Implementation

Version: 1.0  
Status: Ready for Development

---

# 1. Objective

Implement an AI-powered Resume module to analyze student resumes and generate meaningful career insights.

Features:

- Resume upload
- Resume storage
- Text extraction
- Skill extraction
- Resume scoring
- AI feedback
- Resume history

---

# 2. Scope

Included:

- PDF/DOCX upload
- Resume parsing
- Skill identification
- Education extraction
- Project extraction
- Experience extraction
- Resume score generation

Excluded:

- AI resume generation
- Interview preparation
- Video resume analysis

---

# 3. Architecture

```
Student

   ↓

Resume Upload

   ↓

Resume Service

   ↓

File Storage

   ↓

AI Processing Engine

   ↓

Resume Analysis Result
```

---

# 4. Package Structure

```
resume/

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
├── parser
│
├── ai
│
└── storage
```

---

# 5. Database Design

## resumes

```
id

student_id

file_name

file_type

file_size

file_path

resume_text

resume_score

ai_feedback

version

status

created_at

updated_at
```

---

## resume_skills

```
id

resume_id

skill_name

category

confidence_score
```

---

## resume_projects

```
id

resume_id

title

description

technologies
```

---

## resume_experience

```
id

resume_id

company

role

duration

description
```

---

# 6. Resume Processing Flow

```
Upload Resume

↓

Validate File

↓

Store File

↓

Extract Text

↓

AI Analysis

↓

Generate Score

↓

Save Result

↓

Return Response
```

---

# 7. DTO Design

## ResumeUploadRequest

Contains:

```
File

Student ID
```

---

## ResumeResponse

Returns:

```
Resume ID

Score

Skills

Projects

Feedback

Upload Date
```

---

# 8. API Endpoints

## Upload Resume

```
POST /api/v1/resumes/upload
```

---

## Get Resume

```
GET /api/v1/resumes/{id}
```

---

## Get Student Resumes

```
GET /api/v1/resumes/student
```

---

## Analyze Resume

```
POST /api/v1/resumes/{id}/analyze
```

---

## Delete Resume

```
DELETE /api/v1/resumes/{id}
```

---

# 9. AI Processing Rules

Resume Analysis:

```
Skills Match

Projects Quality

Education

Experience

Resume Structure

Keywords
```

Score:

```
0 - 100
```

---

# 10. Business Rules

- Only students can upload resumes.
- Supported formats: PDF, DOCX.
- Maximum file size: 10MB.
- Each upload creates a new version.
- Old resumes remain in history.
- Only owner and authorized recruiters can access resumes.

---

# 11. Security

Rules:

```
ROLE_STUDENT

Upload and manage own resumes
```

```
ROLE_RECRUITER

View shortlisted candidates
```

```
ROLE_ADMIN

Full access
```

---

# 12. Implementation Order

Step 1

Create Resume entities.

Step 2

Create file upload service.

Step 3

Create storage configuration.

Step 4

Implement text extraction.

Step 5

Integrate AI analysis service.

Step 6

Generate resume score.

Step 7

Create APIs.

Step 8

Test complete flow.

---

# 13. Definition of Done

Completed:

- Resume upload works.
- Files stored securely.
- Text extraction works.
- AI analysis works.
- Score generated.
- Feedback generated.
- APIs tested.

---

# Next Step

06_RECRUITER_MODULE_IMPLEMENTATION.md
