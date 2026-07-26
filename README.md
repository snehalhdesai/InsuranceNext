# InsuranceNext

> Building the next generation AI-native insurance intelligence platform.

---

# Overview

InsuranceNext is an enterprise-grade, AI-native intelligence platform designed specifically for the insurance industry. The platform enables insurers, brokers, investigators, adjusters, compliance teams, fraud analysts, and underwriters to collect, organize, analyze, and act upon complex insurance information through a unified intelligence workspace.

Rather than functioning as a traditional policy administration or claims management system, InsuranceNext serves as the intelligence layer that connects people, evidence, relationships, investigations, insights, and AI into a single collaborative platform.

The platform is designed from the ground up using modern cloud-native architecture, domain-driven design, event-driven services, and AI-assisted workflows.

---

# Vision

InsuranceNext aims to become the operating system for insurance intelligence by enabling organizations to transform fragmented information into actionable knowledge.

The platform will support:

- Claims Investigation
- Fraud Detection
- Underwriting Intelligence
- Risk Assessment
- Compliance Management
- Customer Intelligence
- Case Management
- Document Intelligence
- Relationship Analysis
- AI Assisted Decision Support

---

# Repository Structure

```
InsuranceNext/

README.md
AI_INDEX.md

docs/
src/
database/
infrastructure/
scripts/
assets/
diagrams/
tests/
```

Detailed documentation is located under the `docs` directory.

---

# Documentation Structure

```
docs/

00-Project-Governance/
01-Vision/
02-Domain-Model/
03-Architecture/
04-Services/
05-API/
06-Backend/
07-Frontend/
08-Workflows/
09-Permissions/
10-ADR/
11-Operations/
12-Deployment/
13-Testing/
14-Product/
15-Future/
```

Each folder represents a logical area of the platform and should remain self-contained.

---

# Core Engineering Principles

InsuranceNext follows several architectural principles:

- Domain Driven Design (DDD)
- Clean Architecture
- Event Driven Architecture
- Microservice-Oriented Design
- API First Development
- AI Native Design
- Security by Design
- Cloud Native Deployment
- Infrastructure as Code
- Documentation as Code

These principles guide every architectural and implementation decision.

---

# Source of Truth

The GitHub repository is the authoritative source for:

- Architecture
- Domain Model
- APIs
- Backend Services
- Frontend Design
- Infrastructure
- Documentation
- ADRs (Architecture Decision Records)

No design decisions should exist only in conversations or personal notes. Once accepted, they should be documented and committed to the repository.

---

# Documentation Philosophy

Documentation should be:

- Complete
- Accurate
- Version controlled
- Self-contained
- Cross-referenced
- Easy for both humans and AI assistants to navigate

Documentation is considered part of the product and should evolve alongside the codebase.

---

# Development Workflow

The recommended workflow is:

1. Define or update the product vision.
2. Refine the domain model.
3. Update architecture documentation.
4. Implement backend services.
5. Build frontend functionality.
6. Add or update tests.
7. Update documentation.
8. Commit changes to Git.
9. Push changes to GitHub.

Documentation updates should accompany implementation whenever practical.

---

# Repository Standards

- Markdown (`.md`) is the standard format for documentation.
- One concept per document.
- Use descriptive filenames.
- Avoid duplicate documentation.
- Cross-reference related documents instead of repeating content.
- Maintain a consistent heading hierarchy.
- Prefer diagrams for complex flows where they add clarity.

---

# Branching Strategy

The default branch is:

```
main
```

Feature development should be performed in dedicated branches when multiple contributors are involved.

Example:

```
feature/evidence-service
feature/frontend-dashboard
feature/graph-engine
bugfix/authentication
```

For the initial documentation effort, work may be committed directly to `main` until the baseline documentation is complete.

---

# Current Status

Current project phase:

**Foundation Documentation**

Upcoming milestones:

- Foundation Documentation
- Domain Model
- Architecture
- Services
- APIs
- Backend
- Frontend
- Operations
- Deployment
- Testing
- Version 1.0 Baseline

---

# Contributing

All contributors should:

- Follow the documented architecture.
- Keep documentation synchronized with implementation.
- Record significant design decisions as ADRs.
- Maintain consistency in terminology and naming.

---

# License

License information will be defined prior to public release.

---

# Contact

Project Name:

**InsuranceNext**

Repository Owner:

_To be updated._

Repository URL:

_To be updated after GitHub initialization._