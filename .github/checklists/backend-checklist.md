# Backend Technical Review Checklist

## Purpose

Used by the Backend Engineer to validate backend implementation quality, technology alignment, architecture compliance, correctness, security awareness, maintainability, testing, and production readiness.

This checklist is technology-neutral.

Technology-specific validation must additionally follow the active engineering skill:

- Python Engineering Skill
- Java Engineering Skill
- Python MCP Engineering Skill when MCP is involved

For each section use:

PASS
FAIL
NOT APPLICABLE

A FAIL in a critical section must be reported to the Orchestrator.

---

# Technology Detection

- [ ] Backend technology identified from repository evidence
- [ ] Framework identified when applicable
- [ ] Relevant runtime/version identified
- [ ] Build or dependency management system identified
- [ ] Existing repository technology preserved unless an approved change exists
- [ ] Active engineering skill identified
- [ ] Technology selection supported by repository evidence or approved architecture
- [ ] No corporate technology, dependency, or standard assumed without evidence

Active backend technology:

`Python / Java / Other / Not determined`

Active skills:

`Python Engineering / Java Engineering / Python MCP Engineering / Other`

Result:

PASS / FAIL / N/A

---

# MCP Applicability

Apply only when MCP is involved.

- [ ] MCP requirement explicitly identified
- [ ] MCP is justified by an integration or agent-tooling requirement
- [ ] Python Engineering Skill also applied
- [ ] Python MCP Engineering Skill applied
- [ ] MCP tools, resources, or prompts identified
- [ ] MCP permissions and security boundaries evaluated
- [ ] Tool side effects identified
- [ ] MCP input and output contracts validated
- [ ] External or retrieved content treated as untrusted
- [ ] MCP-specific tests defined
- [ ] MCP contracts documented

Result:

PASS / FAIL / N/A

---

# Requirements Understanding

- [ ] Business requirements understood
- [ ] Acceptance criteria identified
- [ ] Scope clearly defined
- [ ] Assumptions documented
- [ ] Missing requirements identified
- [ ] Open questions resolved or explicitly reported
- [ ] Implementation does not depend on invented requirements

Result:

PASS / FAIL / N/A

---

# Architecture Compliance

- [ ] Existing architecture respected
- [ ] Approved technology decision respected
- [ ] Service boundaries respected
- [ ] Data ownership boundaries respected
- [ ] Security boundaries respected
- [ ] No unnecessary coupling introduced
- [ ] Separation of concerns maintained
- [ ] No unauthorized architectural pattern introduced
- [ ] Architectural conflicts escalated to the Solution Architect
- [ ] No silent technology migration introduced

Result:

PASS / FAIL / N/A

---

# Implementation Quality

- [ ] Implementation follows the active engineering skill
- [ ] Code is readable
- [ ] Naming is meaningful
- [ ] Responsibilities are clear
- [ ] No duplicated business logic introduced unnecessarily
- [ ] Complexity is appropriate
- [ ] Dependencies are explicit
- [ ] Existing repository conventions are respected
- [ ] No unnecessary abstraction introduced
- [ ] No material dead code introduced

Result:

PASS / FAIL / N/A

---

# Business Logic

- [ ] Business rules correctly implemented
- [ ] Business invariants preserved
- [ ] Edge cases handled
- [ ] Null or empty values handled where relevant
- [ ] Invalid states handled
- [ ] Failure scenarios handled
- [ ] Unexpected external responses considered
- [ ] Business logic separated appropriately from infrastructure concerns

Result:

PASS / FAIL / N/A

---

# API Design

Apply when APIs are involved.

- [ ] Endpoint naming consistent with existing API conventions
- [ ] HTTP methods correctly used
- [ ] Request contracts explicitly defined
- [ ] Request validation exists
- [ ] Response contracts explicitly defined
- [ ] Structured error contracts defined
- [ ] Internal persistence models not unnecessarily exposed
- [ ] Authentication requirements considered
- [ ] Authorization requirements considered
- [ ] Backward compatibility evaluated
- [ ] API versioning evaluated when compatibility requires it
- [ ] API documentation updated
- [ ] Frontend or external consumers impact identified

Result:

PASS / FAIL / N/A

---

# Input Validation

- [ ] External input treated as untrusted
- [ ] Required fields validated
- [ ] Types validated
- [ ] Formats validated
- [ ] Ranges and limits validated where applicable
- [ ] Business constraints validated
- [ ] External service responses validated where necessary
- [ ] Validation errors produce predictable behaviour

Result:

PASS / FAIL / N/A

---

# Error Handling

- [ ] Expected failures handled explicitly
- [ ] Exceptions are meaningful
- [ ] Errors provide actionable information
- [ ] Internal implementation details are not exposed
- [ ] Stack traces are not exposed to consumers
- [ ] Sensitive configuration is not included in errors
- [ ] External dependency failures handled
- [ ] Timeout behaviour considered
- [ ] Retry behaviour evaluated
- [ ] Duplicate execution risk evaluated for state-changing operations
- [ ] Failure scenarios documented when operationally relevant

Result:

PASS / FAIL / N/A

---

# Data Access Layer

Apply when persistence is involved.

- [ ] Existing persistence architecture respected
- [ ] Queries reviewed
- [ ] Queries parameterized where applicable
- [ ] Transactions handled correctly
- [ ] Data consistency verified
- [ ] Data integrity maintained
- [ ] Database permissions considered
- [ ] N+1 query risk evaluated
- [ ] Large result sets bounded or paginated
- [ ] Concurrency implications evaluated where relevant
- [ ] Persistence models appropriately separated from external contracts

Result:

PASS / FAIL / N/A

---

# Database Changes

Apply when database schema or stored data is affected.

- [ ] Schema changes identified
- [ ] Migration strategy defined
- [ ] Existing data impact evaluated
- [ ] Data integrity impact evaluated
- [ ] Backward compatibility evaluated
- [ ] Deployment ordering considered
- [ ] Rollback implications evaluated
- [ ] Performance impact evaluated
- [ ] Migration documented

Result:

PASS / FAIL / N/A

---

# External Integrations

Apply when external services or systems are involved.

- [ ] Integration contract understood
- [ ] Authentication requirements identified
- [ ] Authorization requirements identified
- [ ] Request validation implemented
- [ ] Response validation considered
- [ ] Timeout configured or evaluated
- [ ] Retry behaviour evaluated
- [ ] Rate limits considered where applicable
- [ ] Partial failure considered
- [ ] Duplicate execution considered
- [ ] Sensitive information protected
- [ ] External failure behaviour documented where necessary

Result:

PASS / FAIL / N/A

---

# Dependency Review

- [ ] New dependencies justified
- [ ] Existing capability checked before introducing a dependency
- [ ] Existing framework capability checked
- [ ] Dependency compatibility evaluated
- [ ] Runtime compatibility evaluated
- [ ] Security implications considered
- [ ] Transitive dependency impact considered where relevant
- [ ] Unnecessary dependency duplication avoided
- [ ] Corporate dependencies not invented
- [ ] Dependency changes documented

Result:

PASS / FAIL / N/A

---

# Security Awareness

Backend review does not replace Security Engineer review.

- [ ] Input validation exists
- [ ] Authentication impact reviewed
- [ ] Authorization impact reviewed
- [ ] Least privilege considered
- [ ] Secret handling reviewed
- [ ] Sensitive data exposure reviewed
- [ ] Injection risks considered
- [ ] Dependency security implications considered
- [ ] Sensitive information not exposed through errors or logs
- [ ] Security boundary changes identified
- [ ] Security Engineer involvement requested when necessary
- [ ] Critical security findings are not bypassed

Result:

PASS / FAIL / N/A

---

# Logging And Observability

- [ ] Significant operational events logged where appropriate
- [ ] Important business events logged where appropriate
- [ ] Error conditions logged appropriately
- [ ] Sensitive information not logged
- [ ] Credentials not logged
- [ ] Tokens not logged
- [ ] Authentication headers not logged
- [ ] Correlation or trace identifiers considered where available
- [ ] Monitoring impact evaluated
- [ ] Troubleshooting information is sufficient for production operation

Result:

PASS / FAIL / N/A

---

# Performance Awareness

Backend review does not replace Performance Engineer review.

- [ ] Expensive operations identified
- [ ] Database impact reviewed
- [ ] External calls reviewed
- [ ] Large dataset impact reviewed
- [ ] Serialization impact considered where relevant
- [ ] Memory consumption considered where relevant
- [ ] Connection or worker pool implications considered
- [ ] Timeout and retry impact considered
- [ ] Unbounded operations avoided
- [ ] Potential bottlenecks documented
- [ ] Significant performance concerns escalated to Performance Engineer

Result:

PASS / FAIL / N/A

---

# Testing Review

- [ ] Unit tests exist where appropriate
- [ ] Business rules tested
- [ ] Edge cases tested
- [ ] Failure cases tested
- [ ] Integration tests exist where appropriate
- [ ] API integration tested where applicable
- [ ] Database interaction tested where applicable
- [ ] External integration boundaries tested where applicable
- [ ] Contract tests exist where applicable
- [ ] Regression tests added for defect fixes where practical
- [ ] Tests are deterministic
- [ ] Tests avoid unnecessary implementation coupling
- [ ] Tests do not depend on production credentials
- [ ] Test coverage gaps documented
- [ ] Active technology skill testing requirements satisfied
- [ ] Test existence distinguished from test execution
- [ ] Tests not executed explicitly reported as NOT EXECUTED
- [ ] Missing test evidence not treated as PASS

Unit Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Integration Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Contract Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Regression Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Technical Debt Review

- [ ] Existing technical debt relevant to the change identified
- [ ] New technical debt avoided where practical
- [ ] Unavoidable new technical debt documented
- [ ] Debt impact described
- [ ] Debt risk described
- [ ] Remediation recommendation provided
- [ ] Blocking versus non-blocking debt distinguished
- [ ] Significant unrelated debt kept outside the current scope
- [ ] Separate tracking recommended where appropriate

Result:

PASS / FAIL / N/A

---

# Documentation Review

- [ ] Implementation documentation updated where necessary
- [ ] API documentation updated where applicable
- [ ] Configuration documented
- [ ] New dependencies documented
- [ ] Database changes documented
- [ ] External integration requirements documented
- [ ] Operational limitations documented
- [ ] Missing corporate information explicitly identified
- [ ] MCP contracts documented when MCP is involved

Result:

PASS / FAIL / N/A

---

# Deployment Impact

- [ ] Configuration changes identified
- [ ] Environment variables documented
- [ ] Secret configuration impact identified
- [ ] Runtime changes identified
- [ ] Dependency changes identified
- [ ] Backward compatibility assessed
- [ ] Database migration requirements identified
- [ ] Deployment ordering considered
- [ ] External service dependencies considered
- [ ] Rollback implications documented
- [ ] DevOps review requested when deployment risk requires it

Result:

PASS / FAIL / N/A

---

# Critical Backend Gates

The Backend Engineer must not recommend approval when any applicable critical condition exists:

- [ ] No unresolved critical implementation defect
- [ ] No known material data-integrity risk
- [ ] No known material data-loss risk
- [ ] No broken mandatory API contract
- [ ] No unresolved critical security concern
- [ ] No unsafe database migration
- [ ] No incompatible technology change without architectural approval
- [ ] No missing mandatory validation
- [ ] No knowingly failing mandatory core test
- [ ] No unsafe MCP capability when MCP is involved

If any applicable item fails, report it explicitly to the Orchestrator.

Result:

PASS / FAIL / N/A

---

# Evidence Summary

Backend Technology:

`Python / Java / Other / Not determined`

Framework:

`_____________________`

Framework Version:

`_____________________`

Active Engineering Skills:

`_____________________`

Repository Evidence:

`_____________________`

Unit Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Integration Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Contract Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Regression Tests:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Tests Not Executed:

`_____________________`

Known Limitations:

`_____________________`

Missing Information:

`_____________________`

---

# Final Backend Recommendation

Use the same decision vocabulary as the Orchestrator.

Allowed values:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Recommendation:

`_____________________`

---

# Technical Risk Assessment

Allowed values:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

Risk:

`_____________________`

Main Risk Drivers:

`_____________________`

---

# Backend Review Result

Allowed values:

```text
PASSED
CONDITIONAL
FAILED
```

Result:

`_____________________`

---

# Backend Engineer Sign-Off

Reviewer:

`_____________________`

Date:

`_____________________`

Result:

`PASSED / CONDITIONAL / FAILED`

Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO`

Conditions:

`________________________________________________`

Missing Evidence:

`________________________________________________`

Comments:

`________________________________________________`

`________________________________________________`

`________________________________________________`

---

# Definition of Backend Readiness

A backend implementation is considered ready for its intended lifecycle when:

- Backend technology has been identified from repository evidence or approved architecture.
- The appropriate engineering skill has been applied.
- Existing backend technology has been preserved unless a change was explicitly approved.
- Approved architecture and service boundaries have been respected.
- No unauthorized technology migration has been introduced.
- Business requirements and acceptance criteria are understood.
- Business rules and invariants are correctly implemented.
- External input is appropriately validated.
- Error behaviour is explicit and predictable.
- Sensitive implementation details are not exposed through errors.
- API contracts are explicit and compatible where applicable.
- Mandatory API contracts are not broken.
- Authentication requirements are respected where applicable.
- Authorization requirements are respected where applicable.
- Security-sensitive changes have been escalated to the Security Engineer when required.
- Secrets and credentials are handled safely.
- Data ownership and persistence boundaries are respected.
- Database queries are safe where applicable.
- Transactions preserve expected data integrity where applicable.
- Database migrations are defined and safe when applicable.
- External integrations handle expected failure scenarios.
- Timeouts and retry behaviour have been considered where applicable.
- Dependencies are justified and compatible.
- Corporate dependencies or standards have not been invented.
- Logging and observability are appropriate to operational requirements.
- Sensitive information is not unnecessarily logged.
- Performance implications have been considered.
- MCP has only been introduced when justified by an approved requirement.
- MCP permissions, contracts and side effects have been evaluated when applicable.
- Required tests exist.
- Required tests pass where execution evidence is available.
- Tests that were not executed are explicitly reported as NOT EXECUTED.
- Missing test evidence has not been treated as PASS.
- Build success has not been treated as proof of functional correctness.
- Relevant unit tests have been evaluated.
- Relevant integration tests have been evaluated.
- Relevant contract tests have been evaluated.
- Relevant regression tests have been evaluated.
- Technical debt is documented.
- Documentation is updated.
- Deployment impact is understood.
- Rollback implications are understood where applicable.
- Known limitations are explicit.
- Missing information and evidence are explicit.
- No applicable critical Backend Gate remains failed.
- Backend Review Result has been produced.
- Final Backend Recommendation is traceable to verified evidence.