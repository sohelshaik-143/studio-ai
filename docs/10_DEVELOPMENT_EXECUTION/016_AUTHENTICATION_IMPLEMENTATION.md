# NEXORA AI

# Authentication Implementation

Version: 1.0
Status: Ready for Implementation

---

# 1. Objective

Build a secure authentication system using Spring Security and JWT.

Features:

- User Registration
- User Login
- JWT Authentication
- Refresh Token
- Role-Based Access Control (RBAC)
- Logout

---

# 2. Scope

Included

- Student Registration
- Recruiter Registration
- College Registration
- Admin Login
- JWT Access Token
- Refresh Token
- Password Encryption
- Role Management

Excluded

- Social Login
- OTP Verification
- MFA
- Forgot Password

---

# 3. Architecture

```
Client
    │
    ▼
AuthController
    │
    ▼
AuthService
    │
    ▼
UserRepository
    │
    ▼
PostgreSQL
```

Spring Security protects all secured APIs.

---

# 4. Package Structure

```
auth/

controller/

service/

service/impl/

repository/

entity/

dto/

mapper/

security/

config/
```

---

# 5. Database Design

## Tables

```
users

roles

refresh_tokens
```

---

### users

```
id

first_name

last_name

email

password

phone

is_active

created_at

updated_at
```

---

### roles

```
id

name
```

Default Roles

```
ROLE_STUDENT

ROLE_RECRUITER

ROLE_COLLEGE

ROLE_ADMIN
```

---

### refresh_tokens

```
id

token

expiry_date

user_id
```

---

# 6. API Endpoints

```
POST /api/v1/auth/register

POST /api/v1/auth/login

POST /api/v1/auth/refresh

POST /api/v1/auth/logout

GET /api/v1/auth/profile
```

---

# 7. Business Rules

- Email must be unique.
- Password must be encrypted using BCrypt.
- Every user has at least one role.
- Access Token expires after 15 minutes.
- Refresh Token expires after 7 days.
- Inactive users cannot log in.

---

# 8. Security

- Spring Security
- JWT Authentication
- BCrypt Password Encoder
- Stateless Sessions
- Role-Based Authorization
- CORS Configuration
- Input Validation

---

# 9. Implementation Steps

Step 1

Create entities

- User
- Role
- RefreshToken

Step 2

Create repositories.

Step 3

Create DTOs.

Step 4

Implement JWT service.

Step 5

Configure Spring Security.

Step 6

Implement AuthService.

Step 7

Implement AuthController.

Step 8

Test all authentication APIs.

---

# 10. Definition of Done

- Registration works.
- Login works.
- JWT generated successfully.
- Refresh Token works.
- Logout invalidates refresh token.
- Protected APIs require authentication.
- Role-based authorization verified.

---

# Next Module

07_STUDENT_IMPLEMENTATION.md
