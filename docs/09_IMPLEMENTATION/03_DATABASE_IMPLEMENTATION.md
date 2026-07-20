NEXORA AI — Database Implementation Document
# NEXORA AI

## Database Implementation Guide

Version: 1.0  
Status: Database Engineering Foundation


# 1. Introduction

This document defines the database architecture for NEXORA AI.

The database stores:



User Information

Student Profiles

Recruiter Data

Resume Data

Skills

Jobs

Applications

AI Results




# 2. Database Technology


Primary Database:



PostgreSQL




Additional Storage:



Redis




Purpose:


PostgreSQL:

Permanent application data


Redis:

Caching and temporary data



# 3. Database Architecture


Structure:



Application Layer

    ↓

Spring Data JPA

    ↓

Hibernate ORM

    ↓

PostgreSQL Database




# 4. Database Naming Rules


Rules:



Table names:

snake_case

Column names:

snake_case

Primary keys:

id

Foreign keys:

entity_id




Example:



student_profile

student_id




# 5. Core Database Tables


Main tables:



users

students

recruiters

companies

resumes

skills

student_skills

jobs

applications

ai_analysis




# 6. Users Table


Purpose:

Stores authentication information.



Table:



users




Columns:



id

name

email

password

role

created_at

updated_at




Roles:



STUDENT

RECRUITER

ADMIN




# 7. Student Table


Purpose:

Stores student career information.



Table:



students




Columns:



id

user_id

college

degree

branch

graduation_year

github_url

linkedin_url

created_at




Relationship:



User

1

↓

1

Student




# 8. Recruiter Table


Purpose:

Stores recruiter information.



Columns:



id

user_id

company_id

designation

phone




Relationship:



User

1

↓

1

Recruiter




# 9. Company Table


Purpose:

Stores company information.



Columns:



id

company_name

industry

website

location

size

created_at




# 10. Resume Table


Purpose:

Stores uploaded resumes.



Columns:



id

student_id

file_url

file_name

upload_date

status




Status:



UPLOADED

PROCESSING

COMPLETED

FAILED




# 11. Resume AI Analysis Table


Purpose:

Stores AI-generated insights.



Columns:



id

resume_id

resume_score

skills_detected

strengths

weaknesses

recommendations

created_at




# 12. Skills Table


Purpose:

Master skill database.



Columns:



id

skill_name

category




Examples:



Java

Python

Spring Boot

AWS

SQL




# 13. Student Skills Table


Purpose:

Many-to-many relationship.



Columns:



id

student_id

skill_id

level




Relationship:



Student

Many

↓

Many

Skills




# 14. Jobs Table


Purpose:

Stores company job postings.



Columns:



id

company_id

title

description

experience

location

salary

status

created_at




Status:



ACTIVE

CLOSED

DRAFT




# 15. Job Skills Table


Purpose:

Required skills for jobs.



Columns:



id

job_id

skill_id

importance




# 16. Applications Table


Purpose:

Tracks student applications.



Columns:



id

student_id

job_id

status

applied_date




Status:



APPLIED

REVIEWING

SHORTLISTED

INTERVIEW

SELECTED

REJECTED




# 17. AI Matching Table


Purpose:

Stores AI matching results.



Columns:



id

student_id

job_id

match_score

explanation

created_at




Example:



Match:

94%

Reason:

Java + Spring Boot Experience




# 18. Database Relationships


Complete relationship:



User

|

|1:1

|

Student

Student

|

|M:N

|

Skills

Student

|

|1:M

|

Resume

Resume

|

|1:1

|

AI Analysis

Company

|

|1:M

|

Jobs

Student

|

|M:N

|

Jobs

(Through Applications)




# 19. Database Migration


Tool:



Flyway




Migration structure:



db/

migration/

V1__create_users.sql

V2__create_students.sql

V3__create_jobs.sql




# 20. Database Optimization


Implement:


## Indexing


Create indexes on:



email

skill_name

job_title

match_score




## Query Optimization


Use:



Pagination

Lazy Loading

Caching




# 21. Security Rules


Database:



Passwords encrypted

Sensitive data protected

No direct entity exposure




# 22. Completion Checklist


Database Created:

⬜


Tables Designed:

✅


Relationships Defined:

✅


Migration Ready:

✅


Optimization Planned:

✅



# 23. Final Vision


The NEXORA AI database should provide a reliable data foundation capable of powering AI-driven career intelli
