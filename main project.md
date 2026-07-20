NEXORA-AI/

│
├── README.md
├── LICENSE
├── .gitignore
├── docker-compose.yml
│
├── docs/
│
│   ├── 01_PROJECT_OVERVIEW/
│   │   ├── PROJECT_VISION.md
│   │   ├── BUSINESS_REQUIREMENTS.md
│   │   └── FEATURE_SPECIFICATION.md
│   │
│   ├── 02_SYSTEM_DESIGN/
│   │   ├── SYSTEM_ARCHITECTURE.md
│   │   ├── MODULE_DESIGN.md
│   │   ├── DATA_FLOW.md
│   │   └── SECURITY_ARCHITECTURE.md
│   │
│   ├── 03_DATABASE_DESIGN/
│   │   ├── DATABASE_SCHEMA.md
│   │   ├── ENTITY_RELATIONSHIP.md
│   │   └── MIGRATION_PLAN.md
│   │
│   ├── 04_API_DOCUMENTATION/
│   │   ├── AUTH_API.md
│   │   ├── STUDENT_API.md
│   │   ├── RESUME_API.md
│   │   ├── RECRUITER_API.md
│   │   └── MATCHING_API.md
│   │
│   ├── 05_AI_DESIGN/
│   │   ├── RESUME_AI_ARCHITECTURE.md
│   │   ├── MATCHING_ENGINE_DESIGN.md
│   │   └── AI_PIPELINE.md
│   │
│   ├── 06_UI_UX_DESIGN/
│   │   ├── DESIGN_SYSTEM.md
│   │   ├── USER_FLOWS.md
│   │   └── SCREEN_DESIGN.md
│   │
│   ├── 07_DEVELOPMENT/
│   │   ├── CODING_STANDARDS.md
│   │   ├── GIT_WORKFLOW.md
│   │   └── DEVELOPMENT_GUIDE.md
│   │
│   ├── 08_TESTING/
│   │   ├── TESTING_STRATEGY.md
│   │   └── TEST_CASES.md
│   │
│   └── 09_DEPLOYMENT/
│       ├── DEPLOYMENT_ARCHITECTURE.md
│       ├── CLOUD_SETUP.md
│       └── PRODUCTION_CHECKLIST.md
│
│
├── backend/
│
│   ├── pom.xml
│   └── src/
│       │
│       ├── main/
│       │
│       │   ├── java/com/nexora/
│       │   │
│       │   ├── auth/
│       │   │   ├── controller
│       │   │   ├── service
│       │   │   ├── repository
│       │   │   ├── entity
│       │   │   └── dto
│       │   │
│       │   ├── student/
│       │   │
│       │   ├── recruiter/
│       │   │
│       │   ├── company/
│       │   │
│       │   ├── resume/
│       │   │
│       │   ├── matching/
│       │   │
│       │   ├── dashboard/
│       │   │
│       │   ├── security/
│       │   │
│       │   ├── config/
│       │   │
│       │   ├── exception/
│       │   │
│       │   ├── common/
│       │   │
│       │   └── NexoraApplication.java
│       │
│       └── resources/
│           │
│           ├── application.yml
│           ├── application-dev.yml
│           ├── application-prod.yml
│           │
│           └── db/
│               └── migration/
│
│
├── frontend/
│
│   ├── src/
│   │
│   ├── components/
│   ├── pages/
│   ├── layouts/
│   ├── routes/
│   ├── hooks/
│   ├── context/
│   ├── services/
│   └── utils/
│
│
├── ai-engine/
│
│   ├── resume-parser/
│   ├── skill-extraction/
│   ├── matching-model/
│   └── recommendation-engine/
│
│
├── storage/
│
│   └── resumes/
│
│
├── tests/
│
│   ├── backend-tests/
│   ├── frontend-tests/
│   └── integration-tests/
│
│
└── deployment/

    ├── docker/
    ├── nginx/
    ├── cloud/
    └── monitoring/
