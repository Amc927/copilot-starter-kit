---
name: "Java Engineering"
description: "Engineering standards and best practices for building production-grade backend software using Java."
---

# Java Engineering Skill

## Purpose

This skill provides standards, patterns, best practices, and engineering guidance for building production-grade backend software using Java.

It applies to:

- Backend services
- REST APIs
- Business applications
- Microservices
- Batch processes
- Database integrations
- External service integrations
- Enterprise applications

---

# Activation Rules

Use this skill when:

- The repository already contains Java source code.
- A `pom.xml`, `build.gradle`, or `build.gradle.kts` file is present.
- The user explicitly requests Java.
- The Solution Architect selects Java and documents the decision.
- Java is required by an existing application, platform, service, or integration.

Do NOT select Java only because this skill is available.

Prefer the technology already used by the repository unless a technology change has been explicitly requested and approved.

If the repository technology cannot be determined, report the missing information before making a technology recommendation.

---

# Mandatory Repository Inspection

Before recommending or implementing Java changes, inspect the repository for:

- `pom.xml`
- `build.gradle`
- `build.gradle.kts`
- `.java-version`
- `Dockerfile`
- CI/CD configuration
- Existing Java source code
- Existing tests
- Application configuration
- Database configuration
- Existing architecture documentation
- README files
- Existing API specifications

Determine from repository evidence:

- Java version
- Framework
- Build system
- Project structure
- Testing framework
- Persistence technology
- Security mechanisms
- Logging framework
- Existing architectural conventions

Repository evidence takes precedence over generic recommendations.

Never invent missing project information.

---

# Java Version

Always use the Java version defined by the repository.

Do not silently change or upgrade the Java version.

For a new project where no version has been defined, the selected Java version must be justified considering:

- Runtime support
- Corporate compatibility
- Framework compatibility
- Deployment environment
- Dependency compatibility
- Maintenance lifecycle

A Java version upgrade must be treated as an explicit technical change.

---

# Framework Detection

Detect the framework from repository dependencies and configuration.

Possible frameworks may include:

- Spring Boot
- Jakarta EE
- Quarkus
- Micronaut
- Other Java frameworks already present in the repository

Do NOT assume Spring Boot if repository evidence indicates another framework.

Do NOT introduce or replace an application framework without an approved architectural decision.

When Spring Boot is detected, preserve the Spring Boot version and conventions already used by the application unless a migration has been explicitly approved.

---

# Core Engineering Principles

Always apply:

- Readability
- KISS
- YAGNI
- DRY pragmatically
- SOLID pragmatically
- Separation of concerns
- Explicit dependencies
- Clear responsibility boundaries
- Immutability where practical
- Constructor-based dependency injection
- Clear transaction boundaries
- Consistent error handling
- Testable design

Prefer simple and explicit solutions over unnecessary abstraction.

Avoid:

- Excessive inheritance
- Hidden side effects
- Static mutable state
- God classes
- Unnecessary design patterns
- Premature abstraction
- Framework-specific logic inside domain rules when avoidable
- Generic exception handling
- Unbounded concurrency

---

# Architecture Compliance

The Java implementation must respect the architecture already defined for the application.

The Backend Engineer is an executor of the approved architecture, not the owner of architectural redesign.

Do NOT:

- Change system boundaries.
- Introduce microservices into a monolith without approval.
- Merge services without approval.
- Introduce new architectural patterns without approval.
- Change persistence technology without approval.
- Replace synchronous communication with asynchronous messaging without approval.
- Change API boundaries without impact analysis.

Architectural changes must be escalated to the Solution Architect.

---

# Project Structure

First preserve the structure already used by the repository.

A possible Java structure is:

```text
src/
├── main/
│   ├── java/
│   │   └── application/
│   │       ├── api/
│   │       ├── application/
│   │       ├── domain/
│   │       └── infrastructure/
│   └── resources/
│
└── test/
    └── java/
```

This is an example, not a mandatory structure.

Do NOT reorganize an existing codebase only to make it match this example.

Repository conventions take precedence.

---

# Build and Dependency Management

Use the build system already present in the repository.

Supported examples include:

- Maven
- Gradle

Always:

- Preserve existing build conventions.
- Control dependency versions.
- Review transitive dependencies.
- Avoid duplicate libraries with overlapping responsibilities.
- Check compatibility before dependency upgrades.
- Document newly introduced dependencies.
- Review security impact of new dependencies.

Do NOT introduce a new build tool without explicit architectural approval.

Never invent:

- Corporate Maven repositories
- Corporate Gradle repositories
- Internal dependencies
- Artifact coordinates
- Internal library names

If an internal dependency is referenced but documentation is unavailable, report the missing information instead of guessing.

---

# Coding Standards

## Naming

Use:

```text
PascalCase
```

for:

- Classes
- Records
- Interfaces
- Enums

Use:

```text
camelCase
```

for:

- Variables
- Methods
- Parameters

Use:

```text
UPPER_SNAKE_CASE
```

for:

- Constants

Packages should use lowercase names.

Names must express business intent.

Avoid generic names such as:

- Manager
- Helper
- Utils
- Processor
- Common
- Misc

unless responsibility is clearly defined.

---

# Classes and Methods

Prefer:

- Small cohesive classes
- Short methods
- One clear responsibility
- Explicit input and output types
- Immutable value objects
- Records where appropriate
- Constructor injection
- Clear public contracts

Review classes that:

- Have too many responsibilities
- Depend on many unrelated services
- Mix infrastructure and business logic
- Contain excessive mutable state

Review methods that:

- Mix business and infrastructure logic
- Have excessive branching
- Modify unrelated state
- Require many parameters
- Perform hidden external calls

---

# Dependency Injection

Use the dependency injection mechanism already established by the project.

Prefer constructor-based dependency injection.

Avoid:

- Hidden dependencies
- Global mutable dependencies
- Service locator patterns
- Unnecessary static dependencies

Dependencies should be explicit and testable.

---

# API Development

For REST APIs:

- Follow existing API conventions.
- Use explicit request models.
- Use explicit response models.
- Do not expose persistence entities directly.
- Validate input at system boundaries.
- Use correct HTTP methods.
- Use meaningful HTTP status codes.
- Preserve backward compatibility when required.
- Keep endpoints predictable.
- Keep error responses consistent.
- Update API documentation when contracts change.

API contract changes require review from:

- Backend Engineer
- Security Engineer
- QA Engineer
- Code Reviewer

If frontend applications consume the API, evaluate frontend impact.

---

# Data Validation

Validate:

- API input
- Configuration
- External service responses
- File content
- Database input
- Business invariants
- Integration boundaries

Use the validation mechanisms already selected by the project.

Do not duplicate the same business validation inconsistently across:

- Controllers
- Services
- Repositories
- Database access layers

Never trust external input.

---

# Error Handling

Always:

- Use meaningful exceptions.
- Distinguish business errors from technical failures.
- Preserve root cause internally.
- Map errors into stable API responses.
- Produce actionable logs.
- Handle expected failures explicitly.

Never:

- Return stack traces to clients.
- Catch and silently ignore exceptions.
- Use generic `Exception` as the normal business error mechanism.
- Expose database implementation details.
- Expose credentials.
- Expose secrets.
- Expose internal paths.
- Expose sensitive personal information.

---

# Logging

Use the logging framework already configured by the project.

Use structured and parameterized logging where supported.

Log:

- Application startup
- Application shutdown
- Important business events
- External integrations
- Relevant failures
- Security-relevant events where appropriate
- Correlation identifiers when available

Never log:

- Passwords
- Secrets
- Tokens
- Authentication headers
- Sensitive personal data
- Credentials

Avoid string concatenation for structured log messages.

---

# Database Access

Follow the persistence technology already used by the repository.

Possible technologies may include:

- JPA
- Hibernate
- JDBC
- Spring Data
- Other technologies already present in the project

Do not replace persistence technology without approval.

Always:

- Use parameterized queries.
- Define transaction boundaries.
- Avoid N+1 query patterns.
- Apply pagination to potentially large datasets.
- Review query performance.
- Consider indexes for new access patterns.
- Separate persistence models from external API contracts where appropriate.
- Handle connection and transaction failures explicitly.

Avoid:

- Dynamic SQL built by unsafe string concatenation
- Unbounded queries
- Loading large datasets into memory unnecessarily

---

# Database Schema Changes

Database changes require:

- Migration strategy
- Compatibility assessment
- Data integrity assessment
- Rollback consideration
- Performance assessment
- Deployment coordination

Do not assume schema changes are safe simply because application code compiles.

Changes affecting critical business data require additional Security, QA, DevOps, and Code Reviewer validation.

---

# External Service Integration

When integrating external services:

- Define explicit contracts.
- Validate responses.
- Configure timeouts.
- Define retry behaviour.
- Avoid unbounded retries.
- Handle partial failure.
- Protect credentials.
- Log failures without exposing sensitive information.
- Consider idempotency where relevant.

Do not assume external services are always available.

---

# Testing Strategy

Use the testing frameworks already configured by the repository.

Typical Java testing technologies may include:

- JUnit
- Mockito
- Spring testing tools
- Integration test frameworks already present in the project

Do not introduce a new testing framework unnecessarily.

## Unit Tests

Cover:

- Business logic
- Domain rules
- Utility functions
- Validation
- Edge cases
- Error conditions

## Integration Tests

Cover:

- Database interaction
- API endpoints
- Framework configuration
- External integration boundaries

## Contract Tests

Use when APIs or service contracts are involved.

## Testing Rules

Tests must be:

- Deterministic
- Repeatable
- Readable
- Independent where practical
- Focused on observable behaviour

Avoid testing internal implementation details unnecessarily.

Do not replace meaningful tests with excessive mocking.

---

# Concurrency and Async Processing

Before introducing:

- Threads
- Virtual threads
- Reactive programming
- Async processing
- Queues
- Parallel execution

evaluate:

- Actual workload
- Existing concurrency model
- Transaction propagation
- Security context propagation
- Error handling
- Retry behaviour
- Resource limits
- Observability
- Deployment implications

Do not introduce concurrency only to appear more scalable.

---

# Performance Guidelines

Optimize only after identifying a measurable bottleneck or clear scalability risk.

Evaluate:

- Database queries
- Connection pools
- Serialization
- External calls
- Thread pools
- Memory usage
- Garbage collection behaviour
- Cache behaviour
- Batch sizes
- Timeout policies
- Retry policies

Avoid unbounded:

- Collections
- Queues
- Retries
- Parallelism
- Cache growth

Performance changes should be coordinated with the Performance Engineer.

---

# Security Guidelines

Apply:

- OWASP principles
- Least privilege
- Input validation
- Output encoding
- Secure secret management
- Explicit authorization
- Dependency security review
- Secure communication
- Safe error handling

Never:

- Hardcode credentials.
- Trust authorization information provided by clients.
- Disable TLS certificate validation.
- Expose internal stack traces.
- Build SQL through unsafe concatenation.
- Store secrets in source code.
- Log credentials or tokens.

Authentication and authorization changes require Security Engineer review.

Critical security findings block production approval.

---

# Configuration

Configuration must:

- Be externalized where appropriate.
- Separate environment-specific values.
- Protect secrets.
- Have sensible validation.
- Fail clearly when required configuration is missing.

Do not hardcode environment-specific URLs, credentials, or production secrets.

Use the configuration mechanism already present in the application.

---

# Documentation Requirements

Every production component should document:

- Purpose
- Inputs
- Outputs
- Dependencies
- Configuration
- External integrations
- Error behaviour
- Security considerations
- Operational limitations

API changes require updated API contract documentation.

Database changes require updated migration and operational documentation.

---

# Technical Debt

Identify technical debt encountered during implementation.

For each relevant item document:

- Problem
- Impact
- Risk
- Recommended remediation

Do not silently expand scope to fix unrelated technical debt.

Significant technical debt should be reported to the Orchestrator.

---

# Output Format

When this skill is used, provide:

## Technology Detection

Report:

- Java version
- Framework
- Build system
- Persistence technology
- Testing framework
- Evidence found in repository

## Implementation Approach

Explain:

- Components affected
- Layers involved
- Existing patterns being followed
- New implementation required

## Dependencies

Report:

- Existing dependencies used
- New dependencies proposed
- Compatibility considerations

## API and Data Impact

Report:

- API contract changes
- Database changes
- Integration changes

## Testing Strategy

Report:

- Unit tests
- Integration tests
- Contract tests
- Regression impact

## Security and Performance

Report relevant:

- Security considerations
- Performance considerations
- Operational implications

## Technical Debt

Report:

- Existing debt discovered
- New debt introduced, if any
- Recommended remediation

## Missing Information

Report explicitly:

- Missing corporate standards
- Missing internal dependency documentation
- Missing deployment information
- Missing API documentation

Never invent missing information.

---

# Definition of Done

A Java implementation is complete when:

- Repository Java version is respected.
- Existing framework conventions are respected.
- Existing architecture is respected.
- Code compiles.
- Tests pass.
- Input validation exists.
- Errors are handled explicitly.
- Logging is safe and useful.
- Security considerations are addressed.
- Database impact is assessed.
- API contracts are updated when applicable.
- Deployment impact is understood.
- Documentation is updated.
- Technical debt is documented.