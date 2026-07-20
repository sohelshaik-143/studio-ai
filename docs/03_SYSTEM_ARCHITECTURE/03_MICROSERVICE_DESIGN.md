# NEXORA AI

## Microservice Design Document

Version: 1.0  
Status: System Architecture Foundation


# 1. Introduction

NEXORA AI follows a microservice architecture where each major business capability is developed as an independent service.

The goal is to achieve:

- Independent development
- Independent deployment
- Better scalability
- Easier maintenance
- Fault isolation


# 2. Microservice Architecture Overview

                 API GATEWAY

                      |
                      Authentication Service

Student Service

Recruiter Service

College Service

Job Service

Application Service

Matching Service

AI Intelligence Service

Analytics Service

Notification Service

File Service
                      |

              Database Layer

              

# 3. Authentication Service


## Service Name

auth-service


## Purpose

Manages user identity and security.


## Responsibilities


- User registration
- Login authentication
- JWT token generation
- Role management
- Password security
- Session management


## Database Ownership


Tables:

- users
- roles
- permissions
- sessions


## APIs


POST /auth/register

POST /auth/login

POST /auth/logout

GET /auth/profile



## Future Enhancements


- OAuth login
- Multi-factor authentication
- Organization verification



# 4. Student Service


## Service Name

student-service


## Purpose

Manages student career profiles.


## Responsibilities


- Student profile management
- Education details
- Skills
- Projects
- Certifications


## Database Ownership


Tables:

- student_profiles
- education
- skills
- projects



## APIs


GET /students/{id}

PUT /students/profile

POST /students/projects

GET /students/skills



# 5. Recruiter Service


## Service Name

recruiter-service


## Purpose

Manages companies and recruiters.


## Responsibilities


- Company profiles
- Recruiter accounts
- Organization verification


## Database Ownership


Tables:

- companies
- recruiters



## APIs


POST /companies

GET /companies/{id}

PUT /companies/profile



# 6. College Service


## Service Name

college-service


## Purpose

Manages educational institutions.


## Responsibilities


- College profiles
- Student mapping
- Placement management


## Database Ownership


Tables:

- colleges
- departments
- college_students



# 7. Job Service


## Service Name

job-service


## Purpose

Handles job opportunities.


## Responsibilities


- Job creation
- Job updates
- Job search
- Requirements management


## Database Ownership


Tables:

- jobs
- job_skills
- job_requirements



## APIs


POST /jobs

GET /jobs

GET /jobs/{id}

PUT /jobs/{id}



# 8. Application Service


## Service Name

application-service


## Purpose

Manages student-job interactions.


## Responsibilities


- Job applications
- Application status
- Hiring pipeline


## Database Ownership


Tables:

- applications
- interviews
- hiring_status



## Workflow


Student applies

↓

Application created

↓

Recruiter reviews

↓

Status updated



# 9. Matching Service


## Service Name

matching-service


## Purpose

Provides intelligent candidate-job matching.


## Responsibilities


- Candidate ranking
- Skill comparison
- Match scoring


## Inputs


Student Profile

+

Job Requirement



## Output


Example:


# 3. Authentication Service


## Service Name

auth-service


## Purpose

Manages user identity and security.


## Responsibilities


- User registration
- Login authentication
- JWT token generation
- Role management
- Password security
- Session management


## Database Ownership


Tables:

- users
- roles
- permissions
- sessions


## APIs


POST /auth/register

POST /auth/login

POST /auth/logout

GET /auth/profile



## Future Enhancements


- OAuth login
- Multi-factor authentication
- Organization verification



# 4. Student Service


## Service Name

student-service


## Purpose

Manages student career profiles.


## Responsibilities


- Student profile management
- Education details
- Skills
- Projects
- Certifications


## Database Ownership


Tables:

- student_profiles
- education
- skills
- projects



## APIs


GET /students/{id}

PUT /students/profile

POST /students/projects

GET /students/skills



# 5. Recruiter Service


## Service Name

recruiter-service


## Purpose

Manages companies and recruiters.


## Responsibilities


- Company profiles
- Recruiter accounts
- Organization verification


## Database Ownership


Tables:

- companies
- recruiters



## APIs


POST /companies

GET /companies/{id}

PUT /companies/profile



# 6. College Service


## Service Name

college-service


## Purpose

Manages educational institutions.


## Responsibilities


- College profiles
- Student mapping
- Placement management


## Database Ownership


Tables:

- colleges
- departments
- college_students



# 7. Job Service


## Service Name

job-service


## Purpose

Handles job opportunities.


## Responsibilities


- Job creation
- Job updates
- Job search
- Requirements management


## Database Ownership


Tables:

- jobs
- job_skills
- job_requirements



## APIs


POST /jobs

GET /jobs

GET /jobs/{id}

PUT /jobs/{id}



# 8. Application Service


## Service Name

application-service


## Purpose

Manages student-job interactions.


## Responsibilities


- Job applications
- Application status
- Hiring pipeline


## Database Ownership


Tables:

- applications
- interviews
- hiring_status



## Workflow


Student applies

↓

Application created

↓

Recruiter reviews

↓

Status updated



# 9. Matching Service


## Service Name

matching-service


## Purpose

Provides intelligent candidate-job matching.


## Responsibilities


- Candidate ranking
- Skill comparison
- Match scoring


## Inputs


Student Profile

+

Job Requirement



## Output


Example:
andidate Match Score:

92%

Reasons:

Java skill match
Spring Boot experience
Similar projects


## Database Ownership


Tables:

- match_results
- recommendation_cache



# 10. AI Intelligence Service


## Service Name

ai-engine-service


## Purpose

Acts as the intelligence layer.


## Responsibilities


## Resume Intelligence

- Resume parsing
- Skill extraction
- Resume scoring


## Skill Intelligence

- Skill classification
- Skill level detection


## Recommendation Engine

- Career suggestions
- Learning paths


## AI Assistant

- Student guidance
- Recruiter assistance



# 11. Analytics Service


## Service Name

analytics-service


## Purpose

Provides insights and reporting.


## Responsibilities


- Student analytics
- Recruitment analytics
- College reports


## Database Ownership


Tables:

- analytics_events
- reports
- metrics



# 12. Notification Service


## Service Name

notification-service


## Purpose

Handles communication.


## Responsibilities


- Email notifications
- Application updates
- Alerts


Channels:


- Email
- Push notifications
- In-app messages



# 13. File Service


## Service Name

file-service


## Purpose

Manages uploaded documents.


Responsibilities:


- Resume storage
- Certificate storage
- File security


Storage:

- Object storage
- Cloud buckets



# 14. Service Communication


Communication methods:


## Synchronous


REST APIs


Used for:

- User requests
- Immediate responses



## Asynchronous


Message Queue


Used for:

- AI processing
- Notifications
- Analytics events



# 15. Scaling Strategy


Each service can scale independently.


Example:


High resume uploads:

↓

Scale AI service


High job searches:

↓

Scale Job service


High login traffic:

↓

Scale Auth service



# 16. Microservice Security


Each service implements:


- Authentication validation
- Authorization checks
- API security
- Internal communication security



# 17. Final Architecture Principle


Each microservice owns one responsibility.


NEXORA AI architecture follows:


"Small independent services working together to create one intelligent career ecosystem."
