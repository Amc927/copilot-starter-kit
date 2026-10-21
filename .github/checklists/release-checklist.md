# Release Readiness Checklist

Version: 2.0

---

# Purpose

This checklist supports the evidence-based decision on whether a change is ready for deployment, release, production use, or formal closure.

It may be used by:

- Orchestrator
- Solution Architect
- Backend Engineer
- Frontend Systems Engineer
- Security Engineer
- QA Engineer
- Code Reviewer
- DevOps Engineer
- Performance Engineer
- Documentation Engineer
- Applicable release-governance process

The checklist does not replace specialist Quality Gates.

It consolidates evidence from the gates that materially apply to the release.

Not every release requires every section or every gate.

Release-readiness depth must reflect:

- Lifecycle
- Target environment
- Release scope
- Business criticality
- Architecture
- Technology
- Security impact
- Functional impact
- Data impact
- Deployment impact
- Performance impact
- Operational risk
- LLM or agentic functionality

Use:

`quality-gates.md`

to determine gate applicability.

Use:

`decision-authority.md`

for authority, conflict resolution, formal risk-treatment boundaries, and the final engineering decision.

---

# Core Rules

Always apply:

```text
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
DEFINED != EXECUTED
CONFIGURED != EXECUTED
TEST EXISTS != TEST PASSED
BUILD PASSED != QA PASSED
SONARQUBE PASSED != SECURITY APPROVAL
GATE NOT APPLICABLE != GATE PASSED
AGENT DEFINED != AGENT PARTICIPATED
PLANNED DEPLOYMENT != SUCCESSFUL DEPLOYMENT
```

Do not fabricate:

- Release identifiers
- Change identifiers
- Execution identifiers
- Timestamps
- Agent participation
- Test execution
- Pipeline execution
- Deployment execution
- Gate results
- Human approval
- Formal risk acceptance
- Operational ownership

---

# Checklist Result Vocabulary

For checklist sections use:

```text
PASS
FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## PASS

Use only when required validation has been completed and supporting evidence exists.

## FAIL

Use when validation was performed and an applicable requirement was not satisfied.

## NOT EXECUTED

Use when required or potentially applicable validation was not performed.

## NOT AVAILABLE

Use when required evidence cannot currently be retrieved or verified.

## NOT APPLICABLE

Use when the section does not apply to the release scope.

Never convert `NOT EXECUTED` or `NOT AVAILABLE` into `PASS`.

---

# Release Context

- [ ] Release objective identified
- [ ] Target lifecycle identified
- [ ] Target environment identified
- [ ] Release scope identified
- [ ] Change type identified
- [ ] Business criticality understood
- [ ] Affected systems identified
- [ ] Affected users identified when relevant
- [ ] Main risks identified
- [ ] Release assumptions documented
- [ ] Missing release-critical information documented

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Target environment:

`Development / Test / QA / Pre-production / Production / Other / Not determined`

Change type:

`Feature / Bug Fix / Refactor / Security / Infrastructure / Documentation / Performance / LLM / Agentic / Mixed`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Release Scope Validation

- [ ] Included changes identified
- [ ] Excluded changes identified where relevant
- [ ] Affected repositories identified
- [ ] Affected components identified
- [ ] Affected services identified
- [ ] Affected frontend applications identified
- [ ] Affected APIs identified
- [ ] Data or database changes identified
- [ ] Infrastructure changes identified
- [ ] Configuration changes identified
- [ ] External integrations identified
- [ ] Dependencies between changes identified
- [ ] Release ordering dependencies identified
- [ ] Known partial implementations excluded or documented
- [ ] Planned work not represented as completed work

Release identifiers:

`Verified value / Not available / Not applicable`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Requirements Validation

- [ ] Business objective verified
- [ ] Functional requirements identified
- [ ] Acceptance criteria identified
- [ ] Expected behaviour verified
- [ ] Non-functional requirements identified where applicable
- [ ] Security requirements identified where applicable
- [ ] Performance requirements identified where applicable
- [ ] Accessibility requirements identified where applicable
- [ ] Operational requirements identified where applicable
- [ ] Verified requirements distinguished from assumptions
- [ ] Missing requirements explicitly documented
- [ ] Release has not been validated against invented requirements

Requirements status:

`VERIFIED / PARTIALLY VERIFIED / INFERRED / NOT VERIFIED / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Lifecycle Suitability

## Experiment

When applicable:

- [ ] Technical objective satisfied
- [ ] Critical safety constraints satisfied
- [ ] Execution limitations documented
- [ ] Experiment not represented as production-ready

## Prototype / PoC

When applicable:

- [ ] Prototype objective satisfied
- [ ] Business or technical assumptions evaluated
- [ ] Critical functionality validated
- [ ] Prototype limitations documented
- [ ] Security limitations documented
- [ ] Operational limitations documented
- [ ] Production migration implications documented where relevant
- [ ] Prototype success not represented as production readiness

## MVP

When applicable:

- [ ] Core business scope delivered
- [ ] Important integrations validated
- [ ] Maintainability assessed
- [ ] Security assessed appropriately
- [ ] Regression risk assessed
- [ ] Deployment readiness assessed
- [ ] Known limitations documented

## Production

When applicable:

- [ ] Production scope clearly defined
- [ ] Applicable mandatory Quality Gates evaluated
- [ ] Required deployment evidence available
- [ ] Required operational controls available
- [ ] Required recovery or rollback available
- [ ] Required security controls validated
- [ ] Required functional evidence available
- [ ] Required documentation available
- [ ] No prototype assumption remains unvalidated

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Feature Validation

Apply only when new or changed functionality exists.

- [ ] Feature scope implemented
- [ ] Acceptance criteria evaluated
- [ ] Critical user flows validated
- [ ] Required business rules validated
- [ ] Edge cases considered
- [ ] Negative scenarios considered
- [ ] Required contracts validated
- [ ] Known limitations documented
- [ ] Planned functionality not represented as implemented
- [ ] Prototype functionality not represented as production-ready without evidence

Execution status:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Bug Fix Validation

Apply only when the release contains defect remediation.

Reproduction status:

```text
REPRODUCED
OBSERVED
INFERRED
NOT REPRODUCED
NOT EXECUTED
NOT AVAILABLE
```

Root Cause Status:

```text
CONFIRMED
PROBABLE
NOT DETERMINED
NOT APPLICABLE
```

Validate:

- [ ] Reported defect understood
- [ ] Expected behaviour verified
- [ ] Reproduction status supported by evidence
- [ ] Root Cause Status explicit
- [ ] Probable cause not represented as confirmed
- [ ] Fix scope identified
- [ ] Expected behaviour restored where execution permits validation
- [ ] Original failure no longer reproduced where practical
- [ ] Related behaviour validated
- [ ] Regression protection evaluated
- [ ] Temporary workaround distinguished from permanent remediation
- [ ] Data repair separated from application remediation where applicable
- [ ] Remaining uncertainty documented

Regression evidence:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Architecture Validation

Apply only when the release materially affects architecture.

- [ ] Architecture Gate applicability evaluated
- [ ] Approved architecture identified
- [ ] Technology decisions verified
- [ ] System boundaries respected
- [ ] Service boundaries respected
- [ ] Data-ownership boundaries respected
- [ ] Integration patterns validated
- [ ] Deployment architecture validated when affected
- [ ] Technology migration approved when applicable
- [ ] Prototype-to-production architecture reviewed where relevant
- [ ] Material architecture decision recorded in an ADR when required
- [ ] No unauthorized architectural change remains

Architecture Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Backend Validation

Apply only when backend implementation is materially affected.

Backend technology:

`Python / Java / Existing technology / Other / Not determined / Not applicable`

Active skills:

`Python Engineering / Java Engineering / Python MCP Engineering / Other / None`

Validate:

- [ ] Backend Gate applicability evaluated
- [ ] Approved technology used
- [ ] Approved architecture respected
- [ ] Business logic implemented
- [ ] Input validation implemented
- [ ] Error handling implemented
- [ ] API contracts implemented where applicable
- [ ] Data integrity preserved
- [ ] Persistence changes validated
- [ ] Database migrations defined where applicable
- [ ] External integrations validated where applicable
- [ ] Dependency changes justified
- [ ] Required implementation tests evaluated
- [ ] No blocking backend defect remains

Backend Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Frontend Validation

Apply only when frontend implementation is materially affected.

Frontend technology:

`Angular / Streamlit / Existing technology / Other / Not determined / Not applicable`

Active skill:

`Endesa Corporate Angular Engineering / Python Engineering / Other / None`

Validate:

- [ ] Frontend Gate applicability evaluated
- [ ] Approved frontend technology used
- [ ] Lifecycle suitability validated
- [ ] Critical user flows implemented
- [ ] Required UI states handled
- [ ] API contracts compatible
- [ ] Forms and validation behave correctly where applicable
- [ ] Authentication states handled where applicable
- [ ] Authorization states handled where applicable
- [ ] Accessibility evaluated appropriately
- [ ] Frontend security concerns addressed or escalated
- [ ] Required implementation tests evaluated
- [ ] Corporate capabilities not invented
- [ ] Streamlit prototype not represented as Angular production validation
- [ ] No blocking frontend defect remains

Frontend Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Test Execution Evidence

For each relevant test category report actual evidence.

Unit Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Integration Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Contract Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

End-to-End Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Regression Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Negative Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Security-Control Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Validate:

- [ ] Test definitions distinguished from execution
- [ ] CI/CD evidence identified where applicable
- [ ] Failed tests explicitly reported
- [ ] Tests not executed explicitly reported
- [ ] Missing test evidence explicitly reported
- [ ] Build success not treated as functional PASS
- [ ] SonarQube PASS not treated as test PASS
- [ ] Synthetic test data identified when used

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# QA Validation

Apply only when QA Gate is applicable.

- [ ] QA Gate applicability evaluated
- [ ] Acceptance criteria evaluated
- [ ] Critical flows validated
- [ ] Functional behaviour validated
- [ ] Required contracts validated
- [ ] Regression risk evaluated
- [ ] Negative scenarios considered
- [ ] Data behaviour validated where applicable
- [ ] Security-control behaviour validated when requested
- [ ] Test execution evidence available
- [ ] No critical functional blocker remains

QA Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

QA Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Code Review Validation

Apply only when Code Review Gate is applicable.

- [ ] Code Review applicability evaluated
- [ ] Changed implementation reviewed
- [ ] Correctness evaluated
- [ ] Maintainability evaluated
- [ ] Architecture compliance evaluated
- [ ] Contract implementation reviewed
- [ ] Error handling reviewed
- [ ] Dependency changes reviewed
- [ ] Test quality reviewed
- [ ] Regression risk reviewed
- [ ] Security-sensitive implementation concerns escalated
- [ ] Performance-sensitive implementation concerns escalated
- [ ] No critical implementation blocker remains

Code Review Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Code Review Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Security Validation

Apply only when Security Gate is applicable.

- [ ] Security Gate applicability evaluated
- [ ] Verified corporate requirements identified where applicable
- [ ] Project-specific requirements identified
- [ ] Threats evaluated
- [ ] Authentication evaluated where applicable
- [ ] Authorization evaluated where applicable
- [ ] Sensitive-data handling evaluated
- [ ] Secrets and credentials evaluated
- [ ] Dependency risk evaluated
- [ ] API security evaluated where applicable
- [ ] MCP security evaluated where applicable
- [ ] LLM security evaluated where applicable
- [ ] Agentic security evaluated where applicable
- [ ] SonarQube evidence reviewed when available
- [ ] Mandatory security tooling evidence verified where required
- [ ] Ethical Hacking or Assurance applicability evaluated where relevant
- [ ] Required remediation evidence reviewed
- [ ] No unresolved critical security blocker remains

Security Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Security Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# SonarQube and Static Analysis Evidence

SonarQube is supporting evidence unless a verified process makes it a mandatory gate.

SonarQube detected:

`YES / NO / NOT DETERMINED`

Configured in CI/CD:

`YES / NO / NOT DETERMINED`

Execution status:

`EXECUTED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Quality Gate:

`PASS / FAIL / NOT AVAILABLE / NOT APPLICABLE`

Mandatory gate:

`YES / NO / NOT DETERMINED`

Validate:

- [ ] Analysis execution supported by evidence
- [ ] Relevant revision identified when available
- [ ] Quality Gate result preserved accurately
- [ ] Security findings routed to Security Engineer
- [ ] Implementation findings routed to Code Reviewer
- [ ] Missing execution not treated as PASS
- [ ] SonarQube PASS not treated as complete release approval

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Performance Validation

Apply only when Performance Gate is applicable.

Evidence classification:

`MEASURED / OBSERVED / INFERRED / NOT VALIDATED / NOT APPLICABLE`

Validate:

- [ ] Performance Gate applicability evaluated
- [ ] Verified performance requirements identified
- [ ] Workload assumptions identified
- [ ] Critical paths identified
- [ ] Benchmarking performed when required
- [ ] Profiling performed when required
- [ ] Load testing performed when required
- [ ] Database impact evaluated
- [ ] Resource consumption evaluated
- [ ] Scalability evaluated at appropriate lifecycle depth
- [ ] Performance-regression risk evaluated
- [ ] Optimization improvements supported by before-and-after evidence
- [ ] No critical performance blocker remains

Performance Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Performance Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Build and Artifact Readiness

Apply when build and artifact evidence is relevant.

Build:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Artifact:

`AVAILABLE / NOT AVAILABLE / NOT APPLICABLE`

Validate:

- [ ] Build configuration identified
- [ ] Build execution evidence available where required
- [ ] Dependency resolution completed where required
- [ ] Artifact created where applicable
- [ ] Artifact version or identity verified where available
- [ ] Source-to-artifact traceability available where required
- [ ] Artifact publication verified where applicable
- [ ] Build logs do not expose secrets
- [ ] Build success not treated as complete release approval

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# CI/CD Readiness

Apply when CI/CD is used or required.

Pipeline:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Validate:

- [ ] Pipeline configuration identified
- [ ] Required stages identified
- [ ] Required test stages identified
- [ ] Required static-analysis stages identified
- [ ] Required dependency-analysis stages identified
- [ ] Required deployment stages identified
- [ ] Mandatory gates identified from evidence
- [ ] Pipeline execution evidence available
- [ ] Failed mandatory stage explicitly reported
- [ ] Missing pipeline execution not treated as PASS

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Configuration Readiness

- [ ] Configuration changes identified
- [ ] Environment variables identified
- [ ] Required values documented safely
- [ ] Defaults verified where applicable
- [ ] Environment-specific differences identified
- [ ] Production-only configuration identified
- [ ] Feature configuration identified where applicable
- [ ] Sensitive values excluded from source code
- [ ] Missing required configuration explicitly reported
- [ ] Configuration validated in the target environment where required

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Secrets, Credentials, and Certificates

Apply when the release uses secrets, machine credentials, tokens, or certificates.

- [ ] Secret-management mechanism verified
- [ ] Required secret references identified
- [ ] Real secrets absent from source control
- [ ] Real secrets absent from documentation
- [ ] Secrets absent from pipeline logs
- [ ] Required credentials available through approved mechanisms
- [ ] Credential ownership verified when available
- [ ] Rotation considered where applicable
- [ ] Certificate expiration considered where applicable
- [ ] Revocation considered where applicable
- [ ] Runtime update behaviour considered where applicable
- [ ] No critical secret-management blocker remains

Do not record real secret values in this checklist.

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Deployment Readiness

Apply when a deployment is planned or required.

Deployment execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Validate:

- [ ] DevOps Gate applicability evaluated
- [ ] Deployment scope identified
- [ ] Target environment verified
- [ ] Deployment procedure identified
- [ ] Deployment strategy appropriate to lifecycle and risk
- [ ] Required artifact identified
- [ ] Required configuration available
- [ ] Required secrets available through approved mechanisms
- [ ] Infrastructure dependencies validated
- [ ] External dependencies considered
- [ ] Application startup validation defined
- [ ] Health checks evaluated where applicable
- [ ] Smoke tests evaluated where applicable
- [ ] Deployment result supported by evidence
- [ ] No critical deployment blocker remains

DevOps Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

DevOps Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Database and Data Migration Readiness

Apply when schemas, persistence, stored data, or migration order are affected.

- [ ] Schema changes identified
- [ ] Migration available
- [ ] Existing-data impact evaluated
- [ ] Data-integrity impact evaluated
- [ ] Backward compatibility evaluated
- [ ] Application/database version compatibility evaluated
- [ ] Deployment order defined
- [ ] Long-running migration risk evaluated
- [ ] Locking or availability impact evaluated
- [ ] Rollback or forward-recovery strategy evaluated
- [ ] Migration validation defined
- [ ] Data repair separated from schema migration where applicable
- [ ] Required human approval evaluated for destructive changes
- [ ] No unsafe migration blocker remains

Migration execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Rollback and Recovery Readiness

Rollback requirements must reflect lifecycle, reversibility, environment, and risk.

- [ ] Rollback applicability evaluated
- [ ] Recovery applicability evaluated
- [ ] Application rollback available where required
- [ ] Artifact rollback available where required
- [ ] Configuration rollback available where required
- [ ] Database recovery strategy available where required
- [ ] External compatibility considered
- [ ] Failure-detection criteria defined where required
- [ ] Recovery validation available where required
- [ ] Limitations documented
- [ ] Operational owner recorded only when verified
- [ ] No high-risk production change lacks a required viable recovery path

Rollback:

`VALIDATED / DEFINED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Recovery:

`VALIDATED / DEFINED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Do not fail a low-risk prototype solely because production-grade automated rollback is absent.

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Observability Readiness

Observability depth must reflect lifecycle and operational requirements.

Evaluate applicable:

- [ ] Logging available where required
- [ ] Sensitive information protected in logs
- [ ] Health checks available where required
- [ ] Metrics available where required
- [ ] Tracing available where justified
- [ ] Dashboards available where useful
- [ ] Alerts available where actionable
- [ ] Critical failures observable
- [ ] External dependency failures observable where required
- [ ] Deployment validation observable
- [ ] Operational troubleshooting evidence available
- [ ] Unavailable capabilities not represented as implemented

Logging:

`AVAILABLE / NOT AVAILABLE / NOT VERIFIED / NOT APPLICABLE`

Metrics:

`AVAILABLE / NOT AVAILABLE / NOT VERIFIED / NOT APPLICABLE`

Tracing:

`AVAILABLE / NOT AVAILABLE / NOT VERIFIED / NOT APPLICABLE`

Health checks:

`AVAILABLE / NOT AVAILABLE / NOT VERIFIED / NOT APPLICABLE`

Alerts:

`AVAILABLE / NOT AVAILABLE / NOT VERIFIED / NOT APPLICABLE`

Do not require logs, metrics, traces, dashboards, and alerts universally for every experiment or PoC.

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Operational Readiness

Apply when the target lifecycle or environment requires ongoing operation.

- [ ] Operational responsibilities identified when verified
- [ ] Support expectations documented when verified
- [ ] Common failure scenarios considered
- [ ] Troubleshooting information available where required
- [ ] Recovery procedure available where required
- [ ] Required runbooks available
- [ ] Required platform dependencies understood
- [ ] Required access available
- [ ] Known operational limitations documented
- [ ] Operational contacts or owners not invented
- [ ] No critical operational-readiness blocker remains

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Documentation Readiness

Apply when Documentation Gate is applicable.

- [ ] Documentation Gate applicability evaluated
- [ ] System overview updated where required
- [ ] Architecture documentation updated where required
- [ ] ADR updated where required
- [ ] API documentation updated where required
- [ ] Data documentation updated where required
- [ ] Configuration documentation updated where required
- [ ] Developer documentation updated where required
- [ ] Deployment documentation updated where required
- [ ] Runbooks updated where required
- [ ] Security documentation updated where required
- [ ] Performance documentation updated where required
- [ ] Prototype limitations documented where applicable
- [ ] Prototype-to-production implications documented where applicable
- [ ] No secrets exposed
- [ ] No dangerous documentation contradiction remains

Documentation Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Documentation Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# LLM Release Readiness

Apply only when material LLM functionality exists.

Use:

`LLM Engineering Skill`

Validate:

- [ ] LLM Gate applicability evaluated
- [ ] LLM use justified
- [ ] Model requirements identified
- [ ] Grounding requirements satisfied
- [ ] Retrieval authorization validated where applicable
- [ ] Retrieval quality evaluated where applicable
- [ ] No-result behaviour defined
- [ ] Conflicting-source behaviour defined
- [ ] Structured outputs validated where applicable
- [ ] Model output treated as untrusted
- [ ] Hallucination controls evaluated
- [ ] Abstention behaviour evaluated
- [ ] Representative evaluation defined
- [ ] Required evaluation executed
- [ ] Security review completed where applicable
- [ ] Sensitive-data handling evaluated
- [ ] Observability evaluated
- [ ] Performance and cost evaluated when material
- [ ] No critical LLM blocker remains

LLM Evaluation:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

LLM Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Agentic Release Readiness

Apply only when material agentic behaviour exists.

Use:

`Agentic Systems Engineering Skill`

Validate:

- [ ] Agentic Gate applicability evaluated
- [ ] Agentic behaviour justified
- [ ] Agent responsibilities explicit
- [ ] Authority model explicit
- [ ] Routing evaluated
- [ ] Delegation bounded
- [ ] Circular delegation prevented
- [ ] Tool access follows Least Privilege
- [ ] Read-only and state-changing tools distinguished
- [ ] Destructive actions controlled
- [ ] Human approval implemented where required
- [ ] Stopping conditions defined
- [ ] Workflow state explicit
- [ ] Memory controls evaluated where applicable
- [ ] Prompt-injection threats evaluated
- [ ] Tool-abuse threats evaluated
- [ ] Confused-deputy risk evaluated
- [ ] Production-change controls evaluated
- [ ] Traceability appropriate to lifecycle and risk
- [ ] Representative workflow evaluation executed where required
- [ ] No critical agentic blocker remains

Agentic Evaluation:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Agentic Gate:

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Governance Validation

- [ ] Applicable workflow identified
- [ ] Lifecycle considered
- [ ] Only required agents invoked
- [ ] Participating agents supported by execution evidence
- [ ] Only applicable skills activated
- [ ] Applicable Quality Gates selected using `quality-gates.md`
- [ ] Gate results supported by evidence
- [ ] Irrelevant gates not represented as PASSED
- [ ] Conflicts handled according to `decision-authority.md`
- [ ] NOT EXECUTED not treated as PASS
- [ ] NOT AVAILABLE not treated as PASS
- [ ] Formal risk acceptance not invented
- [ ] Human approval evaluated where required
- [ ] Conditions explicit
- [ ] Missing evidence explicit
- [ ] Final decision traceable

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Human Approval

Evaluate when required by governance, risk, environment, or reversibility.

Possible cases include:

- Production changes
- Emergency production changes
- Destructive actions
- Irreversible migrations
- Data deletion
- Permission changes
- Credential changes
- Public exposure
- Formal risk acceptance
- High-impact financial action
- Critical unresolved uncertainty
- Agentic production actions
- Governance changes

Human approval applicability:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Human approval status:

```text
GRANTED
DENIED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Do not report `GRANTED` without evidence.

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Open Risk Review

- [ ] Known risks documented
- [ ] Risk severity documented
- [ ] Risk evidence documented
- [ ] Existing controls documented
- [ ] Required remediation documented
- [ ] Compensating controls documented where applicable
- [ ] Residual risk documented
- [ ] Formal treatment requirement identified where applicable
- [ ] Formal risk acceptance not claimed without evidence
- [ ] Authorized risk decision recorded only when verified
- [ ] Risk ownership recorded only when verified

Residual risk:

`LOW / MEDIUM / HIGH / CRITICAL / NOT DETERMINED / NOT APPLICABLE`

Formal risk acceptance:

`REQUIRED / NOT REQUIRED / NOT DETERMINED / NOT APPLICABLE`

Verified acceptance evidence:

`AVAILABLE / NOT AVAILABLE / NOT APPLICABLE`

Residual-risk reporting does not itself constitute formal risk acceptance.

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Conditions Review

For every non-blocking condition record:

```text
Condition:
Responsible area:
Required action:
Evidence required:
Validation:
```

Validate:

- [ ] Conditions are specific
- [ ] Conditions are actionable
- [ ] Responsible area identified
- [ ] Required evidence identified
- [ ] Validation identified
- [ ] Mandatory blocker not disguised as a condition
- [ ] Formal risk acceptance not replaced by a condition

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Missing Evidence Review

For each material missing item record:

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

Validate:

- [ ] Missing evidence explicitly listed
- [ ] Impact classified
- [ ] Expected source identified when known
- [ ] Missing evidence not represented as PASS
- [ ] Blocking missing evidence reflected in the final recommendation

Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Final Quality Gate Summary

Report only gates relevant to the actual release.

## Architecture Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Backend Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Frontend Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Security Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## QA Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Code Review Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## DevOps Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Performance Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Documentation Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## LLM Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

## Agentic Gate

`PASSED / CONDITIONAL / FAILED / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

---

# Release Blocking Rules

Recommend `BLOCK` when an applicable unresolved condition exists, such as:

- Mandatory applicable Quality Gate failed
- Critical functional defect remains
- Critical security blocker remains
- Critical implementation defect remains
- Critical data-integrity risk remains
- Unsafe database migration remains
- Deployment is demonstrably unsafe
- Required production secret is exposed or unavailable
- Critical performance blocker prevents required workload
- Critical mandatory documentation is dangerously incorrect or absent
- Critical LLM control failure remains
- Critical agentic control failure remains
- Required human approval was denied
- Safe release cannot proceed

Do not block solely because an optional improvement remains.

---

# Release NEEDS MORE INFO Rules

Use `NEEDS MORE INFO` when release-critical evidence is unavailable.

Examples:

- Scope cannot be verified
- Requirements cannot be verified
- Mandatory gate applicability cannot be determined
- Required test results unavailable
- Required security evidence unavailable
- Required deployment evidence unavailable
- Required configuration unknown
- Required migration status unavailable
- Required human-approval status unavailable
- Specialist conflict cannot be resolved safely

Do not guess release readiness.

---

# Release Conditional Approval Rules

Use `CONDITIONAL APPROVAL` only when:

- No unresolved critical blocker remains
- Mandatory controls are not bypassed
- Remaining issues are non-critical
- Conditions are explicit
- Responsible areas are identifiable
- Required evidence is identifiable
- Validation requirements are explicit
- Required human approval is satisfied
- Remaining risk is understood

Do not use conditional approval as a substitute for formal risk acceptance.

---

# Release Gate Result

Use exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## PASSED

Use when:

- Applicable mandatory gates pass
- No critical blocker remains
- Required evidence is available
- Required human approval is available
- Release can proceed safely for its intended lifecycle and target environment

## CONDITIONAL

Use when:

- No critical blocker remains
- Remaining conditions are non-critical and explicit
- Mandatory governance is not bypassed

## FAILED

Use when:

- An applicable mandatory gate fails
- A critical blocker remains
- Required approval was denied
- Safe release cannot proceed

The Release Gate does not use `NOT EXECUTED` or `NOT AVAILABLE` as final results.

Where required evidence is missing, use the recommendation:

`NEEDS MORE INFO`

and do not claim that the Release Gate passed.

---

# Release Recommendation

Use exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Recommendation:

`_____________________`

Evidence-based rationale:

`________________________________________________`

`________________________________________________`

---

# Release Sign-Off

Orchestrator:

`_____________________`

Date:

`_____________________`

Do not invent the reviewer or date.

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Target environment:

`_____________________`

Release Gate:

`PASSED / CONDITIONAL / FAILED`

Final Decision:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO`

Human Approval:

`GRANTED / DENIED / NOT PROVIDED / NOT VERIFIED / NOT APPLICABLE`

Conditions:

`________________________________________________`

Missing Evidence:

`________________________________________________`

Residual Risk:

`LOW / MEDIUM / HIGH / CRITICAL / NOT DETERMINED / NOT APPLICABLE`

Comments:

`________________________________________________`

`________________________________________________`

`________________________________________________`

---

# Traceability

Record only information actually available from the execution environment.

Possible fields include:

- Execution identifier
- Release identifier
- Change identifier
- Lifecycle
- Target environment
- Participating agents
- Active skills
- Applicable gates
- Gate results
- Tools executed
- Test evidence
- Human approval
- Final decision
- Timestamp

Do not fabricate unavailable trace information.

Do not report an agent as participating if the agent was not invoked.

Do not report a tool, test, pipeline, deployment, or gate as executed without evidence.

---

# Release Readiness Anti-Patterns

Avoid:

## Every Gate for Every Release

Running every available Quality Gate regardless of scope.

## False PASS

Treating missing, unavailable, configured, or non-executed evidence as successful validation.

## Build as Release Approval

Treating a successful build as complete QA, Security, deployment, or release approval.

## SonarQube as Release Approval

Treating SonarQube PASS as complete engineering readiness.

## Universal Rollback Requirement

Failing every prototype or low-risk environment because automated production rollback is absent.

## Universal Observability Requirement

Demanding logs, metrics, traces, dashboards, and alerts for every lifecycle regardless of operational need.

## Accepted Risk Without Evidence

Claiming that risk was accepted without an authorized governance decision.

## Invented Ownership

Creating release owners, operational owners, contacts, or approvers not supported by evidence.

## Planned Deployment as Executed Deployment

Describing a deployment plan as successful deployment evidence.

## Prototype-to-Production Drift

Approving a prototype for production without production-specific validation.

## Conditional Approval as Bypass

Using conditions to hide mandatory blockers.

## False Traceability

Inventing identifiers, timestamps, agent participation, or approvals to complete the release record.

---

# Definition of Ready for Release

A change is ready for its intended release context when:

- Release objective is understood.
- Release scope is verified.
- Lifecycle is identified.
- Target environment is identified.
- Applicable requirements are verified.
- Assumptions are explicit.
- Missing information is explicit.
- Planned work is not represented as completed implementation.
- Applicable Quality Gates have been selected using `quality-gates.md`.
- Conflicts have been handled according to `decision-authority.md`.
- Irrelevant gates have not been represented as PASSED.
- Required architecture evidence is available.
- Required backend evidence is available.
- Required frontend evidence is available.
- Required security evidence is available.
- Required QA evidence is available.
- Required Code Review evidence is available.
- Required DevOps evidence is available.
- Required performance evidence is available.
- Required documentation evidence is available.
- Required LLM evidence is available when material LLM functionality exists.
- Required agentic evidence is available when material agentic behaviour exists.
- Test definitions have been distinguished from test execution.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Build success has not been treated as QA PASS.
- SonarQube PASS has not been treated as complete release approval.
- Required contracts are compatible.
- Required configuration is available.
- Secrets are handled safely.
- Database and data migrations are safe when applicable.
- Deployment is safe for the intended lifecycle and environment.
- Required rollback or recovery is available according to risk.
- Observability is sufficient for actual operational needs.
- Required documentation is accurate and available.
- Required human approval has been evaluated.
- Formal risk acceptance has not been invented.
- Critical blockers are resolved.
- Conditions are explicit.
- Missing evidence is explicit.
- Residual risk is explicit.
- Trace information has not been fabricated.
- Release Gate has been produced.
- Release Recommendation is traceable to verified evidence.

---

# Goal

Ensure that each change is released only when the evidence required by its actual lifecycle, scope, target environment, architecture, technology, risk, and operational impact is available, all applicable critical blockers are resolved, mandatory controls are satisfied, and the final release decision is traceable without inventing execution, approval, ownership, or risk acceptance.