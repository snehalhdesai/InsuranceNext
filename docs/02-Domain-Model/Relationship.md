# Relationship

> A verified connection between two or more domain entities that represents business intelligence within an Investigation.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

A Relationship represents a meaningful connection between domain entities within the InsuranceNext platform.

Unlike traditional database relationships, a Relationship is a business object with its own identity, lifecycle, provenance, confidence, and supporting evidence.

Relationships transform isolated facts into connected intelligence, enabling investigators and AI systems to understand how people, organizations, policies, claims, assets, and events relate to one another.

---

# Scope

This document defines:

- Business purpose
- Responsibilities
- Ownership model
- Relationship types
- Lifecycle
- Verification
- Business rules
- AI interaction
- Search
- Audit
- Events

Implementation details such as graph databases, storage models, or query engines are intentionally excluded.

---

# Business Definition

A Relationship expresses a business fact describing how two or more domain entities are connected.

Relationships are created through:

- Human investigation
- Imported data
- External systems
- AI-assisted discovery
- Analytical processes

A Relationship exists independently of how the connected entities are stored.

---

# Responsibilities

Relationships are responsible for:

- Connecting business entities
- Preserving provenance
- Recording confidence
- Supporting graph analysis
- Enabling explainable intelligence
- Supporting fraud detection
- Preserving investigative context

Relationships do not replace entities.

They describe how entities are connected.

---

# Ownership Model

Every Relationship belongs to exactly one Investigation.

A Relationship may reference:

- Evidence
- Users
- Organizations
- Policies
- Claims
- People
- Companies
- Vehicles
- Locations
- Financial Transactions
- Insights
- Future domain entities

Relationships may later become organizational knowledge through controlled promotion.

---

# Domain Relationships

```
                Investigation
                      │
                      ▼
               Relationship
              ╱      │      ╲
             ▼       ▼       ▼
         Entity A  Entity B  Evidence
                ╲     │     ╱
                      ▼
                  Insight
```

Relationships connect business objects without changing ownership.

---

# Relationship Components

Every Relationship consists of:

- Source Entity
- Target Entity
- Relationship Type
- Direction
- Confidence
- Provenance
- Supporting Evidence
- Created By
- Created Date

These components define both the meaning and reliability of the connection.

---

# Relationship Types

Examples include:

## Ownership

- Owns
- Controlled By
- Managed By

---

## Identity

- Same Person As
- Alias Of
- Duplicate Of

---

## Communication

- Called
- Emailed
- Messaged
- Contacted

---

## Financial

- Paid
- Received Payment
- Transferred Funds
- Shares Bank Account

---

## Insurance

- Covers
- Submitted
- Approved
- Denied
- Associated With

---

## Geographic

- Located At
- Resides At
- Visited
- Registered In

---

## Investigative

- Supports
- Contradicts
- Corroborates
- References
- Derived From

Relationship types should be extensible and governed centrally.

---

# Confidence

Every Relationship carries a confidence assessment.

Typical confidence levels include:

- Unknown
- Low
- Medium
- High
- Verified

Confidence reflects belief in the relationship, not the importance of the connected entities.

---

# Verification Lifecycle

Relationships progress through verification states.

```
Discovered

↓

Pending Review

↓

Verified

↓

Disputed

↓

Superseded

↓

Archived
```

Verification reflects confidence in the connection rather than the entities themselves.

---

# Business Rules

## Investigation Ownership

Every Relationship belongs to exactly one Investigation.

---

## Valid References

Every Relationship must reference valid domain entities.

---

## Provenance

Relationships should retain links to supporting Evidence.

---

## Explainability

AI-generated Relationships must expose the reasoning and evidence supporting the connection.

---

## Immutability

Historical Relationship assertions should not be silently modified.

Changes should be represented through superseding or versioning.

---

## Directionality

Relationship direction should be explicitly defined where meaningful.

Examples:

Person → Owns → Company

Company → Employs → Person

---

# AI Responsibilities

Artificial Intelligence may assist with:

- Relationship discovery
- Entity resolution
- Duplicate detection
- Graph expansion
- Hidden network detection
- Fraud ring analysis
- Link prediction
- Confidence estimation

AI-generated Relationships remain hypotheses until validated according to organizational policy.

---

# Search Responsibilities

Relationships support graph-oriented discovery.

Search capabilities may include:

- Connected entities
- Relationship type
- Degree of separation
- Confidence
- Investigation
- Supporting evidence
- Temporal validity

Search should enable investigators to explore networks rather than isolated records.

---

# Audit Responsibilities

Relationship audit events include:

- Relationship created
- Relationship verified
- Confidence updated
- Evidence linked
- Relationship disputed
- Relationship superseded
- Relationship archived

Every change must preserve historical traceability.

---

# Events

Typical Relationship events include:

- Relationship Discovered
- Relationship Created
- Relationship Verified
- Relationship Updated
- Relationship Disputed
- Relationship Linked
- Relationship Removed
- Relationship Archived

Events support graph maintenance, analytics, AI, and workflow orchestration.

---

# Permissions

Typical permissions include:

- View Relationships
- Create Relationships
- Verify Relationships
- Link Evidence
- Merge Relationships
- Archive Relationships
- Export Relationship Graph

Permission definitions are specified in the Permissions documentation.

---

# Non-Functional Requirements

Relationships should be:

- Explainable
- Traceable
- Immutable
- Searchable
- Graph-ready
- Auditable
- Scalable
- AI-Ready

The platform should support billions of relationship edges while maintaining query performance and provenance.

---

# Future Evolution

Potential future capabilities include:

- Temporal relationships
- Probabilistic relationships
- Multi-hop reasoning
- Automatic relationship validation
- Knowledge graph synchronization
- Cross-investigation graph analysis
- Graph embeddings
- Semantic relationship inference

These capabilities should extend the Relationship model while preserving its role as the platform's representation of connected intelligence.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Investigation | Owns Relationships. |
| Evidence | Provides factual support for Relationships. |
| Insight | Uses Relationships to derive conclusions. |
| Collection | Organizes Relationship sets. |
| User | Creates and validates Relationships. |
| AI Strategy | Defines AI-assisted relationship discovery. |
| Architecture | Defines graph storage and processing implementation. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-28 | Initial Relationship domain model specification. |