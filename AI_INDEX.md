# InsuranceNext AI Index

> Master Navigation and Knowledge Index for the InsuranceNext Repository

**Version:** 1.0  
**Status:** Active  
**Last Updated:** 2026-07-26

---

# Purpose

This document is the primary entry point into the InsuranceNext repository.

It serves four purposes:

1. Guide engineers through the documentation.
2. Guide AI assistants through the documentation.
3. Define the authoritative source for every major topic.
4. Prevent duplicate or conflicting documentation.

Every contributor should begin here before navigating the repository.

---

# Repository Philosophy

InsuranceNext follows a **Documentation as Code** philosophy.

Documentation is considered part of the product and is maintained alongside the source code.

The repository is organized so that every major concept has exactly one authoritative document.

If information appears to exist in multiple places, this index identifies the canonical source.

---

# Reading Order

New contributors should read the documentation in the following order.

## Phase 1 – Foundation

```
README.md
AI_INDEX.md
```

---

## Phase 2 – Vision

```
docs/
    01-Vision/
```

Read in the following order:

1. Vision.md
2. Product-Principles.md
3. Business-Goals.md
4. Roadmap.md

Purpose:

Understand **why** the platform exists before understanding **how** it is built.

---

## Phase 3 – Domain Model

```
docs/
    02-Domain-Model/
```

Read in the following order:

1. Organization.md
2. Workspace.md
3. User.md
4. Investigation.md
5. Evidence.md
6. Relationship.md
7. Insight.md
8. Collection.md

Purpose:

Understand the business language used throughout the system.

Every service, API and database entity is built from this domain model.

---

## Phase 4 – Architecture

```
docs/
    03-Architecture/
```

Read in the following order:

1. System-Architecture.md
2. Service-Architecture.md
3. Data-Architecture.md
4. Event-Architecture.md
5. Security-Architecture.md

Purpose:

Understand how the platform is structured.

---

## Phase 5 – Services

```
docs/
    04-Services/
```

Each document describes a single bounded context or microservice.

Examples:

- Identity Service
- Workspace Service
- Investigation Service
- Evidence Service
- Relationship Service
- Insight Service
- Search Service
- Graph Service
- AI Service
- Notification Service

---

## Phase 6 – APIs

```
docs/
    05-API/
```

Read:

- API Standards
- Authentication
- REST Endpoints
- Event Contracts
- Webhooks

---

## Phase 7 – Backend

```
docs/
    06-Backend/
```

Topics include:

- Persistence
- Repository Pattern
- CQRS
- Event Bus
- Caching
- Background Jobs

---

## Phase 8 – Frontend

```
docs/
    07-Frontend/
```

Topics include:

- UI Architecture
- Component Library
- Navigation
- State Management
- Dashboard Framework

---

## Phase 9 – Workflows

```
docs/
    08-Workflows/
```

Business processes implemented by the platform.

Examples:

- Create Investigation
- Add Evidence
- Generate Insight
- Relationship Analysis
- AI Investigation Assistant

---

## Phase 10 – Permissions

```
docs/
    09-Permissions/
```

Role definitions and authorization model.

---

## Phase 11 – Architecture Decision Records

```
docs/
    10-ADR/
```

Contains all significant technical decisions.

Every major architectural change should result in a new ADR.

---

## Phase 12 – Operations

```
docs/
    11-Operations/
```

Topics include:

- Logging
- Monitoring
- Metrics
- Alerting
- Backup
- Disaster Recovery

---

## Phase 13 – Deployment

```
docs/
    12-Deployment/
```

Infrastructure and deployment documentation.

---

## Phase 14 – Testing

```
docs/
    13-Testing/
```

Testing strategy and quality standards.

---

## Phase 15 – Product

```
docs/
    14-Product/
```

Product management artifacts.

---

## Phase 16 – Future

```
docs/
    15-Future/
```

Research ideas and long-term roadmap.

---

# Documentation Rules

Every document should:

- Have a single responsibility.
- Be self-contained.
- Avoid duplication.
- Reference related documents.
- Use consistent terminology.
- Be written in Markdown.

---

# Naming Standards

Document names should:

- Use PascalCase.
- Be descriptive.
- Represent a single concept.

Examples:

```
Evidence.md
Service-Architecture.md
Graph-Service.md
User-Permissions.md
```

Avoid filenames such as:

```
Architecture-New.md
Architecture-v2.md
Final-Version.md
Latest.md
Notes.md
```

The Git history preserves evolution; filenames should remain stable.

---

# Canonical Sources

| Topic | Authoritative Document |
|---------|-----------------------|
| Product Vision | `docs/01-Vision/Vision.md` |
| Business Goals | `docs/01-Vision/Business-Goals.md` |
| Roadmap | `docs/01-Vision/Roadmap.md` |
| Domain Objects | `docs/02-Domain-Model/` |
| Architecture | `docs/03-Architecture/` |
| Services | `docs/04-Services/` |
| APIs | `docs/05-API/` |
| Backend | `docs/06-Backend/` |
| Frontend | `docs/07-Frontend/` |
| Workflows | `docs/08-Workflows/` |
| Permissions | `docs/09-Permissions/` |
| ADRs | `docs/10-ADR/` |
| Operations | `docs/11-Operations/` |
| Deployment | `docs/12-Deployment/` |
| Testing | `docs/13-Testing/` |

---

# AI Assistant Instructions

When assisting with InsuranceNext:

1. Treat this repository as the source of truth.
2. Read documents in the order defined above.
3. Do not invent new terminology if an existing term exists.
4. Preserve architectural consistency.
5. Prefer extending existing documentation over creating new files.
6. Record significant architectural changes through ADRs.
7. Ensure documentation and implementation remain synchronized.

---

# Repository Evolution

The documentation is expected to evolve.

However:

- Existing filenames should remain stable.
- Major architectural changes should be documented through ADRs.
- Deprecated documents should be archived rather than overwritten.
- AI_INDEX.md should always reflect the current repository structure.

---

# Current Documentation Status

| Section | Status |
|----------|--------|
| Foundation | In Progress |
| Vision | Pending |
| Domain Model | Pending |
| Architecture | Pending |
| Services | Pending |
| APIs | Pending |
| Backend | Pending |
| Frontend | Pending |
| Workflows | Pending |
| Permissions | Pending |
| Operations | Pending |
| Deployment | Pending |
| Testing | Pending |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-26 | Initial repository index created. |
