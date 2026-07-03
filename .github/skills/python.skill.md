# Python Engineering Skill

## Purpose

This skill provides standards, patterns, best practices, and engineering guidance for building production-grade software using Python.

It applies to:

- Backend services
- APIs
- Automation tools
- CLI applications
- AI/LLM systems
- Data processing applications
- Microservices

---

# Supported Python Version

Preferred:

- Python 3.12+

Minimum:

- Python 3.11

Avoid supporting legacy versions unless explicitly required.

---

# Core Engineering Principles

## Readability First

Code is read more often than it is written.

Prefer:

- explicit code
- clear naming
- small functions

Avoid:

- clever solutions
- implicit behavior
- unnecessary abstraction

---

## Simplicity

Apply:

- KISS
- YAGNI

Do not introduce complexity without measurable benefit.

---

## Strong Typing

Always use type hints.

Example:

```python
def calculate_total(items: list[Item]) -> Decimal:
    ...
```

Avoid:

```python
def calculate_total(items):
    ...
```

---

# Project Structure

Recommended layout:

```text
src/
│
├── api/
├── services/
├── repositories/
├── domain/
├── infrastructure/
├── schemas/
└── tests/
```

---

# Dependency Management

Preferred:

- uv
- poetry

Acceptable:

- pip

Avoid:

- unmanaged requirements
- global package installation

---

# Coding Standards

## Functions

Prefer:

- single responsibility
- less than 50 lines

Review if:

- more than 100 lines

---

## Classes

Create classes only when they represent:

- behavior
- state
- abstraction boundary

Avoid classes used only as namespaces.

---

## Naming

Use:

```python
snake_case
```

for:

- variables
- functions
- modules

Use:

```python
PascalCase
```

for:

- classes

Use:

```python
UPPER_CASE
```

for:

- constants

---

# Error Handling

Always:

- raise meaningful exceptions
- catch only expected failures
- provide actionable messages

Avoid:

```python
except Exception:
    pass
```

---

# Logging

Use structured logging.

Log:

- application startup
- external calls
- failures
- critical business events

Never log:

- passwords
- secrets
- tokens
- sensitive personal data

---

# API Development

Preferred framework:

- FastAPI

General principles:

- REST first
- explicit schemas
- validation at boundaries
- version APIs when necessary

Always use:

- request models
- response models
- OpenAPI generation

---

# Data Validation

Preferred:

```python
Pydantic
```

Validate:

- API inputs
- configuration
- external data

Never trust external input.

---

# Database Access

Preferred:

- SQLAlchemy

Always:

- parameterized queries
- explicit transactions
- connection pooling

Avoid:

- string concatenation SQL
- N+1 queries

---

# Testing Strategy

Framework:

```python
pytest
```

Required:

### Unit Tests

- business logic
- utility functions
- edge cases

### Integration Tests

- database interaction
- APIs
- external services

### Contract Tests

when APIs are involved

---

# Async Programming

Use async when:

- IO bound workloads
- APIs
- external services

Avoid async for:

- CPU intensive workloads

Preferred:

```python
asyncio
```

---

# Performance Guidelines

Optimize only after identifying bottlenecks.

Focus on:

- database queries
- network calls
- serialization cost
- memory consumption

Avoid premature optimization.

---

# Security Guidelines

Must follow:

- OWASP principles
- input validation
- least privilege
- secure secret management

Never:

- hardcode credentials
- expose stack traces
- trust user input

---

# AI / LLM Development

When building AI systems:

- validate prompts
- limit tool permissions
- sanitize retrieved content
- protect secrets
- log tool execution

Evaluate:

- hallucination risks
- prompt injection risks
- data leakage risks

---

# Documentation Requirements

Every production component must include:

- purpose
- inputs
- outputs
- dependencies
- limitations

---

# Definition of Done

A Python implementation is complete when:

- Code works.
- Tests pass.
- Types are defined.
- Logging exists.
- Validation exists.
- Security considerations are addressed.
- Documentation is updated.
- Technical debt is documented.