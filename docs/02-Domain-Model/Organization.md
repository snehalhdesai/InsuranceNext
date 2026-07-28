# Organization

> The root aggregate representing an enterprise that owns and governs an InsuranceNext environment.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

The Organization is the highest-level business entity within InsuranceNext.

It represents an enterprise customer and establishes the security, governance, ownership, and operational boundary for all platform resources.

Every business object within InsuranceNext ultimately belongs to exactly one Organization.

The Organization aggregate is the root of the domain hierarchy and defines the highest level of ownership.

---

# Scope

This document defines:

- Business purpose
- Responsibilities
- Aggregate boundaries
- Business rules
- Ownership
- Relationships
- Lifecycle
- Security responsibilities
- AI responsibilities
- Audit requirements

This document does not define authentication, billing, deployment, or infrastructure.

---

# Business Definition

An Organization represents a legally recognised business or operational entity that uses InsuranceNext.

Examples include:

- Insurance Companies
- Reinsurance Companies
- Third Party Administrators
- Claims Management Companies
- Investigation Firms
- Government Agencies
- Regulatory Bodies

An Organization owns its data, users, workspaces, configuration, and platform policies.

---

# Business Responsibilities

The Organization aggregate is responsible for:

- Enterprise ownership
- Tenant isolation
- Governance
- Security policies
- Workspace ownership
- User ownership
- Platform configuration
- AI governance
- Audit ownership
- Compliance boundaries

No business object exists outside an Organization.

---

# Aggregate Responsibilities

The Organization aggregate guarantees consistency for enterprise-level operations.

It owns:

- Enterprise configuration
- Security policies
- Workspace catalogue
- User directory
- Platform settings
- Feature enablement
- Integration configuration
- Compliance configuration

Objects below the Organization boundary maintain their own transactional consistency.

---

# Ownership Model

The Organization owns:

- Workspaces
- Users
- Roles
- Permissions
- Integrations
- AI Policies
- Data Retention Policies
- Audit Policies

Indirect ownership includes:

- Investigations
- Evidence
- Relationships
- Insights
- Collections

Ownership cascades through the domain hierarchy.

---

# Domain Relationships

```
Organization

├── Workspace

│      ├── Investigation

│      │      ├── Evidence

│      │      ├── Relationship

│      │      ├── Insight

│      │      └── Collection

│      └── Users

├── Roles

├── Policies

├── Integrations

└── AI Governance
```

---

# Business Attributes

Every Organization maintains core business information.

Typical attributes include:

- Organization Identifier
- Display Name
- Legal Name
- Industry
- Business Type
- Status
- Time Zone
- Primary Language
- Country
- Region
- Branding
- Contact Information

Implementation details are defined separately.

---

# Organization Status

An Organization progresses through a controlled lifecycle.

```
Provisioning

↓

Active

↓

Suspended

↓

Archived

↓

Deleted
```

Deletion should normally occur only after retention requirements have been satisfied.

---

# Business Rules

The following rules always apply.

## Unique Ownership

Every Workspace belongs to exactly one Organization.

---

## User Ownership

Every User belongs to exactly one Organization.

---

## Tenant Isolation

Business information cannot be shared between Organizations unless explicitly supported through controlled collaboration mechanisms.

---

## Enterprise Governance

Organization policies override Workspace defaults where applicable.

---

## Compliance

Organization-wide compliance settings apply to all subordinate business objects.

---

## Configuration Authority

Enterprise administrators control Organization-level configuration.

---

# Security Responsibilities

The Organization defines enterprise-wide security.

Responsibilities include:

- Identity federation
- Authentication policies
- Password policies
- Multi-factor authentication
- Session policies
- Data residency
- Encryption policies
- Access governance

Lower-level objects inherit these controls where appropriate.

---

# AI Responsibilities

The Organization defines enterprise AI governance.

Responsibilities include:

- AI feature enablement
- Model approval policies
- Prompt governance
- AI audit requirements
- Data sharing restrictions
- Human approval requirements
- AI usage monitoring

All AI capabilities operate within Organization-defined governance boundaries.

---

# Audit Responsibilities

The Organization owns enterprise audit requirements.

Organization-level auditing includes:

- Administrative changes
- Policy changes
- Permission changes
- Integration changes
- AI configuration changes
- Security events

Audit records must be immutable and retained according to organizational policy.

---

# Integration Responsibilities

Organization-level integrations include:

- Identity Providers
- Core Insurance Platforms
- CRM Systems
- ERP Systems
- Email Services
- Document Repositories
- External Data Providers
- AI Providers

These integrations become available to authorized Workspaces according to organizational policy.

---

# Search Responsibilities

Organization metadata supports:

- Enterprise discovery
- Administrative search
- Governance reporting
- Audit reporting
- Usage analytics

Business content is not searched at the Organization level.

Search primarily indexes metadata rather than operational data.

---

# Events

Typical Organization events include:

- Organization Created
- Organization Activated
- Organization Updated
- Organization Suspended
- Organization Archived
- Organization Deleted
- Organization Policy Changed
- Organization Integration Added
- Organization Integration Removed

Events support auditability and downstream processing.

---

# Permissions

Typical Organization permissions include:

- View Organization
- Update Organization
- Manage Workspaces
- Manage Users
- Manage Roles
- Manage Policies
- Manage Integrations
- Configure AI
- View Audit Logs

Permission definitions are documented in the Permissions section.

---

# Non-Functional Requirements

The Organization aggregate should satisfy the following characteristics:

- Secure
- Highly Available
- Auditable
- Scalable
- Extensible
- Configurable
- Provider Independent

---

# Future Evolution

Future enhancements may include:

- Multi-organization groups
- Delegated administration
- Cross-organization collaboration
- Organization templates
- Enterprise policy inheritance
- Federated governance
- Marketplace participation

These capabilities should extend rather than redefine the Organization aggregate.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Domain Overview | Defines the overall business model. |
| Workspace | Defines operational business boundaries within an Organization. |
| User | Defines participants belonging to an Organization. |
| Permissions | Defines authorization rules. |
| Architecture | Defines technical implementation. |
| Services | Defines Organization service responsibilities. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-28 | Initial Organization aggregate specification. |