NEXORA AI — Recruiter Module Implementation Document
# NEXORA AI

## Recruiter Module Implementation

Version: 1.0  
Status: Recruiter Platform Core


# 1. Introduction

The Recruiter Module manages company-side hiring operations.

Responsibilities:



Recruiter Profile

Company Management

Job Creation

Candidate Discovery

Application Management

Hiring Workflow

AI Talent Insights



# 2. Recruiter Module Architecture


Flow:



Recruiter

↓

Frontend Dashboard

↓

Recruiter Controller

↓

Recruiter Service

↓

Database

↓

AI Matching Engine



# 3. Recruiter Data Model


Recruiter Entity:



Recruiter

{

id

userId

companyId

designation

phone

createdAt

updatedAt

}



# 4. Recruiter Database Table


Table:



recruiters



Columns:



id

user_id

company_id

designation

phone

created_at

updated_at



Relationship:



User

1

↓

1

Recruiter




# 5. Company Module


Purpose:

Store organization information.



Company Entity:



Company

{

id

name

industry

website

location

size

description

}



Database:



companies




# 6. Company Profile API


Base URL:



/api/v1/recruiters



## Create Company Profile


Endpoint:



POST /company



Request:


```json
{
"name":"Tech Company",
"industry":"Software",
"location":"India"
}
Get Company Profile

Endpoint:

GET /company

7. Job Management Module

Purpose:

Allow recruiters to create and manage opportunities.

Job Entity:

Job

{

id

companyId

title

description

experience

location

salary

status

createdAt

}

8. Create Job API

Endpoint:

POST /jobs


Request:

{
"title":"Backend Developer",
"skills":[
"Java",
"Spring Boot"
],
"experience":"0-2 years"
}

Response:

{
"message":"Job Created Successfully"
}
9. Job Status Management

States:

DRAFT

ACTIVE

PAUSED

CLOSED

10. Required Skills System

Purpose:

Define hiring requirements.

Job Skills:

job_skills


Fields:

id

job_id

skill_id

importance


Importance:

MANDATORY

PREFERRED

OPTIONAL

11. Candidate Discovery Module

Purpose:

Find suitable candidates automatically.

Flow:

Create Job

↓

AI Matching Engine

↓

Analyze Student Profiles

↓

Rank Candidates

↓

Display Results

12. Candidate Search API

Endpoint:

GET /jobs/{id}/candidates


Response:

[
{
"name":"Student A",
"matchScore":94
},
{
"name":"Student B",
"matchScore":87
}
]
13. Candidate Profile View

Recruiter can see:

Education

Skills

Projects

GitHub

Resume Score

AI Match Score


Sensitive data:

Protected until:

Candidate Consent

OR

Shortlist Stage

14. Application Management

Application Flow:

Student Applies

↓

Recruiter Reviews

↓

Shortlist

↓

Interview

↓

Decision

15. Application Status

Statuses:

APPLIED

VIEWED

SHORTLISTED

INTERVIEW

SELECTED

REJECTED

16. Application APIs
View Applications
GET /jobs/{jobId}/applications

Update Status
PUT /applications/{id}/status


Example:

{
"status":"SHORTLISTED"
}
17. Recruiter Dashboard API

Endpoint:

GET /recruiter/dashboard


Returns:

Active Jobs

Total Applicants

Shortlisted Candidates

Hiring Analytics

AI Recommendations

18. AI Hiring Assistant

Future feature:

Recruiter Copilot.

Capabilities:

Generate Job Description

Suggest Required Skills

Find Hidden Talent

Generate Interview Questions

19. Security Rules

Recruiter can:

Manage Own Company

Create Jobs

View Applications

Update Hiring Status


Recruiter cannot:

Modify Other Companies

Access Private Student Data

20. Service Layer

Services:

RecruiterService

CompanyService

JobService

ApplicationService

CandidateService


Responsibilities:

Business Logic

Validation

Authorization

AI Integration

21. Testing

Test:

Company Creation

Job Creation

Candidate Search

Application Updates

Permission Control

22. Completion Checklist

Recruiter Profile:

✅

Company Management:

✅

Job Posting:

✅

Candidate Discovery:

✅

Application Workflow:

✅

AI Hiring Assistant:

⬜

23. Final Vision

The Recruiter Module transforms traditional hiring into an intelligent talent discovery system where companies find the right candidates faster and more accurately
