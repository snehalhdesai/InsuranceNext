# Document Template

> Standard template for all documentation within the InsuranceNext repository.

**Version:** 1.0  
**Status:** Active  
**Owner:** Architecture Team

---

# Purpose

This template establishes the standard structure for all documentation within the InsuranceNext repository.

Consistent documentation improves:

- Readability
- Discoverability
- AI reasoning
- Cross-referencing
- Long-term maintenance

Every new document should follow this structure unless there is a compelling reason not to.

---

# Standard Template

```markdown
# Document Title

> One sentence describing the document.

**Version:** 1.0
**Status:** Draft | Active | Deprecated
**Owner:** Team or Role

---

# Purpose

Why this document exists.

---

# Scope

What this document covers.

What it does not cover.

---

# Overview

High-level explanation.

---

# Detailed Description

Main content.

Organize into logical sections.

---

# Design Principles

If applicable.

---

# Business Rules

If applicable.

---

# Technical Considerations

If applicable.

---

# Dependencies

Related documents.

---

# References

Cross-reference other repository documents.

---

# Future Enhancements

Optional.

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | YYYY-MM-DD | Initial version |
```

---

# Document Metadata

Every document begins with:

```
Title

One-line summary

Version

Status

Owner
```

Example

```
# Evidence

> Defines the Evidence domain object.

Version: 1.0

Status: Active

Owner: Platform Architecture
```

---

# Status Values

Allowed status values are:

```
Draft

Active

Deprecated

Archived
```

Only one status should be assigned to a document.

---

# Versioning

Documentation follows semantic versioning.

Examples:

```
1.0

1.1

1.2

2.0
```

Major version changes indicate substantial revisions.

Minor versions indicate additions or clarifications.

---

# Heading Hierarchy

Use headings consistently.

```
#

##

###

####
```

Avoid skipping heading levels.

---

# Writing Style

Documentation should be:

- Clear
- Concise
- Objective
- Technically accurate
- Vendor-neutral where practical

Avoid:

- Marketing language
- Personal opinions
- Ambiguous terminology
- Duplicate explanations

---

# Formatting Rules

Use:

- Bullet lists for short enumerations.
- Tables for structured comparisons.
- Code blocks for commands and examples.
- Diagrams when they significantly improve understanding.

Avoid large walls of text.

---

# Cross References

Whenever another document defines a concept, reference that document instead of repeating its content.

Example:

```
See:

docs/02-Domain-Model/Evidence.md
```

This keeps documentation synchronized and reduces duplication.

---

# Diagrams

Preferred diagram types:

- System Context
- Container Diagram
- Sequence Diagram
- Entity Relationship Diagram
- Workflow Diagram
- State Diagram

Diagrams should be stored in:

```
diagrams/
```

Documentation should reference diagrams rather than embedding generated images.

---

# Code Examples

Code examples should:

- Compile where possible.
- Be minimal.
- Focus on one concept.
- Match the project's coding standards.

---

# Tables

Prefer tables for:

- API fields
- Configuration values
- Comparison matrices
- Permissions
- Status definitions

Keep tables concise and readable.

---

# Revision History

Every document should include a revision history.

Example:

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-26 | Initial document |
| 1.1 | 2026-08-10 | Added API examples |

---

# Review Process

Before committing a document, verify:

- Purpose is clear.
- Scope is defined.
- Terminology matches the Glossary.
- Engineering Standards are followed.
- References are correct.
- Formatting is consistent.
- Revision history is updated.

---

# Related Documents

- README.md
- AI_INDEX.md
- Glossary.md
- Engineering-Standards.md

---

# Revision History

| Version | Date | Description |
|----------|------|-------------|
| 1.0 | 2026-07-26 | Initial document template established. |