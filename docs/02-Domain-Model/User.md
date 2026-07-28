# User

> The enterprise identity representing a person who interacts with the InsuranceNext platform.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

The User represents an authenticated individual who performs work within the InsuranceNext platform.

Users investigate claims, analyse evidence, collaborate with colleagues, configure workspaces, review AI-generated insights, and make business decisions.

The User domain object represents business identity rather than authentication credentials.

Authentication mechanisms are implementation concerns and are defined separately.

---

# Scope

This document defines:

- Business purpose
- Responsibilities
- Identity model
- Lifecycle
- Business rules
- Relationships
- Security responsibilities
- AI responsibilities
- Audit requirements

This document does not define authentication protocols, identity providers, or session management.

---

# Business Definition

A User is an individual who has been granted access to an Organization and one or more Workspaces.

A User performs actions on behalf of the Organization and is accountable for those actions.

Every significant activity within the platform can be attributed to a User.

---

# Business Responsibilities

A User is responsible for:

- Conducting investigations
- Managing evidence
- Creating relationships
- Generating insights
- Reviewing AI recommendations
- Collaborating with colleagues
- Managing collections
- Participating in workflows
- Making business decisions

---

# Identity Model

A User possesses a persistent enterprise identity.

Identity includes:

- Organization membership
- Workspace memberships
- Assigned roles
- Permissions
- Expertise
- Preferences
- Audit history

Authentication credentials remain external to the domain model.

---

# Ownership Model

Every User belongs to exactly one Organization.

A User may belong to one or more Workspaces.

A User may participate in many Investigations.

A User may own, create, review, or approve multiple business objects.

---

# Domain Relationships

```
Organization
      │
      ▼
     User
      │
      ├──────────────┐
      ▼              ▼
 Workspace      Investigation
                     │
                     ▼
      Evidence • Relationships • Insights
```

Users interact with business objects but do not own them.

Ownership remains with the Organization and Workspace aggregates.

---

# User Types

InsuranceNext supports different categories of users.

Examples include:

- Investigator
- Claims Adjuster
- Underwriter
- Fraud Analyst
- Compliance Officer
- Legal Advisor
- Risk Analyst
- Team Leader
- Workspace Administrator
- Organization Administrator
- Executive

User types describe business responsibilities rather than technical permissions.

---

# Business Attributes

Typical User attributes include:

- User Identifier
- Display Name
- Email Address
- Job Title
- Department
- Organization Identifier
- Preferred Language
- Time Zone
- Status
- Profile Photo
- Contact Information

Implementation details are defined separately.

---

# User Lifecycle

A User progresses through a controlled lifecycle.

```
Invited

↓

Active

↓

Suspended

↓

Inactive

↓

Archived
```

Archived users remain associated with historical business records for audit purposes.

---

# Business Rules

## Organization Membership

Every User belongs to exactly one Organization.

---

## Workspace Membership

Users may participate in multiple Workspaces.

Workspace membership determines operational visibility.

---

## Accountability

Every business action must be attributable to a User or approved system process.

---

## Least Privilege

Users receive only the permissions necessary to perform their responsibilities.

---

## Immutable Identity

Historical records continue to reference the User even after the account becomes inactive or archived.

---

# Security Responsibilities

Users operate within Organization and Workspace security boundaries.

Responsibilities include:

- Identity verification
- Permission enforcement
- Role assignment
- Access reviews
- Session accountability
- Multi-factor authentication support (implementation)

Security policies are inherited from the Organization.

---

# AI Responsibilities

Users collaborate with AI rather than delegate authority.

AI interactions include:

- Requesting summaries
- Reviewing recommendations
- Asking questions
- Exploring relationships
- Generating reports
- Reviewing insights

AI never replaces User accountability.

Users remain responsible for accepting, rejecting, or modifying AI-generated outputs.

---

# Search Responsibilities

Users may search only information they are authorized to access.

Search personalization may include:

- Recent investigations
- Assigned work
- Saved searches
- Preferred collections
- Frequently accessed entities

Search results must respect Organization, Workspace, and object-level permissions.

---

# Audit Responsibilities

Every User action should be auditable.

Examples include:

- Login
- Investigation updates
- Evidence creation
- Relationship modifications
- Insight approvals
- AI interactions
- Permission changes
- Administrative actions

Audit records must remain immutable.

---

# Events

Typical User events include:

- User Invited
- User Activated
- User Updated
- User Suspended
- User Archived
- Workspace Joined
- Workspace Left
- Role Assigned
- Role Removed

These events support auditability, notifications, and downstream processing.

---

# Permissions

Typical User permissions include:

- View Profile
- Update Profile
- Join Workspace
- Leave Workspace
- Create Investigation
- Manage Evidence
- Review Insights
- Use AI Features
- View Audit History

Permission definitions are specified in the Permissions documentation.

---

# Non-Functional Requirements

The User domain object should be:

- Secure
- Auditable
- Scalable
- Extensible
- Privacy-aware
- Highly Available

Identity information should support enterprise-scale organizations with thousands of concurrent users.

---

# Future Evolution

Potential future enhancements include:

- Skills and certifications
- Expertise profiles
- Workload balancing
- Availability status
- Team structures
- Delegated authority
- AI proficiency indicators
- Activity analytics

These enhancements should enrich the User model without changing its core responsibility as the enterprise identity.

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Domain Overview | Defines the overall business model. |
| Organization | Defines the enterprise boundary that owns Users. |
| Workspace | Defines the operational context in which Users collaborate. |
| Investigation | Defines the primary business object Users work on. |
| Permissions | Defines authorization rules. |
| Architecture | Defines technical identity and authentication implementation. |

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-28 | Initial User domain model specification. |