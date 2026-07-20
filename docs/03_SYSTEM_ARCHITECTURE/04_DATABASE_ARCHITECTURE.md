# NEXORA AI

## Database Architecture Document

Version: 1.0  
Status: System Architecture Foundation


# 1. Introduction

The database architecture defines how NEXORA AI stores, manages, and processes platform data.

The system requires different storage approaches because it handles:

- User information
- Career profiles
- Job data
- AI-generated insights
- Documents
- Analytics


NEXORA AI follows a polyglot data architecture approach.

Meaning:

Different types of data use different storage solutions.


# 2. Database Architecture Overview

                NEXORA AI DATA LAYER


                      |

    --------------------------------------

    Relational Database

    PostgreSQL


    Cache Database

    Redis


    AI Vector Database

    Vector Store


    Object Storage

    File Storage


    Analytics Storage

    Data Warehouse


    --------------------------------------
    
# 3. Primary Database — PostgreSQL


## Purpose

Stores structured business data.


Used for:


- Users
- Profiles
- Companies
- Jobs
- Applications
- Permissions


Reason:


PostgreSQL provides:

- Strong consistency
- Complex relationships
- Transaction support
- Scalability



# 4. Database Ownership Strategy


Each microservice owns its database.


Architecture:
Auth Service

                          |

                    Auth Database
Auth Service

                          |

                      Auth Database

Student Service

                            |

                      Student Database

Job Service

                            |
      
                        Job Database
                        
Benefits:

- Data isolation
- Independent scaling
- Better security



# 5. Core Database Entities


# 5.1 User Management Domain


## users


Purpose:

Stores all platform users.


Fields:


- user_id
- name
- email
- password_hash
- role
- created_at
- updated_at



Roles:


- Student
- Recruiter
- College Admin
- Platform Admin



---

## roles


Stores permission definitions.


Fields:


- role_id
- role_name
- permissions



# 5.2 Student Domain


## student_profiles


Purpose:

Stores student career identity.


Fields:


- student_id
- user_id
- college_id
- degree
- branch
- graduation_year
- location



---

## skills


Stores technical abilities.


Fields:


- skill_id
- skill_name
- category



---

## student_skills


Maps students with skills.


Fields:


- student_id
- skill_id
- proficiency_level
- verified_score



---

## projects


Stores student projects.


Fields:


- project_id
- student_id
- title
- description
- technologies
- github_url



# 5.3 Resume Domain


## resumes


Stores uploaded resumes.


Fields:


- resume_id
- student_id
- file_url
- uploaded_date
- analysis_status



---

## resume_analysis


Stores AI results.


Fields:


- analysis_id
- resume_id
- extracted_skills
- resume_score
- suggestions



# 5.4 Recruiter Domain


## companies


Stores company information.


Fields:


- company_id
- name
- industry
- website
- description



---

## recruiters


Stores recruiter accounts.


Fields:


- recruiter_id
- company_id
- user_id



# 5.5 Job Domain


## jobs


Stores job opportunities.


Fields:


- job_id
- company_id
- title
- description
- location
- salary_range
- status



---

## job_skills


Stores required skills.


Fields:


- job_id
- skill_id
- importance



# 5.6 Application Domain


## applications


Stores job applications.


Fields:


- application_id
- student_id
- job_id
- status
- applied_date



Statuses:


- Applied
- Reviewed
- Shortlisted
- Interview
- Selected
- Rejected



# 6. AI Data Architecture


AI requires additional storage systems.


# 6.1 Vector Database


Purpose:

Stores AI embeddings.


Used for:


- Resume similarity
- Candidate matching
- Semantic search
- Skill relationships



Example:


Student Profile Vector

+

Job Requirement Vector


=

Similarity Score



# 6.2 AI Knowledge Store


Stores:


- Skill relationships
- Career paths
- Industry requirements
- Learning resources



# 7. Redis Cache Architecture


Purpose:

Improve performance.


Used for:


- User sessions
- Frequently searched jobs
- AI results caching
- Temporary data



Example:


Popular Jobs Query

↓

Redis Cache

↓

Fast Response



# 8. File Storage Architecture


Object storage manages:


- Resumes
- Certificates
- Images
- Documents


Flow:


User Upload

↓

File Service

↓

Secure Storage

↓

Database Reference



# 9. Analytics Data Architecture


Analytics system stores:


- User activity
- Skill growth
- Placement statistics
- AI performance metrics



Used by:


- College Dashboard
- Recruiter Dashboard
- Admin Dashboard



# 10. Data Security Strategy


Database security includes:


## Encryption

Protect sensitive information.


## Access Control

Users only access authorized data.


## Backup

Regular backups prevent data loss.


## Audit Logs

Track important activities.



# 11. Data Flow Example


Student uploads resume:

       Resume File

          |

      File Service
  
          |

      Object Storage

          |

      Resume Database

        |

      AI Analysis Service

          |

      AI Results Database

          |

      Student Dashboard
      

# 12. Database Scaling Strategy


## Horizontal Scaling


Add more database instances.


## Read Replicas


Improve read performance.


## Partitioning


Split large datasets.


## Indexing


Optimize search operations.



# 13. Future Data Expansion


Future databases may include:


- Global Talent Graph
- AI Career Knowledge Graph
- Company Intelligence Database
- Skill Evolution Database



# 14. Final Database Vision


NEXORA AI database architecture is designed to store not only information but intelligence.

Data becomes:

Information

↓

Knowledge

↓

Career Intelligence

