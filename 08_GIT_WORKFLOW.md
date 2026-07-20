# NEXORA AI

# Git Workflow

**Version:** 1.0
**Status:** Approved

---

# Document Information

| Property | Value |
|----------|--------|
| Document Name | Git Workflow |
| Project | NEXORA AI |
| Version | 1.0 |
| Owner | NEXORA Development Team |
| Status | Approved |
| Last Updated | July 2026 |

---

# Revision History

| Version | Date | Author | Description |
|----------|------|---------|-------------|
| 1.0 | July 2026 | NEXORA Development Team | Initial Git Workflow Standard |

---

# Table of Contents

1. Purpose
2. Workflow Philosophy
3. Branch Strategy
4. Branch Naming Convention
5. Commit Standards
6. Pull Request Standards
7. Code Review Guidelines
8. Merge Strategy
9. Release Management
10. Versioning
11. Repository Rules
12. Git Ignore Policy
13. Backup Strategy
14. Best Practices
15. Review Checklist
16. Definition of Done

---

# 1. Purpose

This document defines the Git workflow and repository management standards for the NEXORA AI project.

The objective is to maintain a clean Git history, simplify collaboration, and ensure high-quality releases.

---

# 2. Workflow Philosophy

The project follows these principles:

- Small and focused commits
- Meaningful commit messages
- Feature-based development
- Frequent synchronization
- Reviewed code before merging
- Stable main branch

The `main` branch should always remain deployable.

---

# 3. Branch Strategy

Primary branches

```
main
develop
```

Supporting branches

```
feature/*
bugfix/*
hotfix/*
release/*
docs/*
refactor/*
test/*
```

Example

```
feature/authentication

feature/student-module

feature/resume-ai

bugfix/login-error

docs/api-standard

release/v1.0.0
```

---

# 4. Branch Naming Convention

Use lowercase letters and hyphens.

Examples

```
feature/student-profile

feature/recruiter-dashboard

feature/job-matching

bugfix/jwt-expiration

hotfix/security-patch

docs/database-standard
```

Avoid:

```
Feature1

MyBranch

NewCode
```

---

# 5. Commit Standards

Follow the Conventional Commits specification.

### Features

```
feat(auth): implement JWT authentication
```

### Bug Fixes

```
fix(student): resolve profile update issue
```

### Documentation

```
docs(api): add pagination guidelines
```

### Refactoring

```
refactor(resume): simplify parsing service
```

### Performance

```
perf(database): optimize candidate search query
```

### Tests

```
test(auth): add login integration tests
```

### Build

```
build: update Maven dependencies
```

### Chore

```
chore: update project configuration
```

---

# 6. Pull Request Standards

Each Pull Request should include:

- Clear title
- Summary of changes
- Linked issue (if applicable)
- Testing evidence
- Updated documentation
- Screenshots (for UI changes)

Keep Pull Requests focused on a single feature or fix.

---

# 7. Code Review Guidelines

Reviewers should verify:

- Code quality
- Readability
- Naming conventions
- Security considerations
- Performance impact
- Test coverage
- Documentation updates

Constructive feedback should be provided where improvements are needed.

---

# 8. Merge Strategy

Preferred merge method

```
Squash and Merge
```

Benefits

- Cleaner commit history
- Easier release tracking
- Reduced noise in the main branch

Merge only after successful review and testing.

---

# 9. Release Management

Release branches

```
release/v1.0.0

release/v1.1.0

release/v2.0.0
```

Release process

1. Create release branch.
2. Complete testing.
3. Fix release issues.
4. Merge into `main`.
5. Tag the release.
6. Merge back into `develop`.

---

# 10. Versioning

Follow Semantic Versioning.

```
MAJOR.MINOR.PATCH
```

Examples

```
1.0.0

1.1.0

1.1.1

2.0.0
```

Rules

- MAJOR → Breaking changes
- MINOR → New features
- PATCH → Bug fixes

---

# 11. Repository Rules

The repository should contain:

```
README.md

LICENSE

CONTRIBUTING.md

CODE_OF_CONDUCT.md

CHANGELOG.md

SECURITY.md
```

Use branch protection on `main`.

Require successful CI checks before merging.

---

# 12. Git Ignore Policy

Ignore generated files and sensitive information.

Examples

```
target/

.idea/

.vscode/

*.log

.env

application-prod.yml

*.class
```

Do not commit secrets, credentials, or generated binaries.

---

# 13. Backup Strategy

Repository backups should include:

- GitHub remote repository
- Local developer clones
- Release tags
- Database migration scripts
- Documentation

Critical releases should be tagged before deployment.

---

# 14. Best Practices

- Commit frequently with meaningful messages.
- Rebase feature branches when appropriate.
- Resolve conflicts before opening Pull Requests.
- Keep branches up to date with `develop`.
- Delete merged branches to keep the repository clean.

---

# 15. Review Checklist

Before merging:

- Branch naming follows standards.
- Commit messages follow conventions.
- Code review approved.
- Tests passed.
- Documentation updated.
- CI pipeline successful.

---

# 16. Definition of Done

Git workflow is correctly followed when:

- Branch strategy is respected.
- Commit messages are meaningful.
- Pull Requests are reviewed.
- Releases are versioned.
- Repository history remains clean and traceable.

---

# References

- PROJECT_VISION.md
- DOCUMENTATION_STANDARD.md
- CODING_STANDARD.md
- SECURITY_STANDARD.md

---

# Next Document

Continue with:

**09_PROJECT_GLOSSARY.md**

This document defines the terminology, abbreviations, and business concepts used throughout the NEXORA AI platform to ensure a common understanding among all contributors.
