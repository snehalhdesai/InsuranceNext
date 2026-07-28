# Investigation

> The primary business aggregate representing a structured investigative process within the InsuranceNext platform.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

The Investigation is the central operational aggregate of InsuranceNext.

It represents a structured body of work undertaken to understand, assess, or resolve a business problem using evidence, collaboration, analysis, and intelligence.

Every operational activity within InsuranceNext ultimately occurs within the context of an Investigation.

The Investigation aggregate provides the transactional, collaborative, and analytical boundary for operational work.

---

# Scope

This document defines:

- Business purpose
- Aggregate responsibilities
- Ownership model
- Lifecycle
- Participants
- Business rules
- Collaboration
- AI interaction
- Events
- Security
- Search
- Audit
- Extensibility

Implementation details such as database schemas, APIs, workflow engines, or storage mechanisms are intentionally excluded.

---

# Business Definition

An Investigation is a managed process for collecting information, analysing evidence, identifying relationships, generating insights, and reaching supported conclusions.

Investigations provide a controlled environment in which teams collaborate while preserving traceability, governance, and accountability.

An Investigation is not merely a record—it is the operational workspace in which intelligence is created.

---

# Aggregate Responsibilities

The Investigation aggregate is responsible for maintaining consistency across all operational activities.

It owns:

- Investigation metadata
- Participants
- Evidence
- Relationships
- Insights
- Collections
- Timeline
- Tasks (future)
- Decisions (future)
- Investigation state

The Investigation aggregate guarantees the consistency of these related objects.

---

# Ownership Model

Every Investigation belongs to exactly one Workspace.

An Investigation owns:

- Evidence
- Relationships
- Insights
- Investigation-specific Collections
- Timeline events
- AI context
- Collaboration history

Indirect ownership extends to all derived intelligence generated during the investigation.

---

# Domain Relationships

```
Organization
      │
Workspace
      │
      ▼
 Investigation
      │
 ┌────┼──────────────┬─────────────┐
 ▼    ▼              ▼             ▼
Evidence Relationship Insight Collection
      │              │
      └───────┬──────┘
              ▼
        Intelligence Graph
```

---

# Investigation Objectives

Every Investigation should enable users to:

- Capture information
- Preserve evidence
- Understand relationships
- Generate intelligence
- Collaborate effectively
- Support decisions
- Maintain auditability
- Produce explainable outcomes

---

# Investigation Lifecycle

Investigations progress through controlled business states.

```
Draft

↓

Open

↓

Active

↓

Under Review

↓

Completed

↓

Closed

↓

Archived
```

State transitions should follow organizational governance and business rules.

---

# Participants

An Investigation may involve multiple participants.

Examples include:

- Lead Investigator
- Investigator
- Reviewer
- Supervisor
- Fraud Analyst
- Claims Adjuster
- Legal Advisor
- Compliance Officer
- AI Assistant (non-human participant)

Participants collaborate according to assigned roles and permissions.

---

# Business Attributes

Typical Investigation attributes include:

- Investigation Identifier
- Title
- Description
- Workspace Identifier
- Status
- Priority
- Classification
- Risk Level
- Owner
- Created Date
- Last Updated
- Closed Date

Implementation details are defined elsewhere.

---

# Collaboration Model

Investigations support collaborative work.

Participants may:

- Add evidence
- Comment
- Review findings
- Assign work
- Share insights
- Approve conclusions
- Request AI assistance

Collaboration history forms part of the permanent audit record.

---

# AI Responsibilities

Artificial Intelligence assists throughout the Investigation lifecycle.

Typical AI capabilities include:

- Summarising evidence
- Suggesting relationships
- Identifying inconsistencies
- Highlighting missing information
- Recommending next actions
- Generating reports
- Detecting anomalies
- Producing explainable insights

AI recommendations remain advisory.

Human participants retain responsibility for all investigative decisions.

---

# Business Rules

## Workspace Ownership

Every Investigation belongs to exactly one Workspace.

---

## Evidence Ownership

Every Evidence item belongs to exactly one Investigation.

---

## Relationship Context

Relationships created during an Investigation remain associated with that Investigation unless explicitly promoted to shared organizational knowledge.

---

## Insight Traceability

Every Insight must reference supporting Evidence and/or Relationships.

---

## Immutable History

Historical Investigation activity cannot be altered once recorded.

---

## Controlled State Changes

Investigation lifecycle transitions require appropriate permissions.

---

## Participant Accountability

Every business action must be attributable to an authenticated participant or approved system process.

---

# Search Responsibilities

Investigations provide the primary search context for operational users.

Searchable content may include:

- Metadata
- Evidence
- Relationships
- Insights
- Collections
- Timeline
- Comments
- Attachments (future)

Search results must respect user permissions.

---

# Audit Responsibilities

Every significant Investigation activity must be recorded.

Examples include:

- Investigation creation
- Status changes
- Evidence additions
- Evidence modifications
- Relationship creation
- Insight approval
- Participant changes
- AI interactions
- Workflow transitions

Audit history must be immutable and complete.

---

# Events

Typical Investigation events include:

- Investigation Created
- Investigation Updated
- Investigation Opened
- Investigation Assigned
- Participant Added
- Participant Removed
- Evidence Added
- Evidence Removed
- Relationship Created
- Insight Generated
- Investigation Reviewed
- Investigation Closed
- Investigation Archived

Events support workflows, notifications, analytics, and downstream services.

---

# Permissions

Typical permissions include:

- Create Investigation
- View Investigation
- Update Investigation
- Close Investigation
- Archive Investigation
- Assign Participants
- Add Evidence
- Create Insights
- Generate AI Analysis
- Export Investigation

Permission definitions are specified in the Permissions documentation.

---

# Non-Functional Requirements

The Investigation aggregate should be:

- Secure
- Highly Available
- Auditable
- Searchable
- Extensible
- Scalable
- Explainable
- AI-Ready

The aggregate should support long-running investigations spanning months or years while maintaining performance and consistency.

---

# Future Evolution

Potential future capabilities include:

- Investigation templates
- Automated workflow orchestration
- Cross-investigation intelligence
- AI-generated investigation plans
- Predictive risk scoring
- Real-time collaboration
- External stakeholder participation
- Investigation versioning

These enhancements should strengthen the Investigation aggregate without changing its role as the primary operational boundary.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Domain Overview | Defines the overall business model. |
| Organization | Defines enterprise ownership. |
| Workspace | Defines the operational context. |
| User | Defines investigation participants. |
| Evidence | Defines information collected within an Investigation. |
| Relationship | Defines connections discovered during an Investigation. |
| Insight | Defines intelligence derived from investigation data. |
| Collection | Defines curated groups of investigation resources. |
| Workflows | Defines business processes operating on Investigations. |
| Permissions | Defines authorization rules. |
| Architecture | Defines technical implementation. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-28 | Initial Investigation aggregate specification. |