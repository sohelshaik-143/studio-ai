# NEXORA AI

# Matching Engine Implementation

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

Develop an AI-powered Matching Engine that intelligently matches students with job opportunities based on skills, education, experience, resume analysis, and recruiter requirements.

---

# 2. Scope

Included

- AI Match Score
- Skill Matching
- Resume Score Integration
- Job Recommendation
- Candidate Ranking
- Recruiter Shortlisting

Excluded

- AI Interview
- Salary Prediction
- Personality Analysis

---

# 3. Architecture

```
Student Profile
        │
Resume AI Analysis
        │
Job Requirements
        │
        ▼
Matching Engine
        │
        ▼
Match Score
        │
        ▼
Recommendations
```

---

# 4. Package Structure

```
matching/

controller/

service/

service/impl/

repository/

entity/

dto/

mapper/

engine/
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

ai_match_score

recommendation

matched_at
```

Recommendation

```
HIGH

MEDIUM

LOW
```

---

# 6. API Endpoints

```
POST /api/v1/matching/run

GET  /api/v1/matching/student

GET  /api/v1/matching/job/{jobId}

GET  /api/v1/matching/top-candidates/{jobId}
```

---

# 7. Matching Criteria

Primary Factors

- Required Skills
- Resume Score
- Education
- Projects
- Experience
- Certifications

Secondary Factors

- Coding Profiles
- GitHub Activity
- Preferred Location
- Job Type Preference

---

# 8. Business Rules

- Match score ranges from 0–100.
- Every new resume upload triggers a new match.
- Every new job posting triggers candidate matching.
- Recruiters see ranked candidates.
- Students receive personalized job recommendations.

---

# 9. Security

- JWT Authentication
- ROLE_STUDENT: View own recommendations
- ROLE_RECRUITER: View candidates for own jobs
- ROLE_ADMIN: Full access

---

# 10. Implementation Steps

Step 1

Create MatchResult entity.

Step 2

Implement matching algorithm.

Step 3

Calculate AI Match Score.

Step 4

Store match results.

Step 5

Expose matching APIs.

Step 6

Test ranking accuracy.

---

# 11. Definition of Done

- Match score generated.
- Candidate ranking works.
- Job recommendations work.
- Recruiter recommendations work.
- APIs tested.
- Authorization verified.

---

# Next Module

11_FRONTEND_INTEGRATION.md
