# NEXORA AI

## User Roles and Permissions Document

Version: 1.0  
Status: Business Requirements Foundation


# 1. Introduction

User roles and permissions define how different users interact with the NEXORA AI platform.

The purpose of this system is to:

- Provide secure access
- Protect user data
- Maintain platform integrity
- Ensure users only access relevant features


NEXORA AI follows a Role-Based Access Control (RBAC) approach.


# 2. Role Hierarchy


                    NEXORA AI PLATFORM

                           |
                    Platform Admin

                           |
        -----------------------------------------
        |                    |                  |
     College             Recruiter           Student


Each role has specific responsibilities and access levels.


# 3. Role 01 — Student


## Role Description

Students are the primary users who build their AI career profile and discover opportunities.


## Main Objectives

- Create digital identity
- Improve skills
- Find opportunities
- Track career growth


## Student Permissions


### Profile Management

Allowed:

✅ Create profile  
✅ Update personal information  
✅ Add education details  
✅ Upload profile image  


### Resume Management

Allowed:

✅ Upload resume  
✅ Update resume  
✅ Delete resume  
✅ View AI resume analysis  


### Skill Management

Allowed:

✅ Add skills  
✅ View skill analysis  
✅ Receive skill recommendations  
✅ Track skill progress  


### External Integration

Allowed:

✅ Connect GitHub  
✅ Connect coding platforms  
✅ Add portfolio links  


### Career Features

Allowed:

✅ Generate roadmap  
✅ View recommended jobs  
✅ Apply for opportunities  
✅ Track applications  


### Restricted Access

Students cannot:

❌ View other student private data  
❌ Access recruiter dashboards  
❌ Modify college data  
❌ Access system settings



# 4. Role 02 — Recruiter


## Role Description

Recruiters represent companies searching for skilled candidates.


## Main Objectives

- Discover talent
- Create job opportunities
- Evaluate candidates


## Recruiter Permissions


### Company Management

Allowed:

✅ Create company profile  
✅ Update company information  
✅ Manage recruiter profile  


### Job Management

Allowed:

✅ Create job postings  
✅ Edit job requirements  
✅ Close job postings  
✅ View applications  


### Candidate Discovery

Allowed:

✅ Search candidates  
✅ Filter candidates  
✅ View AI matching results  
✅ Shortlist candidates  


### Candidate Evaluation

Allowed:

✅ View candidate skill profile  
✅ Review projects  
✅ View assessment results  


### Restricted Access

Recruiters cannot:

❌ View private student information without permission  
❌ Access college administration data  
❌ Modify AI algorithms  
❌ Access platform settings



# 5. Role 03 — College Administrator


## Role Description

College administrators manage students and placement activities.


## Main Objectives

- Monitor student growth
- Improve placement outcomes
- Manage college ecosystem


## College Permissions


### Student Management

Allowed:

✅ Add students  
✅ Import student data  
✅ View student analytics  
✅ Track student progress  


### Placement Management

Allowed:

✅ Manage placement drives  
✅ Connect recruiters  
✅ Track applications  
✅ View placement reports  


### Analytics

Allowed:

✅ View department analytics  
✅ View skill gap reports  
✅ Generate reports  


### Restricted Access

College admins cannot:

❌ Access another college data  
❌ Modify recruiter data  
❌ Change AI models  
❌ Access system administration



# 6. Role 04 — Platform Administrator


## Role Description

Platform administrators maintain the entire NEXORA AI ecosystem.


## Main Objectives

- System control
- Security management
- Platform monitoring


## Admin Permissions


### User Management

Allowed:

✅ Create users  
✅ Suspend accounts  
✅ Manage roles  
✅ Verify organizations  


### Platform Management

Allowed:

✅ Configure system settings  
✅ Monitor services  
✅ Manage integrations  


### AI Management

Allowed:

✅ Monitor AI performance  
✅ Manage AI configurations  
✅ Review AI analytics  


### Security Management

Allowed:

✅ Monitor security events  
✅ Manage access policies  
✅ Audit activities  


# 7. Permission Levels


## Level 1 — Public Access

Examples:

- Landing page
- Public information
- Company profiles


## Level 2 — User Access

Examples:

- Student profile
- Recruiter profile
- College dashboard


## Level 3 — Organization Access

Examples:

- Company data
- College data
- Team management


## Level 4 — System Access

Examples:

- AI configuration
- Platform settings
- Security controls



# 8. Data Privacy Rules


## Student Data

Controlled by:

- Student ownership
- Permission-based sharing


## Recruiter Data

Controlled by:

- Company ownership


## College Data

Controlled by:

- Institution ownership


## Platform Data

Controlled by:

- Admin access



# 9. Authentication Requirements


NEXORA AI should support:


## Login Methods

- Email authentication
- Password authentication
- OAuth integration
- Organization verification


## Security Features

- JWT authentication
- Role verification
- Session management
- Access logging



# 10. Authorization Principle


Every request in NEXORA AI must pass:


User Identity

↓

Role Verification

↓

Permission Check

↓

Resource Access



# 11. Final Role Model


| Role | Primary Responsibility |
|------|------------------------|
| Student | Build skills and find opportunities |
| Recruiter | Discover and hire talent |
| College Admin | Manage student ecosystem |
| Platform Admin | Control and secure platform |


# Conclusion

The NEXORA AI permission system ensures:

- Security
- Privacy
- Scalability
- Clear responsibility boundaries

This RBAC foundation will later support authentication architecture and backend security design.
