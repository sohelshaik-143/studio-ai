NEXORA AI — Development Environment Setup Document
# NEXORA AI

## Development Environment Setup Document

Version: 1.0  
Status: Developer Onboarding Guide


# 1. Introduction

This document defines the complete development environment required to build NEXORA AI.

The setup includes:

- Frontend environment
- Backend environment
- AI environment
- Database environment
- Cloud tools
- Development utilities



# 2. System Requirements


Recommended developer machine:


## Minimum


CPU:

4 Core Processor


RAM:

16 GB


Storage:

50 GB Free Space


Operating System:

- Windows 11
- Linux
- macOS



## Recommended


CPU:

8 Core Processor


RAM:

32 GB


Storage:

SSD



# 3. Required Software


Install:



Git

Docker

Node.js

Java JDK

Python

PostgreSQL

IDE




# 4. Version Requirements


## Frontend



Node.js 22+

npm / pnpm

Next.js Latest




## Backend



Java 21 LTS

Spring Boot 3.x

Maven




## AI



Python 3.11+

pip

Virtual Environment




## Database



PostgreSQL 16+

Redis Latest




# 5. Git Setup


Install Git:


Verify:


```bash
git --version

Configure:

git config --global user.name "Developer Name"

git config --global user.email "developer@email.com"
6. Frontend Setup

Navigate:

cd nexora-frontend

Install:

npm install

Run:

npm run dev

Expected:

Frontend running

localhost:3000

``` id="r8k3m5"



# 7. Backend Setup


Requirements:



Java 21

Maven



Verify:


```bash
java -version

mvn -version

Run:

mvn spring-boot:run

Expected:

Backend running

localhost:8080

``` id="z5m8p2"



# 8. AI Environment Setup


Navigate:


```bash
cd nexora-ai-engine

Create environment:

python -m venv venv

Activate:

Windows:

venv\Scripts\activate

Linux/macOS:

source venv/bin/activate

Install:

pip install -r requirements.txt

Run AI service:

python main.py

Expected:

AI Service running

localhost:8000

``` id="w6n2m9"



# 9. Database Setup


Install PostgreSQL.


Create database:


```sql
CREATE DATABASE nexora;

Configure:

DATABASE_URL

DATABASE_USERNAME

DATABASE_PASSWORD


Run migrations:

mvn flyway:migrate
10. Redis Setup

Purpose:

Cache
Sessions
AI results

Start Redis:

redis-server
11. Docker Setup

Verify:

docker --version

Start services:

docker-compose up

Services:

Frontend

Backend

Database

Redis

AI Service

``` id="u3p8m5"



# 12. IDE Setup


Recommended:


Backend:



IntelliJ IDEA



Frontend:



VS Code



AI:



VS Code

PyCharm




# 13. Required Extensions


VS Code:



ESLint

Prettier

Tailwind CSS IntelliSense

Python

Docker




IntelliJ:



Spring Boot Plugin

Lombok Plugin

Database Tools




# 14. Environment Variables


Never store secrets in code.


Example:



.env

DATABASE_URL=

JWT_SECRET=

AI_API_KEY=

STORAGE_KEY=




# 15. Local Development Workflow


Daily workflow:



Pull Latest Code

↓

Create Feature Branch

↓

Develop

↓

Run Tests

↓

Commit

↓

Create Pull Request




# 16. Troubleshooting


Common issues:


## Port Already Used


Solution:


Stop existing service.



## Database Connection Error


Check:


- Credentials
- Database status



## Dependency Error


Solution:


Clean install dependencies.



# 17. Developer Onboarding Checklist


Environment:


✅ Git installed

✅ Java installed

✅ Node installed

✅ Python installed

✅ Database configured

✅ Docker working


Project:


✅ Repository cloned

✅ Dependencies installed

✅ Application running



# 18. Final Vision


A standardized development environment allows every engineer to contribute efficiently and keeps NEXORA AI devel
