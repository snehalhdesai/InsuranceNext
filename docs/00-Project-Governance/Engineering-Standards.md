# Engineering Standards

> Engineering, documentation, architecture, and repository standards for InsuranceNext.

**Version:** 1.0  
**Status:** Active  
**Owner:** Architecture Team

---

# Purpose

This document defines the engineering standards for the InsuranceNext platform.

These standards apply to:

- Documentation
- Source Code
- APIs
- Services
- Infrastructure
- Database Design
- Git Workflow
- AI-generated contributions

Every contributor is expected to follow these standards.

---

# Engineering Principles

InsuranceNext is built around the following principles:

- Domain Driven Design (DDD)
- API First
- AI Native
- Cloud Native
- Security by Design
- Documentation as Code
- Infrastructure as Code
- Event Driven Architecture
- Clean Architecture
- Automation First

Whenever multiple implementation approaches are possible, preference should be given to the one that best aligns with these principles.

---

# Documentation Standards

Documentation is considered production code.

Every document should:

- Have a single responsibility.
- Define one primary concept.
- Be written in Markdown.
- Be version controlled.
- Be reviewed when architecture changes.
- Reference related documentation instead of duplicating content.

---

# Document Structure

Each document should follow the same structure where applicable:

1. Title
2. Purpose
3. Scope
4. Description
5. Related Concepts
6. References
7. Revision History

Not every document requires every section, but consistency should be maintained.

---

# Naming Standards

## Documents

Use PascalCase.

Examples:

```
Evidence.md
Relationship.md
System-Architecture.md
```

---

## Services

```
EvidenceService
WorkspaceService
InvestigationService
```

---

## APIs

REST endpoints use kebab-case.

```
/api/investigations
/api/evidence
/api/workspaces
```

---

## Events

Past-tense PascalCase.

```
InvestigationCreated
EvidenceUploaded
InsightGenerated
RelationshipDeleted
```

---

## Database

Tables

```
snake_case
```

Examples

```
users
organizations
evidence_items
investigation_events
```

Columns

```
created_at
updated_at
workspace_id
```

---

## Environment Variables

```
DATABASE_URL

JWT_SECRET

SUPABASE_URL
```

---

# Source Code Standards

General principles:

- Readability over cleverness.
- Small focused functions.
- Explicit naming.
- Prefer composition over inheritance.
- Avoid duplicated logic.
- Strong typing where supported.
- Minimize global state.
- Fail fast when errors occur.

---

# Repository Standards

The repository should remain organized.

High-level structure:

```
README.md
AI_INDEX.md

docs/
src/
tests/
database/
scripts/
assets/
diagrams/
infrastructure/
```

Documentation belongs under `docs`.

Executable code belongs under `src`.

Infrastructure definitions belong under `infrastructure`.

---

# Git Standards

Branch naming:

```
feature/<feature-name>

bugfix/<bug-name>

hotfix/<issue>

release/<version>
```

Examples:

```
feature/evidence-service

feature/graph-search

bugfix/login-timeout
```

Commit messages should be concise and written in the imperative mood.

Examples:

```
Add Evidence domain model

Implement Workspace service

Refactor authentication middleware

Update API documentation
```

Avoid vague commit messages such as:

```
Update

Changes

Fix

Latest

Final
```

---

# Documentation Workflow

For every significant feature:

1. Update documentation.
2. Update architecture if required.
3. Implement code.
4. Add tests.
5. Review changes.
6. Commit.
7. Push to GitHub.

Documentation should evolve with the implementation.

---

# API Standards

APIs should:

- Be RESTful where appropriate.
- Use nouns rather than verbs.
- Return consistent response structures.
- Support pagination for collections.
- Return meaningful error messages.
- Be versioned when introducing breaking changes.

---

# Security Standards

Security is mandatory.

All services should:

- Authenticate users.
- Authorize every request.
- Encrypt sensitive data.
- Log security-relevant events.
- Validate all inputs.
- Avoid exposing internal implementation details.

---

# AI Contribution Standards

AI-generated content must:

- Follow existing terminology.
- Preserve architectural consistency.
- Avoid introducing duplicate concepts.
- Update documentation when making architectural changes.
- Never invent business terminology that conflicts with the glossary.

---

# Change Management

Major technical decisions should be documented as Architecture Decision Records (ADRs).

Examples:

- Technology selection
- Database strategy
- Event model
- Authentication model
- Search architecture
- AI architecture

---

# Quality Checklist

Before merging work, verify that:

- Documentation is updated.
- Tests pass.
- Naming follows standards.
- No duplicate documentation exists.
- Architecture remains consistent.
- APIs remain backward compatible where required.

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-26 | Initial engineering standards established. |