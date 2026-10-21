---
name: Release Decision Prompt
description: Evidence-based release decision framework used by the Orchestrator to determine whether a change is ready for its intended release lifecycle and target environment using applicable Quality Gates, verified evidence, human governance, and unresolved risk.
model: Auto (copilot)
---

# Release Decision Prompt

Version: 2.0

---

# Objective

Determine whether a software change, feature, bug fix, security remediation, infrastructure modification, documentation change, LLM capability, agentic capability, or release candidate is ready for its intended release context.

The review must determine readiness using:

- Verified release scope
- Intended lifecycle
- Target environment
- Verified requirements
- Actual specialist findings
- Applicable Quality Gates
- Test and evaluation evidence
- Security evidence
- Deployment evidence
- Performance evidence when applicable
- Documentation evidence when applicable
- Human approval when required
- Blocking findings
- Conditions
- Missing evidence
- Residual risk

This prompt does not replace specialist reviews.

The Orchestrator aggregates verified specialist and gate evidence and produces the final engineering decision.

---

# Governance References

Use:

`quality-gates.md`

to determine:

- Gate applicability
- Gate ownership
- Gate evidence requirements
- Gate states
- Gate aggregation

Use:

`decision-authority.md`

to determine:

- Domain authority
- Conflict resolution
- Human governance
- Formal risk-treatment boundaries
- Final engineering decision rules

Use:

`release-checklist.md`

to consolidate release-readiness evidence.

Use:

`decision-log-template.md`

when a material decision requires a Decision Log.

Use:

`traceability-model.md`

for lifecycle-appropriate traceability.

Do not redefine governance rules inside the release decision.

---

# Core Decision Principles

Always apply:

- Evidence before approval
- Lifecycle-aware readiness
- Target-environment awareness
- Domain-specific authority
- Applicable gates only
- Critical blockers remain blocking
- Explicit conditions
- Explicit missing evidence
- Human control proportional to risk
- No fabricated execution
- No fabricated approval
- No fabricated risk acceptance

Mandatory rules:

```text
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
DEFINED != EXECUTED
TEST EXISTS != TEST PASSED
BUILD PASSED != QA PASSED
SONARQUBE PASSED != SECURITY APPROVAL
GATE NOT APPLICABLE != GATE PASSED
AGENT DEFINED != AGENT PARTICIPATED
PLANNED DEPLOYMENT != SUCCESSFUL DEPLOYMENT
RESIDUAL RISK RECORDED != FORMAL RISK ACCEPTED
```

Feature-delivery pressure must not override an applicable critical blocker.

There is no universal specialist or Quality Gate priority hierarchy.

---

# Release Context

Before making a decision identify:

- Release objective
- Lifecycle
- Target environment
- Change type
- Release scope
- Business criticality
- Affected systems
- Affected users when relevant
- Main risks
- Deployment intent

Lifecycle:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Possible change types:

```text
FEATURE
BUG FIX
REFACTOR
SECURITY
INFRASTRUCTURE
DOCUMENTATION
PERFORMANCE
LLM
AGENTIC
MIXED
```

If lifecycle or target environment is answer-critical and cannot be determined:

`NEEDS MORE INFO`

may be required.

---

# Lifecycle-Aware Release Decision

## Experiment

Prioritize:

- Objective achieved
- Critical correctness
- Critical safety
- Evidence sufficient for the experiment
- Limitations explicit

Do not require production readiness unless production behaviour is itself being evaluated.

## Prototype / PoC

Prioritize:

- Business or technical objective validated
- Critical workflows validated
- Critical data behaviour validated
- Critical security boundaries validated
- Limitations explicit
- Production assumptions explicit

Do not interpret successful PoC execution as production approval.

## MVP

Evaluate appropriate:

- Core functionality
- Security
- Regression risk
- Deployment
- Maintainability
- Important integrations
- Operational needs
- Documentation

## Production

Require sufficient evidence from every materially applicable production gate.

Evaluate appropriate:

- Architecture
- Backend
- Frontend
- Security
- QA
- Code Review
- DevOps
- Performance
- Documentation
- LLM
- Agentic

Do not require irrelevant gates merely because the environment is production.

---

# Release Scope

Verify:

- Included changes
- Excluded changes
- Affected repositories
- Affected components
- Affected services
- Affected frontend applications
- APIs
- Data or database changes
- Infrastructure changes
- Configuration changes
- External integrations
- Dependencies
- Deployment ordering

Do not represent planned or incomplete work as released implementation.

When scope cannot be verified safely:

`NEEDS MORE INFO`

---

# Requirements Review

Separate:

```text
Verified requirements
Assumptions
Constraints
Missing information
```

Evaluate:

- Business objective
- Acceptance criteria
- Functional requirements
- Security requirements
- Performance requirements
- Operational requirements
- Accessibility requirements when applicable

Do not approve against invented requirements.

---

# Participating Agents

List only agents that actually participated.

Possible specialists include:

- Solution Architect
- Backend Engineer
- Frontend Systems Engineer
- Security Engineer
- QA Engineer
- Code Reviewer
- DevOps Engineer
- Performance Engineer
- Documentation Engineer

Do not report an agent as participating merely because the agent exists or its gate could theoretically apply.

---

# Active Skills

List only skills actually applicable and used.

Possible skills include:

- Python Engineering Skill
- Java Engineering Skill
- Python MCP Engineering Skill
- Endesa Corporate Angular Engineering Skill
- LLM Engineering Skill
- Agentic Systems Engineering Skill

Skill availability does not prove skill activation.

---

# Gate Applicability Review

Determine gate applicability using:

`quality-gates.md`

Possible applicability values:

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

Evaluate:

- Architecture Gate
- Backend Gate
- Frontend Gate
- Security Gate
- QA Gate
- Code Review Gate
- DevOps Gate
- Performance Gate
- Documentation Gate
- LLM Gate
- Agentic Gate

Do not mark an irrelevant gate as PASSED.

Do not avoid an inconvenient gate by incorrectly marking it NOT APPLICABLE.

---

# Gate Status Vocabulary

Use:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## PASSED

Required evidence exists and no blocking domain finding remains.

## CONDITIONAL

No critical blocker remains, but explicit non-blocking conditions exist.

## FAILED

An applicable mandatory or critical blocker remains.

## NOT EXECUTED

The applicable evaluation was not performed.

## NOT AVAILABLE

Required evidence cannot currently be verified.

## NOT APPLICABLE

The gate does not apply.

Never convert:

```text
NOT EXECUTED
NOT AVAILABLE
```

into:

```text
PASSED
```

---

# Architecture Gate Review

When Architecture Gate applies, review:

- Gate status
- Approved architecture
- Technology decisions
- System boundaries
- Data ownership
- Integration design
- Deployment architecture
- Prototype-to-production assumptions
- Blocking architecture findings
- Conditions
- Missing evidence

Owner:

`Solution Architect`

Do not replace architecture authority.

---

# Backend Gate Review

When Backend Gate applies, review:

- Gate status
- Backend technology
- Architecture compliance
- Business logic
- APIs
- Data integrity
- Persistence
- Integrations
- Backend tests
- Blocking findings
- Conditions
- Missing evidence

Owner:

`Backend Engineer`

---

# Frontend Gate Review

When Frontend Gate applies, review:

- Gate status
- Frontend technology
- Lifecycle suitability
- Critical workflows
- API compatibility
- State
- Forms
- Accessibility
- Frontend security awareness
- Frontend tests
- Blocking findings
- Conditions
- Missing evidence

Owner:

`Frontend Systems Engineer`

---

# Security Gate Review

When Security Gate applies, review:

- Gate status
- Security requirements
- Authentication
- Authorization
- Sensitive data
- Secrets
- Credentials
- Security boundaries
- Security tooling
- SonarQube evidence when applicable
- Dependency analysis
- Dynamic security testing
- Ethical Hacking / Assurance when applicable
- Remediation evidence
- Residual security risk
- Blocking findings
- Conditions
- Missing evidence

Owner:

`Security Engineer`

Security findings remain governed by Security Engineer authority.

Do not treat SonarQube PASS as Security Gate PASSED.

Do not invent formal security-risk acceptance.

---

# QA Gate Review

When QA Gate applies, review:

- Gate status
- Acceptance criteria
- Critical workflows
- Functional behaviour
- Test execution
- Contracts
- Regression
- Negative tests
- Data validation
- Security-control validation when requested
- Blocking defects
- Conditions
- Missing evidence

Owner:

`QA Engineer`

Do not treat test existence as execution.

---

# Code Review Gate Review

When Code Review Gate applies, review:

- Gate status
- Correctness
- Maintainability
- Architecture compliance
- Contract implementation
- Error handling
- Dependency changes
- Test quality
- Technical debt
- Blocking implementation findings
- Conditions
- Missing evidence

Owner:

`Code Reviewer`

Do not replace Code Review with SonarQube results.

---

# DevOps Gate Review

When DevOps Gate applies, review:

- Gate status
- Build
- CI/CD
- Artifact
- Configuration
- Secrets
- Runtime
- Infrastructure
- Deployment
- Database migration
- Rollback
- Recovery
- Observability
- Blocking operational findings
- Conditions
- Missing evidence

Owner:

`DevOps Engineer`

Do not require production-grade rollback or observability for every PoC.

For production changes, ensure controls match actual deployment risk.

---

# Performance Gate Review

When Performance Gate applies, review:

- Gate status
- Verified performance requirements
- Workload assumptions
- Benchmarks
- Profiling
- Load tests
- Runtime evidence
- Resource behaviour
- Scalability
- Capacity
- Performance regression
- Conditions
- Missing evidence

Owner:

`Performance Engineer`

Preserve evidence classification:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

Do not report inferred performance as measured performance.

---

# Documentation Gate Review

When Documentation Gate applies, review:

- Gate status
- Architecture documentation
- API documentation
- Configuration documentation
- Developer documentation
- Deployment documentation
- Runbooks
- Security documentation
- Known limitations
- Prototype-to-production documentation
- Dangerous contradictions
- Conditions
- Missing evidence

Owner:

`Documentation Engineer`

Documentation Gate may be blocking when inaccurate or absent documentation prevents safe deployment or operation.

---

# LLM Gate Review

Apply only when material LLM functionality exists.

Use:

`LLM Engineering Skill`

Review:

- LLM necessity
- Grounding
- Retrieval
- Authorization
- Structured outputs
- Output validation
- Evaluation
- Security
- Sensitive data
- Observability
- Performance
- Cost where material
- Blocking findings
- Conditions
- Missing evidence

Do not apply LLM Gate merely because Copilot was used to develop the software.

---

# Agentic Gate Review

Apply only when material agentic behaviour exists.

Use:

`Agentic Systems Engineering Skill`

Review:

- Agentic necessity
- Agent responsibilities
- Authority
- Routing
- Delegation
- Tool permissions
- Side effects
- Human approval
- State
- Memory
- Loop prevention
- Stopping conditions
- Traceability
- Evaluation
- Security
- Blocking findings
- Conditions
- Missing evidence

Do not apply Agentic Gate merely because an LLM exists.

---

# Test Evidence

Report actual test evidence.

Possible categories:

```text
Unit Tests
Integration Tests
Contract Tests
End-to-End Tests
Regression Tests
Negative Tests
Security-Control Tests
LLM Evaluation
Agentic Evaluation
```

Use:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Mandatory:

```text
DEFINED != EXECUTED
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
```

---

# Build and Pipeline Evidence

When relevant report:

## Build

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## CI/CD Pipeline

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## SonarQube

```text
PASS
FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Build success does not equal release approval.

Pipeline success does not equal QA approval.

SonarQube PASS does not equal Security approval.

---

# Deployment Evidence

When deployment is material report:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Review:

- Target environment
- Artifact
- Configuration
- Secrets
- Infrastructure
- Database migration
- Startup
- Health validation
- Smoke validation
- Rollback or recovery

Do not report a deployment plan as successful deployment evidence.

---

# Database and Data Readiness

When applicable review:

- Schema changes
- Migration
- Existing-data impact
- Data integrity
- Backward compatibility
- Deployment ordering
- Locking or availability risk
- Data repair
- Rollback or forward recovery
- Validation evidence

Destructive data operations may require explicit human approval.

---

# Rollback and Recovery

Evaluate based on:

- Lifecycle
- Target environment
- Reversibility
- Deployment risk
- Data changes
- Business impact

Possible evidence:

```text
VALIDATED
DEFINED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Do not require automated rollback universally.

A high-risk production change should have an appropriate viable recovery strategy.

---

# Observability Readiness

Evaluate only what actual operational requirements justify.

Possible capabilities:

- Logs
- Metrics
- Traces
- Health checks
- Dashboards
- Alerts

Use:

```text
AVAILABLE
NOT AVAILABLE
NOT VERIFIED
NOT APPLICABLE
```

Do not require every capability for every lifecycle.

Do not represent proposed observability as implemented observability.

---

# Conditions Review

For every condition verify:

```text
Condition
Responsible area
Required action
Evidence required
Validation
```

A condition must be:

- Explicit
- Actionable
- Non-critical
- Traceable

Do not use conditional approval to hide:

- Failed mandatory gate
- Critical blocker
- Missing required human approval
- Required formal risk treatment

---

# Missing Evidence Review

Missing release evidence must remain explicit.

For each material missing item identify:

```text
Missing evidence:
Expected source:
Impact:
Required validation:
```

Impact:

```text
BLOCKING
NON-BLOCKING
INFORMATIONAL
```

If blocking evidence is unavailable and safe readiness cannot be determined:

`NEEDS MORE INFO`

---

# Conflict Resolution

When specialist results conflict, use:

`decision-authority.md`

Process:

1. Identify the disagreement.
2. Identify the domain.
3. Identify domain authority.
4. Compare evidence.
5. Determine whether a blocker remains.
6. Request clarification when necessary.
7. Escalate unresolved governance decisions when required.

Do not use a universal hierarchy such as:

```text
Security > QA > Performance > DevOps
```

Example:

```text
Backend Recommendation:
APPROVE

Security Gate:
FAILED
```

If the unresolved blocker is a critical authorization defect:

```text
Final Decision:
BLOCK
```

because the Security domain owns that blocking finding, not because Security has universal priority.

---

# Cumulative Risk

Multiple non-critical findings may collectively create material release risk.

Evaluate:

- Interaction between findings
- Shared root cause
- Combined exposure
- Business criticality
- Operational impact
- Security impact
- Recoverability

Do not automatically convert multiple MEDIUM findings into BLOCK.

Document the evidence for cumulative-risk escalation.

---

# Human Approval

Evaluate according to:

- Lifecycle
- Target environment
- Impact
- Reversibility
- Security
- Governance
- Business criticality

Applicability:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Status:

```text
GRANTED
DENIED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Particular attention is required for:

- Production changes
- Emergency changes
- Destructive actions
- Data deletion
- Irreversible migrations
- Permission changes
- Credential changes
- Public exposure
- Formal risk acceptance
- Critical uncertainty
- Agentic production actions

Do not fabricate approval.

---

# Formal Risk Treatment

Formal risk treatment is separate from the engineering release decision.

Possible applicability:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Possible verified status:

```text
ACCEPTED
REMEDIATION REQUIRED
TRANSFERRED
AVOIDED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Only use:

`ACCEPTED`

when an authorized governance process provides verified evidence.

The Orchestrator cannot create formal risk acceptance.

`CONDITIONAL APPROVAL` is not formal risk acceptance.

---

# Residual Risk

Report residual risk when applicable:

```text
LOW
MEDIUM
HIGH
CRITICAL
NOT DETERMINED
NOT APPLICABLE
```

Residual risk must be supported by evidence.

Recording residual risk does not constitute accepting that risk.

---

# Release Gate

The final Release Gate uses:

```text
PASSED
CONDITIONAL
FAILED
```

## PASSED

Use when:

- Applicable mandatory gates pass.
- No critical blocker remains.
- Required release evidence is available.
- Required human approval is verified.
- Release can safely proceed for the intended lifecycle and environment.

## CONDITIONAL

Use when:

- No critical blocker remains.
- Remaining issues are explicitly non-critical.
- Conditions are explicit.
- Mandatory controls are not bypassed.
- Required human approval is satisfied.

## FAILED

Use when:

- Applicable mandatory gate fails.
- Critical blocker remains.
- Required approval was denied.
- Safe release cannot proceed.

Do not use `PASSED` when required evidence is `NOT EXECUTED` or `NOT AVAILABLE`.

---

# Final Decision

The Orchestrator must output exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## APPROVE

Use when:

- Applicable mandatory gates pass.
- No unresolved critical blocker remains.
- Required evidence is available.
- Required human approval exists.
- No unresolved conflict prevents safe release.

## CONDITIONAL APPROVAL

Use when:

- No critical blocker remains.
- Conditions are explicit.
- Remaining risk is understood.
- Mandatory controls are not bypassed.
- Required human approval exists.

## BLOCK

Use when:

- Applicable mandatory gate fails.
- Critical blocker remains.
- Required mandatory control is absent.
- Required human approval was denied.
- Safe deployment or release cannot proceed.

## NEEDS MORE INFO

Use when:

- Release scope cannot be verified.
- Requirements are answer-critical but unavailable.
- Required gate evidence is unavailable.
- Gate applicability cannot be determined.
- Required deployment evidence is unavailable.
- Required human-approval status is unavailable.
- Specialist conflict cannot be safely resolved.

Do not force a positive or negative decision when the correct state is uncertainty.

---

# Decision Log

When the release decision is material and governance requires a recorded decision, use:

`decision-log-template.md`

Record only:

- Actual participating agents
- Actual active skills
- Actual tool execution
- Actual evidence
- Actual gate results
- Actual human governance
- Actual conditions
- Actual missing evidence

Do not fabricate trace metadata.

---

# Traceability

Use:

`traceability-model.md`

Traceability should allow a reviewer to understand:

- What was released
- Why
- Which lifecycle applied
- Which specialists participated
- Which gates applied
- Which evidence was available
- Which blockers and conditions existed
- Whether human approval applied
- Why the final decision was produced

Do not fabricate:

- Execution IDs
- Change IDs
- Trace IDs
- Timestamps
- Agent participation
- Tool execution
- Approval

---

# Output Format

## Executive Summary

Summarize release readiness.

## Release Context

Report:

- Release objective
- Lifecycle
- Target environment
- Change type
- Scope
- Risk

## Requirements

Report:

- Verified requirements
- Assumptions
- Constraints
- Missing information

## Participating Agents

List only agents actually participating.

## Active Skills

List only skills actually applied.

## Evidence Summary

Report material:

- Repository evidence
- Test evidence
- Security evidence
- CI/CD evidence
- Deployment evidence
- Performance evidence
- Documentation evidence
- LLM evidence
- Agentic evidence

## Quality Gate Summary

For each relevant gate report:

```text
Architecture Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Backend Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Frontend Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Security Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

QA Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Code Review Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

DevOps Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Performance Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Documentation Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

LLM Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE

Agentic Gate:
PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE
```

Do not include irrelevant gates when a shorter output is preferable.

## Blocking Findings

List unresolved blockers.

## Conditions

List explicit non-blocking conditions.

## Missing Evidence

List unavailable release-critical evidence.

## Human Approval

Report:

```text
Applicability:
REQUIRED / NOT REQUIRED / NOT DETERMINED / NOT APPLICABLE

Status:
GRANTED / DENIED / NOT PROVIDED / NOT VERIFIED / NOT APPLICABLE
```

## Formal Risk Treatment

Report applicability and verified status when relevant.

Do not invent acceptance.

## Residual Risk

Use:

```text
LOW
MEDIUM
HIGH
CRITICAL
NOT DETERMINED
NOT APPLICABLE
```

## Release Gate

Exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## Final Release Decision

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## Decision Rationale

Explain how evidence, applicable gates, blockers, conditions, missing evidence, and human governance support the result.

---

# Decision Anti-Patterns

Avoid:

## Universal Gate Execution

Running every gate because the target environment is production.

## Global Specialist Hierarchy

Using a fixed ranking such as Security > QA > Performance.

## False PASS

Treating `NOT EXECUTED` or `NOT AVAILABLE` as successful validation.

## Build as Release Approval

Treating successful compilation or build as release readiness.

## SonarQube as Release Approval

Treating SonarQube PASS as complete Security, QA, Code Review, or release approval.

## Deployment Plan as Deployment Evidence

Treating a documented plan as successful execution.

## Automatic Rollback Requirement

Requiring automated rollback regardless of lifecycle and release risk.

## Full Observability Requirement

Requiring logs, metrics, traces, dashboards, and alerts universally.

## Conditional Approval as Bypass

Using conditions to hide a mandatory or critical blocker.

## Human Approval Fabrication

Inventing an approver or approval.

## Risk Acceptance Fabrication

Treating engineering approval as formal risk acceptance.

## False Participation

Reporting specialists that did not execute.

## Omitted Failed Gate

Leaving a failed relevant gate out of the final summary.

## Prototype-to-Production Drift

Approving prototype evidence as sufficient production evidence without validation.

---

# Definition of Done

A release decision is complete when:

- Release objective is understood.
- Lifecycle is identified.
- Target environment is identified.
- Release scope is verified.
- Verified requirements are distinguished from assumptions.
- Missing information is explicit.
- Participating agents reflect actual participation.
- Active skills reflect actual use.
- Applicable gates have been selected using `quality-gates.md`.
- Gate states use canonical vocabulary.
- Irrelevant gates have not been represented as PASSED.
- Test definitions have been distinguished from execution.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Build success has not been treated as QA PASS.
- SonarQube PASS has not been treated as Security approval.
- Architecture evidence has been considered when applicable.
- Backend evidence has been considered when applicable.
- Frontend evidence has been considered when applicable.
- Security evidence has been considered when applicable.
- QA evidence has been considered when applicable.
- Code Review evidence has been considered when applicable.
- DevOps evidence has been considered when applicable.
- Performance evidence has been considered when applicable.
- Documentation evidence has been considered when applicable.
- LLM evidence has been considered when applicable.
- Agentic evidence has been considered when applicable.
- Database and data migration readiness has been considered when applicable.
- Rollback or recovery has been evaluated according to risk.
- Observability has been evaluated according to operational need.
- Blocking findings are explicit.
- Conditions are explicit.
- Missing evidence is explicit.
- Conflicts have been handled according to `decision-authority.md`.
- Required human approval has been evaluated.
- Human approval has not been fabricated.
- Formal risk acceptance has not been invented.
- Residual risk is explicit when applicable.
- Decision logging has been applied when required.
- Traceability is appropriate to lifecycle and risk.
- Release Gate has been produced.
- Final Release Decision is traceable to verified evidence.

---

# Goal

Produce a release decision that reflects the actual lifecycle, target environment, scope, applicable Quality Gates, verified specialist evidence, human governance, and unresolved risk, allowing deployment only when mandatory controls are satisfied and preventing approval, blocking, or risk acceptance from being fabricated when evidence is missing.