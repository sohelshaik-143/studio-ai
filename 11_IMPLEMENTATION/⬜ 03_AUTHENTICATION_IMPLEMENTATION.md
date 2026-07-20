# NEXORA AI

# Authentication Implementation

Version: 1.0  
Status: Ready for Development

---

# 1. Objective

Implement secure authentication using Spring Security and JWT.

Features:

- User Registration
- User Login
- JWT Authentication
- Role Management
- Refresh Token
- Protected APIs

---

# 2. Authentication Flow

```
User

↓

Register / Login Request

↓

AuthController

↓

AuthService

↓

UserRepository

↓

JWT Generation

↓

Client Receives Token

↓

Access Protected APIs
```

---

# 3. Package Structure

```
com.nexora

├── auth
│
│   ├── controller
│   │
│   ├── service
│   │
│   ├── repository
│   │
│   ├── entity
│   │
│   └── dto
│
└── security

    ├── SecurityConfig
    ├── JwtService
    ├── JwtFilter
    └── UserPrincipal
```

---

# 4. Database Design

## users

```
id

first_name

last_name

email

password

phone

enabled

created_at

updated_at
```

---

## roles

```
id

name
```

Roles:

```
ROLE_STUDENT

ROLE_RECRUITER

ROLE_COLLEGE

ROLE_ADMIN
```

---

## refresh_tokens

```
id

token

expiry_date

user_id
```

---

# 5. Entity Design

## User

Responsibilities:

- Store user credentials
- Maintain user roles
- Manage account status


## Role

Responsibilities:

- Define permissions
- Support role-based access


---

# 6. DTO Design

## RegisterRequest

Fields:

```
firstName

lastName

email

password

role
```

---

## LoginRequest

Fields:

```
email

password
```

---

## AuthResponse

Fields:

```
accessToken

refreshToken

message
```

---

# 7. Repository Layer

Create:

```
UserRepository

RoleRepository

RefreshTokenRepository
```

Responsibilities:

- Database operations
- User lookup
- Token management

---

# 8. Service Layer

## AuthService

Methods:

```
register()

login()

refreshToken()

logout()
```

---

## Authentication Logic

Register:

```
Validate Input

↓

Check Existing Email

↓

Encrypt Password

↓

Save User

↓

Assign Role

↓

Return Response
```

---

Login:

```
Find User

↓

Verify Password

↓

Generate JWT

↓

Generate Refresh Token

↓

Return Tokens
```

---

# 9. Security Configuration

Configure:

- Spring Security Filter Chain
- JWT Authentication Filter
- Password Encoder
- Session Management


Rules:

```
Session = Stateless

Password = BCrypt

Authentication = JWT
```

---

# 10. API Endpoints

## Register

```
POST /api/v1/auth/register
```

---

## Login

```
POST /api/v1/auth/login
```

---

## Refresh Token

```
POST /api/v1/auth/refresh
```

---

## Logout

```
POST /api/v1/auth/logout
```

---

# 11. Validation Rules

Email:

```
Required

Unique

Valid Format
```

Password:

```
Minimum 8 characters
```

Role:

```
Must be valid role
```

---

# 12. Security Rules

- Password never stored as plain text.
- JWT secret stored in environment variables.
- Protected APIs require valid token.
- Unauthorized requests return proper error response.

---

# 13. Implementation Order

Step 1

Create User and Role entities.

Step 2

Create repositories.

Step 3

Create DTO classes.

Step 4

Implement password encryption.

Step 5

Implement JWT service.

Step 6

Configure Spring Security.

Step 7

Implement authentication APIs.

Step 8

Test using Postman.

---

# 14. Definition of Done

Completed:

- User registration works.
- Login generates JWT.
- Refresh token works.
- Logout works.
- Protected APIs secured.
- Role authorization verified.

---

# Next Step

Create Authentication Java Classes
