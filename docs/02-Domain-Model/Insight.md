# Insight

> A reasoned observation, conclusion, hypothesis, or recommendation derived from Evidence and Relationships within an Investigation.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

An Insight represents knowledge generated during an Investigation.

Unlike Evidence, which records facts, an Insight captures the interpretation of those facts.

Insights help investigators understand the significance of information, identify emerging patterns, evaluate risks, and support business decisions.

Every Insight should be explainable, traceable, and supported by evidence.

---

# Scope

This document defines:

- Business purpose
- Responsibilities
- Ownership model
- Insight lifecycle
- Insight types
- Business rules
- AI interaction
- Search
- Audit
- Events

Implementation details such as AI prompts, machine learning models, or reporting engines are intentionally excluded.

---

# Business Definition

An Insight is a structured interpretation of one or more Evidence items and Relationships.

Insights may be created by investigators, generated through analytical processes, or proposed by AI systems.

An Insight represents understanding—not raw information.

Insights support decision-making but are not decisions themselves.

---

# Responsibilities

Insights are responsible for:

- Explaining findings
- Identifying patterns
- Highlighting anomalies
- Supporting hypotheses
- Communicating investigative observations
- Providing recommendations
- Preserving reasoning

Insights do not replace evidence.

They explain the significance of evidence.

---

# Ownership Model

Every Insight belongs to exactly one Investigation.

An Insight may reference:

- Evidence
- Relationships
- Collections
- Timeline events
- AI analyses
- Other Insights (future)

Ownership remains with the Investigation aggregate.

---

# Domain Relationships

```
Evidence
     │
     ▼
Relationship
     │
     ▼
 Insight
     │
     ▼
Decision / Report
```

Insights are derived from information rather than serving as the information itself.

---

# Insight Types

InsuranceNext supports multiple categories of insights.

## Observational

Describes noteworthy findings without drawing conclusions.

Examples:

- Duplicate contact details detected
- Missing documentation identified

---

## Analytical

Interprets patterns and relationships.

Examples:

- Multiple claims appear connected
- Payment behaviour is unusual

---

## Predictive

Estimates future outcomes or risks.

Examples:

- Elevated fraud likelihood
- High probability of policy lapse

Predictive insights should include confidence measures and assumptions.

---

## Recommendation

Suggests possible actions.

Examples:

- Conduct additional verification
- Request supporting documentation
- Escalate for specialist review

Recommendations remain advisory.

---

## Hypothesis

Represents an unverified explanation requiring further investigation.

Examples:

- Two claimants may be acting together
- Property damage may pre-date policy inception

Hypotheses must be clearly distinguishable from verified conclusions.

---

# Business Attributes

Typical Insight attributes include:

- Insight Identifier
- Investigation Identifier
- Title
- Description
- Insight Type
- Status
- Priority
- Confidence
- Created By
- Created Date
- Last Updated

Implementation details are defined separately.

---

# Confidence

Every Insight should include an assessment of confidence.

Typical levels include:

- Low
- Medium
- High
- Verified

Confidence reflects the strength of supporting information and should be reviewed as new evidence becomes available.

---

# Insight Lifecycle

Insights progress through a managed lifecycle.

```
Draft

↓

Proposed

↓

Under Review

↓

Accepted

↓

Rejected

↓

Archived
```

Lifecycle transitions should be governed by organizational policy.

---

# Business Rules

## Investigation Ownership

Every Insight belongs to exactly one Investigation.

---

## Traceability

Every Insight must reference supporting Evidence and/or Relationships.

---

## Explainability

Users should be able to understand why an Insight exists and what information supports it.

---

## Separation of Facts and Interpretation

Evidence records facts.

Insights record interpretations.

These responsibilities should never be conflated.

---

## Human Accountability

AI-generated Insights should be reviewed before influencing significant business decisions where organizational policy requires.

---

## Continuous Evolution

Insights may evolve as additional Evidence becomes available.

Historical versions should remain traceable.

---

# AI Responsibilities

Artificial Intelligence may assist with:

- Pattern detection
- Anomaly identification
- Insight drafting
- Risk assessment
- Recommendation generation
- Report preparation
- Summarisation

AI-generated Insights should clearly indicate:

- Supporting evidence
- Reasoning
- Confidence
- Assumptions
- Areas of uncertainty

---

# Search Responsibilities

Insights are searchable by:

- Type
- Status
- Confidence
- Keywords
- Referenced entities
- Investigation
- Supporting evidence
- Related relationships

Search should prioritize explainability over simple keyword matching.

---

# Audit Responsibilities

Insight audit events include:

- Insight created
- Insight updated
- Insight reviewed
- Insight accepted
- Insight rejected
- Supporting evidence added
- Confidence changed
- Insight archived

All changes should remain historically traceable.

---

# Events

Typical Insight events include:

- Insight Proposed
- Insight Created
- Insight Updated
- Insight Reviewed
- Insight Accepted
- Insight Rejected
- Insight Archived

Events support workflows, notifications, reporting, and analytics.

---

# Permissions

Typical permissions include:

- View Insights
- Create Insights
- Update Insights
- Review Insights
- Approve Insights
- Reject Insights
- Archive Insights
- Export Insights

Permission definitions are specified in the Permissions documentation.

---

# Non-Functional Requirements

Insights should be:

- Explainable
- Traceable
- Searchable
- Auditable
- Versioned
- AI-Ready
- Extensible

The platform should support large numbers of Insights while preserving links to supporting information and historical context.

---

# Future Evolution

Potential future capabilities include:

- Collaborative insight authoring
- Insight version comparison
- Confidence calibration
- AI-assisted peer review
- Cross-investigation insight discovery
- Organizational knowledge promotion
- Insight quality scoring
- Knowledge graph integration

These capabilities should strengthen the Insight model while preserving its role as the platform's representation of investigative understanding.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Investigation | Owns Insights. |
| Evidence | Provides factual support for Insights. |
| Relationship | Connects the information used to derive Insights. |
| Collection | Organizes related Insights and supporting resources. |
| User | Creates, reviews, and approves Insights. |
| AI Strategy | Defines AI-assisted insight generation. |
| Architecture | Defines technical implementation of insight services. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-29 | Initial Insight domain model specification. |