# NEXORA AI

## Database Schema Document

Version: 1.0  
Status: Technical Design Foundation


# 1. Introduction

This document defines the database schema design for NEXORA AI.

The schema supports:

- User management
- Student intelligence
- Recruiter hiring
- College management
- AI analysis
- Job matching
- Analytics


Primary database:

PostgreSQL


Supporting storage:

- Redis
- Vector Database
- Object Storage



# 2. Database Design Principles


The schema follows:


## Normalization

Reduce duplicate data.


## Data Ownership

Each service owns its data.


## Security

Sensitive information is protected.


## Scalability

Tables support future growth.



# 3. High Level Entity Relationship

                USERS

                  |

    ------------------------------

    |              |             |

STUDENT       RECRUITER       COLLEGE

    |              |             |

    |              |             |

RESUME         COMPANY       DEPARTMENT

    |

 SKILLS

    |

PROJECTS


    |

    |

   JOBS

    |APPLICATIONS

    |

MATCH_RESULTS


# 4. User Management Schema


## Table: users


Purpose:

Stores all platform users.


Columns:


| Column | Type | Description |
|---|---|---|
| id | UUID | Primary Key |
| name | VARCHAR | User name |
| email | VARCHAR | Unique email |
| password_hash | TEXT | Encrypted password |
| role_id | UUID | User role |
| status | VARCHAR | Account status |
| created_at | TIMESTAMP | Creation time |
| updated_at | TIMESTAMP | Update time |



Indexes:


- email
- role_id



# 5. Roles Table


## Table: roles


Purpose:

Defines user permissions.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| role_name | VARCHAR |
| permissions | JSON |
| created_at | TIMESTAMP |



Example roles:


- STUDENT
- RECRUITER
- COLLEGE_ADMIN
- PLATFORM_ADMIN



# 6. Student Domain Schema


# Table: student_profiles


Purpose:

Stores student career information.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| user_id | UUID |
| college_id | UUID |
| degree | VARCHAR |
| branch | VARCHAR |
| graduation_year | INT |
| location | VARCHAR |
| career_goal | VARCHAR |



Relationship:

User

1

|

1

Student Profile

# Table: education


Stores academic history.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| institution | VARCHAR |
| degree | VARCHAR |
| year | INT |



# 7. Skill Management Schema


# Table: skills


Stores available skills.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| name | VARCHAR |
| category | VARCHAR |



Examples:


- Java
- Python
- React
- AWS



# Table: student_skills


Maps students and skills.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| skill_id | UUID |
| proficiency | INT |
| verification_score | FLOAT |



Relationship:

Student

Many

|

Many

Skills


# 8. Project Intelligence Schema


## Table: projects


Purpose:

Stores student projects.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| title | VARCHAR |
| description | TEXT |
| github_url | TEXT |
| technologies | JSON |
| project_score | FLOAT |



AI generated:


- Complexity score
- Quality score



# 9. Resume Schema


## Table: resumes


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| file_url | TEXT |
| upload_status | VARCHAR |
| uploaded_at | TIMESTAMP |



# Table: resume_analysis


Stores AI analysis.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| resume_id | UUID |
| score | FLOAT |
| extracted_skills | JSON |
| suggestions | JSON |
| analyzed_at | TIMESTAMP |



# 10. Recruiter Schema


# Table: companies


Columns:


| Column | Type |
|-|-|
| id | UUID |
| name | VARCHAR |
| industry | VARCHAR |
| website | TEXT |
| description | TEXT |



# Table: recruiters


Columns:


| Column | Type |
|-|-|
| id | UUID |
| user_id | UUID |
| company_id | UUID |



# 11. Job Management Schema


# Table: jobs


Stores job opportunities.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| company_id | UUID |
| title | VARCHAR |
| description | TEXT |
| location | VARCHAR |
| salary_range | VARCHAR |
| status | VARCHAR |
| created_at | TIMESTAMP |



# Table: job_skills


Maps required skills.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| job_id | UUID |
| skill_id | UUID |
| importance | INT |



# 12. Application Schema


# Table: applications


Stores student applications.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| job_id | UUID |
| status | VARCHAR |
| applied_at | TIMESTAMP |



Statuses:

APPLIED

REVIEWED

SHORTLISTED

INTERVIEW

SELECTED

REJECTED


# 13. AI Matching Schema


# Table: match_results


Stores AI matching results.


Columns:


| Column | Type |
|-|-|
| id | UUID |
| student_id | UUID |
| job_id | UUID |
| match_score | FLOAT |
| explanation | JSON |
| created_at | TIMESTAMP |



Example:


```json
{
"skills":"matched",
"projects":"relevant",
"experience":"good"
}



14. AI Knowledge Schema
Table: skill_embeddings

Stored in vector database.

Contains:

Skill vectors
Resume embeddings
Job embeddings

Purpose:

Semantic matching.




15. Notification Schema
Table: notifications

Columns:

Column	Type
id	UUID
user_id	UUID
title	VARCHAR
message	TEXT
read_status	BOOLEAN
created_at	TIMESTAMP



16. Analytics Schema
Table: analytics_events

Tracks platform activity.

Columns:

Column	Type
id	UUID
user_id	UUID
event_type	VARCHAR
metadata	JSON
timestamp	TIMESTAMP



17. Indexing Strategy

Important indexes:

Users:

email

Jobs:

title
location
created_at

Skills:

skill_name

Applications:

student_id
job_id
status



18. Data Security Strategy

Protected fields:

Passwords
Contact information
Resume files
Private documents

Security:

Encryption
Access control
Audit logging



19. Database Scaling Strategy

Future scaling:

Partitioning

Large tables split by time.

Read Replicas

Improve read performance.

Caching

Redis optimization.



20. Final Database Vision

The NEXORA AI database is designed not only to store information but to create a foundation for career intelligence.

Data becomes:

Profile Data

↓

Knowledge

↓

AI Intelligence

↓

Better Career Decisions
