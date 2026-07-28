# Domain Overview

> The canonical business domain model for the InsuranceNext platform.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

This document defines the InsuranceNext Domain Model.

It establishes the business language used throughout the platform and provides the conceptual foundation for every service, API, workflow, database schema, event, permission, and AI capability.

The Domain Model is the authoritative representation of how InsuranceNext understands the insurance intelligence domain.

---

# Scope

This document defines:

- Core business concepts
- Domain boundaries
- Business entities
- Aggregate ownership
- Relationships between concepts
- Domain principles
- Domain lifecycle

Implementation details such as database schemas, REST APIs, message contracts, and UI design are intentionally excluded.

---

# Domain Philosophy

InsuranceNext is built using Domain-Driven Design (DDD).

The platform is organised around business capabilities rather than technical components.

The business domain defines the software—not the other way around.

Every architectural decision should preserve the integrity of the domain model.

---

# What is the InsuranceNext Domain?

InsuranceNext operates within the Insurance Intelligence domain.

Its primary purpose is to help insurance organisations transform fragmented information into trusted intelligence that supports operational decision-making.

Unlike traditional claims or policy systems, InsuranceNext focuses on understanding information rather than managing transactions.

---

# Domain Objectives

The domain model is designed to support the following business objectives.

- Organise investigative information.
- Connect related business entities.
- Preserve evidence integrity.
- Generate actionable insights.
- Support collaborative investigations.
- Enable explainable AI.
- Maintain complete auditability.
- Build reusable organisational knowledge.

---

# Core Domain Concepts

InsuranceNext is built around eight primary domain objects.

| Domain Object | Purpose |
|---------------|---------|
| Organization | Owns the platform environment. |
| Workspace | Logical business context. |
| User | Authenticated participant. |
| Investigation | Primary investigative unit of work. |
| Evidence | Information collected during investigations. |
| Relationship | Connection between domain entities. |
| Insight | Knowledge derived from evidence. |
| Collection | Curated grouping of related resources. |

These concepts form the canonical business vocabulary of the platform.

---

# Domain Hierarchy

The business hierarchy is intentionally simple.

```
Organization

└── Workspace

      ├── Users

      ├── Investigations

      │      ├── Evidence

      │      ├── Relationships

      │      ├── Insights

      │      └── Collections

      └── Shared Resources
```

Ownership always flows downward.

---

# Domain Relationships

The following diagram illustrates the conceptual relationships between major domain objects.

```
Organization
      │
      ▼
Workspace
      │
      ├──────────────┐
      ▼              ▼
User        Investigation
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
Evidence   Relationship    Insight
        │            │            │
        └────────────┴────────────┘
                     │
               Collection
```

This represents conceptual ownership rather than implementation dependencies.

---

# Aggregate Boundaries

InsuranceNext follows Aggregate principles from Domain-Driven Design.

Primary Aggregates include:

- Organization
- Workspace
- Investigation

Secondary domain objects belong to one of these aggregates.

For example:

Evidence belongs to an Investigation.

Investigations belong to a Workspace.

Workspaces belong to an Organization.

Aggregates define transactional consistency and ownership.

---

# Domain Entity Types

The domain consists of several categories of business objects.

## Aggregates

Objects responsible for consistency.

Examples:

- Organization
- Workspace
- Investigation

---

## Entities

Objects with persistent identity.

Examples:

- User
- Evidence
- Relationship
- Collection

---

## Derived Entities

Objects created through analysis.

Examples:

- Insight

Derived entities are generated from information rather than manually authored.

---

# Business Rules

The following rules apply throughout the platform.

## Ownership

Every business object belongs to exactly one Organization.

---

## Workspace Isolation

Business information cannot cross Workspace boundaries unless explicitly shared.

---

## Investigation Context

Evidence, Relationships, and Insights always exist within the context of an Investigation.

---

## Traceability

Every Insight must be traceable to supporting Evidence.

---

## Auditability

Every significant business action generates an audit record.

---

## Security

Every domain object is protected by permission-based access control.

---

# Domain Lifecycle

Business information evolves through a predictable lifecycle.

```
Capture

↓

Organise

↓

Connect

↓

Analyse

↓

Generate Insight

↓

Collaborate

↓

Decide

↓

Archive

↓

Retain
```

Every major workflow follows this lifecycle.

---

# AI and the Domain Model

Artificial Intelligence reasons over the domain model.

AI does not operate directly on raw documents.

Instead, AI consumes:

- Investigations
- Evidence
- Relationships
- Entities
- Collections
- Historical knowledge

The quality of AI outputs depends upon the quality and consistency of the domain model.

---

# Domain Invariants

The following invariants should always remain true.

- Every Organization owns one or more Workspaces.
- Every Workspace belongs to exactly one Organization.
- Every User belongs to an Organization.
- Every Investigation belongs to one Workspace.
- Every Evidence item belongs to one Investigation.
- Every Insight references supporting Evidence.
- Every Relationship connects valid domain entities.
- Every Collection references existing business objects.
- Every domain object is auditable.
- Every domain object is permission-aware.

Violation of these invariants indicates a defect in either implementation or business logic.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Vision | Defines why the platform exists. |
| Product Principles | Defines product decision principles. |
| Domain Objects | Defines each business object in detail. |
| Architecture | Implements the domain model. |
| Services | Align service boundaries with aggregates. |
| APIs | Expose domain capabilities. |
| Workflows | Describe business processes operating on the domain. |
| Permissions | Control access to domain objects. |

---

# Future Evolution

The domain model is expected to evolve as new business capabilities are introduced.

However:

- Existing terminology should remain stable.
- Aggregate boundaries should change only with strong architectural justification.
- New domain concepts should integrate with the existing model rather than duplicate existing responsibilities.

Changes to the Domain Model should be considered strategic architectural decisions and reviewed before implementation.

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-27 | Initial Domain Overview established. |