# System Context

> Defines the external environment, users, and systems that interact with the InsuranceNext platform.

**Version:** 1.0  
**Status:** Active  
**Owner:** Platform Architecture

---

# Purpose

This document describes InsuranceNext within its broader ecosystem.

It identifies the people, organizations, and external systems that interact with the platform, along with the major information flows between them.

The objective is to establish clear system boundaries before defining the internal architecture.

---

# Scope

This document defines:

- System boundary
- Primary users
- External systems
- External integrations
- Information flows
- Trust boundaries
- High-level responsibilities

Internal implementation details are intentionally excluded.

---

# System Overview

InsuranceNext is an AI-native investigation and intelligence platform for the insurance industry.

The platform enables investigators, analysts, and operational teams to manage investigations, collect evidence, discover relationships, generate insights, and collaborate securely.

InsuranceNext operates as the central intelligence platform while integrating with enterprise systems and external information providers.

---

# System Boundary

InsuranceNext is responsible for:

- Investigation management
- Evidence management
- Relationship intelligence
- Insight generation
- AI-assisted analysis
- Collaboration
- Search
- Audit
- Reporting
- Security
- Workflow orchestration

The platform does not replace core policy administration, claims processing, or identity providers. Instead, it integrates with them.

---

# Primary Users

The platform is designed for a diverse set of business users.

Examples include:

- Investigators
- Fraud Analysts
- Claims Adjusters
- Underwriters
- Compliance Officers
- Legal Teams
- Risk Analysts
- Supervisors
- Executives
- Workspace Administrators
- Organization Administrators

Each user interacts with the platform according to assigned roles and permissions.

---

# External Systems

InsuranceNext exchanges information with multiple enterprise systems.

Typical integrations include:

## Identity Providers

Examples:

- Microsoft Entra ID (Azure AD)
- Okta
- Auth0
- SAML Providers

Purpose:

- Authentication
- Single Sign-On
- User provisioning

---

## Core Insurance Systems

Examples:

- Policy Administration Systems
- Claims Management Systems
- Billing Systems

Purpose:

- Policy information
- Claims information
- Customer records

---

## CRM Systems

Examples:

- Salesforce
- Microsoft Dynamics 365

Purpose:

- Customer information
- Communication history
- Case references

---

## Document Management Systems

Examples:

- SharePoint
- OpenText
- Enterprise Content Management platforms

Purpose:

- Document retrieval
- Evidence storage
- Historical records

---

## External Data Providers

Examples:

- Government registries
- Company registers
- Vehicle databases
- Credit agencies
- Sanctions lists

Purpose:

- Verification
- Enrichment
- Fraud detection

---

## AI Providers

Examples:

- Azure OpenAI
- OpenAI
- Anthropic
- Google Vertex AI

Purpose:

- Summarization
- Entity extraction
- Pattern analysis
- Insight generation

AI services remain subject to organizational governance.

---

## Notification Services

Examples:

- Email
- SMS
- Microsoft Teams
- Slack

Purpose:

- Alerts
- Workflow notifications
- Collaboration

---

# High-Level Context Diagram

```
                        +----------------------+
                        |     Business Users   |
                        +----------+-----------+
                                   |
                                   |
                                   v
        +------------------------------------------------+
        |                InsuranceNext                   |
        |------------------------------------------------|
        | Investigations                                |
        | Evidence                                      |
        | Relationships                                |
        | Insights                                      |
        | AI Analysis                                   |
        | Search                                        |
        | Reporting                                     |
        +------------------------------------------------+
          ^       ^         ^        ^         ^
          |       |         |        |         |
          |       |         |        |         |
  +-------+   +---+---+ +---+---+ +--+---+ +---+------+
  |Identity|  |Core   | |CRM   | |AI    | |External  |
  |Provider|  |Systems| |System| |Models| |Data      |
  +--------+  +-------+ +------+ +------+ +----------+
```

This diagram illustrates the external environment surrounding the platform rather than internal architecture.

---

# Information Flows

Major information exchanges include:

### Incoming

- User authentication
- Policy data
- Claim information
- Customer records
- External verification data
- AI responses

### Outgoing

- Investigation updates
- Reports
- Notifications
- Audit information
- Search requests
- AI prompts
- Integration events

---

# Trust Boundaries

The platform establishes trust boundaries between:

- External users
- Enterprise identity providers
- InsuranceNext services
- AI providers
- External data providers
- Internal data stores

Every boundary requires authentication, authorization, and secure communication.

---

# Security Considerations

External interactions should satisfy the following principles:

- Authentication required
- Least privilege
- Encryption in transit
- Encryption at rest
- Audit logging
- API security
- Zero Trust principles
- Secure integration patterns

---

# Architectural Principles

The system context follows these principles:

- API-first integration
- Loosely coupled external systems
- Provider independence
- Event-driven communication where appropriate
- AI as an advisory capability
- Explicit trust boundaries

---

# Relationship to Other Documents

| Document | Relationship |
|----------|--------------|
| Architecture Overview | Defines the overall architectural vision. |
| Container Architecture | Defines the deployable components within the system boundary. |
| Integration Architecture | Describes integration mechanisms with external systems. |
| Security Architecture | Defines trust boundaries and security controls. |
| AI Architecture | Describes AI provider interactions. |
| Deployment Architecture | Defines runtime environments. |

---

# Out of Scope

This document does not define:

- Internal application components
- Service decomposition
- Database architecture
- API specifications
- Technology stack
- Deployment topology

These topics are covered in later architecture documents.

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-29 | Initial system context defining the InsuranceNext ecosystem and external interactions. |