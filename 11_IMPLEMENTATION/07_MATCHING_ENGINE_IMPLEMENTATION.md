# NEXORA AI

# Matching Engine Implementation

Version: 1.0  
Status: Ready for Development

---

# 1. Objective

Implement an AI-powered matching system to connect students with suitable job opportunities and help recruiters find the best candidates.

---

# 2. Scope

Included:

- Student-job matching
- Candidate ranking
- AI match score
- Skill comparison
- Job recommendations
- Recruiter candidate suggestions

Excluded:

- AI Interview
- Salary prediction
- Personality analysis

---

# 3. Architecture

```
Student Profile

      +

Resume Analysis

      +

Job Requirements

      ↓

Matching Engine

      ↓

AI Match Score

      ↓

Recommendations
```

---

# 4. Package Structure

```
matching/

├── controller

├── service

├── service/impl

├── repository

├── entity

├── dto

├── engine

└── mapper
```

---

# 5. Database Design

## match_results

```
id

student_id

job_id

resume_score

skill_score

education_score

experience_score

project_score

ai_match_score

recommendation

created_at
```

---

# 6. Matching Algorithm

Factors:

```
Skills          40%

Resume Score    20%

Projects        15%

Experience      10%

Education       10%

Certificates     5%
```

Total:

```
100%
```

---

# 7. Matching Flow

```
New Job Created

↓

Extract Required Skills

↓

Compare Student Profiles

↓

Analyze Resume Data

↓

Calculate Score

↓

Store Result

↓

Show Recommendation
```

---

# 8. API Endpoints

Run Matching

```
POST /api/v1/matching/run
```

---

Student Recommendations

```
GET /api/v1/matching/student
```

---

Job Candidates

```
GET /api/v1/matching/job/{jobId}
```

---

Top Candidates

```
GET /api/v1/matching/top-candidates/{jobId}
```

---

# 9. Business Rules

- Match score range: 0-100.
- Higher score means better compatibility.
- New resume upload triggers recalculation.
- New job posting triggers candidate analysis.
- Recruiters only view candidates for their jobs.

---

# 10. Security

```
ROLE_STUDENT

View own recommendations
```

```
ROLE_RECRUITER

View candidate rankings
```

```
ROLE_ADMIN

Manage matching system
```

---

# 11. Implementation Order

Step 1

Create MatchResult entity.

Step 2

Create matching DTOs.

Step 3

Create matching repository.

Step 4

Implement scoring engine.

Step 5

Integrate Resume AI data.

Step 6

Generate recommendations.

Step 7

Create APIs.

Step 8

Test ranking accuracy.

---

# 12. Definition of Done

Completed:

- Matching algorithm works.
- Scores generated.
- Recommendations displayed.
- Candidate ranking works.
- APIs tested.
- Security verified.

---

# Next Step

08_FRONTEND_IMPLEMENTATION.md
