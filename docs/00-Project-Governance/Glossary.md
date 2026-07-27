# InsuranceNext Glossary

> Canonical business and technical terminology used throughout the InsuranceNext platform.

**Version:** 1.0  
**Status:** Active  
**Owner:** Architecture Team

---

# Purpose

The glossary defines the official vocabulary for InsuranceNext.

Every document, API, database schema, UI component, source code module, and AI assistant should use the terminology defined here.

If a term is not defined here, it should not become part of the platform without review.

---

# Terminology Principles

The glossary follows these principles:

- One concept has one name.
- One name represents one concept.
- Business terminology takes precedence over technical jargon.
- Definitions should remain stable over time.
- New terminology should be added through documentation updates and, where appropriate, Architecture Decision Records (ADRs).

---

# Business Terms

## Organization

A legal business entity that owns and operates within InsuranceNext.

Examples include:

- Insurance Company
- Broker
- Third Party Administrator (TPA)
- Loss Adjuster
- Investigation Firm

An Organization is the highest level of ownership within the platform.

---

## Workspace

A logical environment belonging to a single Organization.

A Workspace groups users, investigations, evidence, collections, insights, and other resources for a specific business purpose.

Examples:

- Fraud Investigations
- Motor Claims
- Property Claims
- Underwriting Risk
- Compliance

---

## User

A person who authenticates into InsuranceNext.

A User belongs to one Organization and may have access to one or more Workspaces depending on assigned permissions.

---

## Role

A collection of permissions assigned to Users.

Examples:

- Administrator
- Investigator
- Claims Adjuster
- Fraud Analyst
- Underwriter
- Compliance Officer
- Auditor

---

## Investigation

A structured case created to investigate an event, claim, customer, policy, or other business matter.

Investigations provide the primary collaborative workspace for intelligence activities.

---

## Evidence

Any piece of information collected during an investigation.

Examples include:

- Documents
- Images
- Videos
- Audio recordings
- Emails
- Policies
- Claim forms
- Police reports
- Witness statements
- Notes

Evidence is immutable. Corrections create new versions rather than overwriting historical data.

---

## Relationship

A meaningful connection between two or more entities.

Relationships describe how information is linked.

Examples:

- Person owns Vehicle
- Customer submitted Claim
- Witness knows Customer
- Phone belongs to Individual
- Company employs Person

Relationships form the basis of graph analysis.

---

## Entity

A uniquely identifiable object within the platform.

Examples include:

- Person
- Vehicle
- Property
- Company
- Policy
- Claim
- Bank Account
- Phone Number
- Email Address

Entities may participate in one or more Relationships.

---

## Insight

Knowledge derived from one or more Evidence items using business rules, analytics, graph analysis, or AI.

Insights are generated—they are not manually created as raw data.

---

## Collection

A curated grouping of related resources.

Collections may contain:

- Evidence
- Entities
- Insights
- Relationships
- Saved searches
- Documents

Collections support organization and collaboration without duplicating underlying data.

---

# Technical Terms

## Service

An independently deployable software component responsible for a specific business capability.

Examples:

- Identity Service
- Evidence Service
- Investigation Service
- Search Service

---

## API

A formal contract through which services, clients, or external systems communicate.

InsuranceNext follows an API-first design philosophy.

---

## Event

A record of something that has occurred within the system.

Examples:

- InvestigationCreated
- EvidenceUploaded
- UserInvited
- InsightGenerated

Events are immutable.

---

## Domain Model

The collection of business concepts and their relationships.

The Domain Model is the foundation for:

- Database design
- APIs
- Services
- User Interface
- AI reasoning

---

## Bounded Context

A logical boundary within which a particular domain model applies consistently.

Each major microservice corresponds to a bounded context.

---

## AI Assistant

An AI-powered capability that assists users by reasoning over structured and unstructured information within InsuranceNext.

AI Assistants operate within defined permission boundaries and never bypass platform authorization.

---

## Knowledge Graph

A graph representation of entities and their relationships used to support investigation, reasoning, search, and visualization.

---

## Audit Trail

A complete chronological record of actions performed within the platform.

Audit records are immutable and retained according to organizational policy.

---

# Naming Conventions

The following naming conventions apply throughout the project.

| Item | Convention | Example |
|-------|------------|---------|
| Document | PascalCase | Evidence.md |
| Service | PascalCase | EvidenceService |
| API Endpoint | kebab-case | /api/investigations |
| Database Table | snake_case | investigation_events |
| Database Column | snake_case | created_at |
| Event | PascalCase (Past Tense) | InvestigationCreated |
| Environment Variable | UPPER_SNAKE_CASE | DATABASE_URL |
| Branch | kebab-case | feature/evidence-service |

---

# Reserved Terms

The following terms are reserved and should not be used interchangeably.

| Correct | Avoid |
|----------|-------|
| Investigation | Case (unless referring to an external system) |
| Evidence | Attachment |
| Organization | Company (unless legally required) |
| Workspace | Project |
| Insight | Finding |
| Relationship | Link |
| Collection | Folder |
| Entity | Object |
| Service | Module |

---

# Future Additions

This glossary is expected to grow as new platform capabilities are introduced.

All new terminology should be reviewed for consistency before adoption.

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-26 | Initial glossary established. |