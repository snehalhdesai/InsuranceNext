# Domain Glossary

> Canonical business vocabulary for the InsuranceNext Domain Model.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

The Domain Glossary defines the canonical business terminology used throughout the InsuranceNext platform.

Its purpose is to ensure that product managers, architects, developers, AI engineers, business analysts, testers, and stakeholders use a consistent vocabulary when discussing the platform.

This glossary defines business concepts only.

It intentionally excludes implementation details.

---

# Scope

This glossary applies to every document within the Domain Model and should be treated as the authoritative reference for business terminology.

Where conflicts arise between informal language and this glossary, the definitions contained here take precedence.

---

# Core Domain Terms

## Organization

The highest business boundary within the platform.

An Organization represents an enterprise or customer responsible for governance, ownership, security policies, users, and workspaces.

---

## Workspace

A collaborative operational environment within an Organization.

A Workspace provides the boundary in which investigations are created, managed, and executed.

---

## User

A business identity that participates in platform activities.

Users collaborate within Organizations and Workspaces according to assigned roles and permissions.

---

## Investigation

The primary operational aggregate.

An Investigation represents a structured body of work undertaken to collect information, analyse evidence, discover relationships, generate insights, and support business decisions.

---

## Evidence

A verifiable business fact.

Evidence represents factual information that supports or contradicts investigative understanding.

Evidence is not limited to files or documents.

---

## Relationship

A business connection between domain entities.

Relationships describe how facts, people, organizations, policies, claims, or other business objects are connected.

Relationships are first-class domain objects.

---

## Insight

A reasoned interpretation derived from Evidence and Relationships.

Insights represent understanding rather than facts.

Every Insight should be explainable and traceable.

---

## Collection

A curated grouping of related domain objects.

Collections organize knowledge without changing ownership of the referenced resources.

---

# Supporting Concepts

## Aggregate

A business consistency boundary.

An Aggregate groups related business objects that should be managed as a single unit to preserve business rules and consistency.

Within the Domain Model, Investigation is the primary operational aggregate.

---

## Entity

A business object with a persistent identity.

Entities continue to exist even when their attributes change.

Examples include Organizations, Investigations, Evidence, and Insights.

---

## Business Fact

A piece of verifiable information about the business domain.

Facts form the foundation of investigative reasoning.

Evidence records business facts.

---

## Intelligence

Business understanding created by interpreting facts and relationships.

Insights represent intelligence within the platform.

---

## Provenance

The documented origin and history of a business object.

Provenance enables traceability, accountability, and confidence in investigative information.

---

## Confidence

A measure of the reliability or certainty associated with an Evidence item, Relationship, or Insight.

Confidence does not indicate business importance.

---

## Traceability

The ability to follow a business conclusion back through Relationships to the supporting Evidence.

Traceability supports explainability, governance, and auditability.

---

## Explainability

The ability to understand why a conclusion, recommendation, or AI-generated result exists.

Every Insight should be explainable through supporting Relationships and Evidence.

---

## Lifecycle

The sequence of business states through which a domain object progresses during its existence.

Each domain object defines its own lifecycle according to business rules.

---

## Ownership

The business aggregate responsible for managing a domain object.

Ownership determines lifecycle, consistency, and governance responsibilities.

Referencing an object does not imply ownership.

---

## Reference

A logical association to an existing domain object.

Collections reference business objects but do not own them.

---

## Collaboration

The coordinated activities of multiple Users working within an Investigation.

Collaboration includes creating evidence, validating findings, reviewing insights, and contributing investigative knowledge.

---

## Audit Trail

The immutable historical record of significant business activities.

Audit trails support accountability, compliance, and operational transparency.

---

## Business Rule

A policy or constraint governing how domain objects behave.

Business rules protect the integrity and consistency of the domain.

---

## AI Assistance

The use of artificial intelligence to support investigative activities.

AI may recommend, summarize, classify, analyse, or suggest.

AI does not replace human accountability.

---

# Domain Principles

The InsuranceNext Domain Model is founded on the following principles.

## Facts Before Conclusions

Evidence records facts.

Insights record interpretations.

The two should never be confused.

---

## Relationships Create Intelligence

Information becomes significantly more valuable when meaningful relationships between business objects are understood.

---

## Every Conclusion Must Be Explainable

Insights should always be supported by Evidence and Relationships.

---

## Ownership Is Explicit

Every domain object has a clearly defined owner.

References do not change ownership.

---

## Business Language Comes First

The Domain Model defines business meaning independently of implementation technology.

Technology should implement the domain rather than define it.

---

## AI Supports Human Decision-Making

Artificial intelligence augments investigators by assisting with analysis, pattern recognition, and recommendations.

Responsibility for significant business decisions remains with authorized users.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Domain Overview | Defines the overall business model. |
| Organization | Defines enterprise ownership. |
| Workspace | Defines operational boundaries. |
| User | Defines business identity. |
| Investigation | Defines the operational aggregate. |
| Evidence | Defines business facts. |
| Relationship | Defines connected intelligence. |
| Insight | Defines investigative understanding. |
| Collection | Defines curated knowledge. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-29 | Initial Domain Glossary defining the canonical business vocabulary for the InsuranceNext Domain Model. |