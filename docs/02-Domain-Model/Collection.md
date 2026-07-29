# Collection

> A curated grouping of related domain objects created to organize, reuse, and communicate investigative knowledge.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

A Collection provides a structured mechanism for organizing related domain objects without changing their ownership.

Collections enable investigators to group information according to investigative themes, business objectives, analytical needs, or operational workflows.

Unlike folders, Collections reference existing resources rather than containing or owning them.

Collections improve collaboration, reporting, search, and AI reasoning by providing meaningful business context.

---

# Scope

This document defines:

- Business purpose
- Responsibilities
- Ownership model
- Collection types
- Lifecycle
- Business rules
- AI interaction
- Search
- Audit
- Events

Implementation details such as storage structures or indexing strategies are intentionally excluded.

---

# Business Definition

A Collection is a logical grouping of domain objects created for a specific business purpose.

Collections organize knowledge rather than data.

Objects remain owned by their originating aggregate.

Collections provide reusable investigative context across the platform.

---

# Responsibilities

Collections are responsible for:

- Organizing business information
- Supporting collaboration
- Providing investigative context
- Simplifying navigation
- Supporting reporting
- Enabling reusable AI context
- Preserving curated knowledge

Collections never become the owner of referenced objects.

---

# Ownership Model

Every Collection belongs to exactly one Investigation or Workspace.

Collections may reference:

- Evidence
- Relationships
- Insights
- Investigations
- Users
- Future domain entities

Referenced objects retain their original ownership.

---

# Domain Relationships

```
            Investigation
                 │
                 ▼
            Collection
                 │
     ┌───────────┼────────────┐
     ▼           ▼            ▼
 Evidence   Relationship   Insight
       ╲         │         ╱
        ╲        ▼        ╱
         ╲   Investigation
          ╲      │
           ╲     ▼
             User
```

Collections create logical associations without affecting aggregate ownership.

---

# Collection Types

Examples include:

## Investigative Collections

- Fraud Ring
- High Priority Cases
- Repeat Offenders
- Escalated Investigations

---

## Operational Collections

- Open Investigations
- Pending Reviews
- Legal Referrals
- Compliance Reviews

---

## Analytical Collections

- High Risk Policies
- Suspicious Payments
- Linked Addresses
- Shared Bank Accounts

---

## Knowledge Collections

- Best Practice Examples
- Historical Cases
- Investigation Templates
- Training Material

---

## AI Collections

Collections prepared specifically for AI reasoning.

Examples include:

- Investigation Context
- Related Evidence
- Supporting Relationships
- Previous Findings

---

# Business Attributes

Typical Collection attributes include:

- Collection Identifier
- Investigation Identifier (optional)
- Workspace Identifier
- Name
- Description
- Collection Type
- Owner
- Status
- Created Date
- Last Updated

Implementation details are defined separately.

---

# Collection Lifecycle

Collections progress through a managed lifecycle.

```
Draft

↓

Active

↓

Shared

↓

Archived
```

Archived Collections remain available for historical reference according to organizational retention policies.

---

# Business Rules

## Ownership

Collections never own business objects.

They reference existing resources.

---

## Traceability

Every referenced object retains its original provenance and audit history.

---

## Reusability

Objects may appear in multiple Collections simultaneously.

---

## Integrity

Deleting a Collection must never delete referenced business objects.

---

## Security

Collections inherit access controls from their owning Investigation or Workspace.

Referenced objects remain subject to their own permissions.

---

# AI Responsibilities

Collections provide structured context for AI-assisted analysis.

AI may use Collections to:

- Scope investigations
- Reduce irrelevant information
- Generate summaries
- Produce reports
- Compare related investigations
- Identify recurring patterns

Collections improve AI performance by supplying curated context rather than relying solely on broad searches.

---

# Search Responsibilities

Collections support:

- Thematic search
- Investigative navigation
- Saved result sets
- Knowledge discovery
- AI context selection

Users should be able to search by:

- Name
- Type
- Owner
- Referenced objects
- Tags (future)
- Keywords

---

# Audit Responsibilities

Collection audit events include:

- Collection created
- Collection updated
- Object added
- Object removed
- Collection shared
- Collection archived

Audit history must preserve changes to membership while maintaining the independent histories of referenced objects.

---

# Events

Typical Collection events include:

- Collection Created
- Collection Updated
- Collection Shared
- Object Added
- Object Removed
- Collection Archived

These events support collaboration, reporting, and downstream processing.

---

# Permissions

Typical permissions include:

- View Collections
- Create Collections
- Update Collections
- Share Collections
- Archive Collections
- Add Objects
- Remove Objects
- Export Collections

Permission definitions are specified in the Permissions documentation.

---

# Non-Functional Requirements

Collections should be:

- Lightweight
- Searchable
- Reusable
- Auditable
- Extensible
- AI-Ready

Collections should support references to very large numbers of domain objects without duplicating underlying data.

---

# Future Evolution

Potential future capabilities include:

- Smart Collections
- Rule-based Collections
- Dynamic Collections
- AI-generated Collections
- Shared enterprise Collections
- Collection templates
- Cross-investigation Collections
- Collection analytics

These enhancements should strengthen the Collection model while preserving its role as a reusable organizational construct.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Investigation | Owns investigation-level Collections. |
| Workspace | May own workspace-level Collections. |
| Evidence | May be referenced by Collections. |
| Relationship | May be referenced by Collections. |
| Insight | May be referenced by Collections. |
| User | Creates and manages Collections. |
| AI Strategy | Defines AI use of Collections as curated context. |
| Architecture | Defines technical implementation. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-29 | Initial Collection domain model specification. |