# NEXORA AI — MASTER PRODUCT DEVELOPMENT PROMPT

You are a senior product architect, AI engineer, backend engineer, frontend engineer, and UI/UX designer.

Build a production-grade AI-powered career intelligence platform called **NEXORA AI**.

NEXORA AI is a complete career operating system that connects students, colleges, recruiters, and companies through artificial intelligence.

The platform should analyze student capabilities, improve career readiness, recommend suitable opportunities, and help recruiters identify the best candidates using AI-driven scoring and matching.

The product must feel like a combination of:

- LinkedIn
- Resume Intelligence Platform
- Applicant Tracking System
- AI Career Coach
- Recruitment Intelligence Engine

Build it with enterprise-level architecture, scalable design, clean UI, and production standards.

---

# PRODUCT OBJECTIVE

The main goal of NEXORA AI:

For Students:

- Understand their career position
- Analyze resume quality
- Identify skill gaps
- Improve employability
- Find suitable jobs
- Track career growth


For Recruiters:

- Discover talented candidates
- Analyze candidate profiles
- Rank applicants
- Shortlist based on AI score
- Manage recruitment workflow


For Colleges:

- Track student performance
- Understand placement readiness
- Identify skill gaps
- Improve placement outcomes


---

# TECHNOLOGY STACK

## Backend

Use:

Java 21

Spring Boot 3.x

Spring Security

Spring Data JPA

Hibernate

PostgreSQL

Flyway Migration

Maven

Lombok

JWT Authentication

REST APIs

Swagger Documentation


Architecture:

Use modular monolithic architecture.

Follow:

Controller Layer

Service Layer

Repository Layer

Entity Layer

DTO Layer

Exception Handling Layer

Security Layer


---

# BACKEND MODULES

Create the following modules:


## 1. AUTHENTICATION MODULE

Functions:

User registration

User login

JWT authentication

Refresh token

Logout

Password encryption

Role-based authorization


Roles:

STUDENT

RECRUITER

COLLEGE

ADMIN


Security requirements:

- BCrypt password hashing
- JWT token validation
- Protected APIs
- Permission-based access


---

# 2. STUDENT MODULE

Create a complete student career profile system.

Student profile fields:

Personal Information:

- Name
- Email
- Phone
- Location


Academic Information:

- College
- Branch
- Degree
- CGPA
- Graduation year


Professional Information:

- Skills
- Projects
- Certifications
- Internships
- Experience


Coding Profiles:

- GitHub username
- LeetCode profile
- CodeChef profile
- HackerRank profile


Social Profiles:

- LinkedIn
- Portfolio website


Student dashboard should show:

Profile completion percentage

Resume score

Skill score

Career readiness score

Recommended jobs

Missing skills

Learning roadmap


---

# 3. RESUME AI INTELLIGENCE MODULE

Create an advanced AI resume analysis system.


Functions:

Resume upload:

Support:

PDF

DOCX


Process:

Upload Resume

↓

Extract Text

↓

Analyze Content

↓

Identify Skills

↓

Analyze Projects

↓

Evaluate Experience

↓

Generate Score

↓

Provide Suggestions


AI should analyze:


## Resume Quality Score

Range:

0-100


Evaluation:


Formatting:

15%


Skills:

25%


Projects:

20%


Experience:

15%


Education:

10%


Keywords:

15%



Generate:

Resume score

Strengths

Weaknesses

Improvement suggestions


Example:

Resume Score:

82/100


Strength:

Strong Java backend skills


Weakness:

Missing cloud deployment experience


Suggestion:

Learn AWS and Docker


---

# 4. SKILL GAP ANALYSIS ENGINE


Analyze:

Student current skills

Target job requirements


Generate:

Missing skills

Priority level

Learning roadmap


Example:


Target:

Java Backend Developer


Current:

Java

Spring Boot

SQL


Missing:

Docker

AWS

Microservices


Output:


Beginner:

Docker basics


Intermediate:

AWS deployment


Advanced:

Microservices architecture


---

# 5. AI MATCHING ENGINE


Build intelligent recommendation system.


Match students with jobs using:


Skills Match:

40%


Resume Score:

20%


Projects:

15%


Experience:

10%


Education:

10%


Certifications:

5%



Generate:

AI Match Score:

0-100


Example:


Job:

Java Backend Engineer


Candidate:

Sohel


Match Score:

91%


Reason:

Strong Java and Spring Boot skills

Relevant projects

Good coding profile


---

# 6. RECRUITER MODULE


Recruiters can:


Company Management:

Create company profile

Update company information

Upload company logo


Job Management:

Create jobs

Edit jobs

Delete jobs

View applications


Job fields:

Title

Description

Required skills

Experience

Salary

Location

Employment type


Candidate Management:

View applicants

AI ranking

Shortlist candidates

Reject candidates

Track hiring status


---

# 7. COLLEGE MODULE


College administrators can:


Manage students

Upload student data

View analytics

Track placement readiness


Dashboard:


Total students

Ready candidates

Average resume score

Average skill score

Placement statistics


---

# FRONTEND REQUIREMENTS


Technology:

React

TypeScript

Tailwind CSS

Modern component architecture


Design style:

Premium SaaS dashboard.

Inspired by:

Apple

Tesla

Linear

Vercel

Stripe


UI requirements:

Dark mode

Glassmorphism

Smooth animations

Responsive design

Modern cards

Interactive charts


---

# FRONTEND PAGES


## Landing Page

Sections:

Hero section

AI career intelligence explanation

Features

Student benefits

Recruiter benefits

College benefits

Testimonials

CTA


---

# STUDENT DASHBOARD


Components:


Career Score Card


Display:


Overall Score:

85/100


Resume Score:

82


Skill Score:

88


Job Match:

91



Resume Analysis Card


Show:

Score

Strengths

Weaknesses

Suggestions


Skill Gap Card


Show:

Current skills

Missing skills

Learning roadmap


Job Recommendation Card


Show:

Job title

Company

Match percentage


---

# RECRUITER DASHBOARD


Show:


Active Jobs

Applicants

Top Candidates

AI Ranking


Candidate Card:


Name

Skills

Resume Score

Match Score

GitHub

Projects


---

# DATABASE DESIGN


Create entities:


User

Role

Student

Recruiter

Company

Job

Application

Resume

ResumeSkill

ResumeProject

MatchResult

Skill


Use:

PostgreSQL

Flyway migrations


---

# API DESIGN


Create REST APIs:


Authentication:

POST /auth/register

POST /auth/login


Student:

GET /students/profile

PUT /students/profile


Resume:

POST /resume/upload

GET /resume/analysis


Jobs:

POST /jobs

GET /jobs


Matching:

GET /matching/recommendations


Applications:

POST /applications

PATCH /applications/status


---

# LOGGING AND ERROR HANDLING


Implement:

Global Exception Handler

Custom Exceptions

Validation Errors

SLF4J Logging


Never use:

System.out.println()


---

# TESTING


Implement:


Backend:

JUnit

Mockito

Spring Boot Test


Frontend:

Jest

React Testing Library


API:

Postman

Swagger


---

# DEPLOYMENT


Prepare:


Docker

Environment variables

Production configuration

Database backup

Monitoring


Architecture:


Frontend

↓

Backend API

↓

Database

↓

AI Services


---

# DEVELOPMENT ORDER


Build step by step:


Phase 1:

Backend Foundation


Phase 2:

Database


Phase 3:

Authentication


Phase 4:

Student Module


Phase 5:

Resume AI


Phase 6:

Recruiter Module


Phase 7:

Matching Engine


Phase 8:

Frontend


Phase 9:

Testing


Phase 10:

Deployment



FINAL EXPECTATION:

Create NEXORA AI as a production-level AI career intelligence platform.

The application should not look like a simple college project.

It should feel like a startup-grade product capable of helping millions of students improve their careers and helping companies discover talent efficiently.
