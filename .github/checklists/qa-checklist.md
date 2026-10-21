# QA Validation Checklist

Version: 2.0

---

# Purpose

Used by the QA Engineer to validate functional correctness, acceptance criteria, integration behaviour, contract compatibility, regression safety, test evidence, and lifecycle-appropriate release readiness.

Testing depth must reflect:

- Application lifecycle
- Business criticality
- Change risk
- Architecture
- Technology
- Integration impact

For each section use:

PASS
FAIL
NOT APPLICABLE
NOT EXECUTED

Do not convert missing test evidence into PASS.

A FAIL in a critical functional flow must be reported to the Orchestrator.

---

# QA Context

- [ ] Change scope identified
- [ ] Application lifecycle identified when relevant
- [ ] Affected components identified
- [ ] Technology context identified
- [ ] Business criticality understood
- [ ] Main functional risks identified
- [ ] Relevant integrations identified
- [ ] Missing QA-critical information documented

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Result:

PASS / FAIL / N/A

---

# Requirements Validation

- [ ] Business requirements identified
- [ ] Acceptance criteria identified
- [ ] Expected behaviour defined
- [ ] Failure behaviour understood
- [ ] Boundary conditions identified
- [ ] Relevant non-functional expectations identified
- [ ] Verified requirements distinguished from assumptions
- [ ] Missing requirements explicitly reported
- [ ] Defects are not based solely on unverified assumptions

Result:

PASS / FAIL / N/A

---

# Repository Test Discovery

- [ ] Existing tests searched
- [ ] Testing framework identified
- [ ] Test configuration identified
- [ ] Test directories identified
- [ ] CI/CD test execution investigated
- [ ] Existing regression tests investigated
- [ ] Integration-test infrastructure investigated
- [ ] Contract-test infrastructure investigated where applicable
- [ ] End-to-end infrastructure investigated where applicable
- [ ] Coverage configuration investigated
- [ ] Existing test conventions understood

Result:

PASS / FAIL / N/A

---

# Lifecycle-Aware Testing

## Experiment

When applicable:

- [ ] Technical feasibility validated
- [ ] Primary assumptions validated
- [ ] Critical failure conditions considered
- [ ] Production-depth testing not required without justification

## Prototype / PoC

When applicable:

- [ ] Primary business flow validated
- [ ] Functional assumptions validated
- [ ] Integration feasibility validated
- [ ] Data processing validated
- [ ] Critical error paths evaluated
- [ ] Prototype limitations documented
- [ ] Prototype success not represented as production readiness

## MVP

When applicable:

- [ ] Core business flows validated
- [ ] Important integrations validated
- [ ] Error behaviour validated
- [ ] Regression safety evaluated
- [ ] Maintainable test coverage exists where appropriate

## Production

When applicable:

- [ ] Critical flows validated
- [ ] Core business functionality validated
- [ ] Integration behaviour validated
- [ ] Mandatory contracts validated
- [ ] Error behaviour validated
- [ ] Regression safety evaluated
- [ ] Required security-control behaviour validated
- [ ] Required test evidence available

Result:

PASS / FAIL / N/A

---

# Risk-Based Test Strategy

- [ ] Critical flows identified
- [ ] High-impact flows identified
- [ ] Secondary flows identified
- [ ] Test priority reflects business impact
- [ ] Test priority reflects regression risk
- [ ] Data-integrity risks considered
- [ ] Integration risks considered
- [ ] State-changing operations considered
- [ ] Testing depth appropriate to lifecycle
- [ ] Unnecessary test complexity avoided

Result:

PASS / FAIL / N/A

---

# Unit Testing

Apply where appropriate.

- [ ] Business rules covered
- [ ] Data transformations covered
- [ ] Validation covered
- [ ] State transitions covered
- [ ] Edge cases covered
- [ ] Error behaviour covered
- [ ] Tests focus on observable behaviour
- [ ] Tests are deterministic
- [ ] Excessive implementation coupling avoided

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Integration Testing

Apply where integration boundaries exist.

- [ ] API integration tested where applicable
- [ ] Database integration tested where applicable
- [ ] External-service integration tested where applicable
- [ ] Authentication integration tested where applicable
- [ ] Authorization integration tested where applicable
- [ ] Framework integration tested where applicable
- [ ] MCP integration tested where applicable
- [ ] Material real boundary behaviour tested where practical
- [ ] Failure behaviour tested

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Contract Validation

Apply when explicit interfaces exist.

- [ ] Request schema validated
- [ ] Response schema validated
- [ ] Required fields validated
- [ ] Optional fields validated
- [ ] Data types validated
- [ ] Error contract validated
- [ ] Status semantics validated where applicable
- [ ] Backward compatibility reviewed
- [ ] Consumer expectations considered
- [ ] Frontend/backend compatibility validated where applicable
- [ ] Service-to-service contracts validated where applicable
- [ ] External API contracts validated where applicable
- [ ] MCP tool contracts validated where applicable
- [ ] MCP resource contracts validated where applicable
- [ ] No mandatory contract is broken

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# End-to-End Testing

Apply when critical integrated journeys justify E2E testing.

- [ ] Critical user journeys identified
- [ ] Important state-changing operations considered
- [ ] Authentication journey tested where relevant
- [ ] Authorization-dependent journey tested where relevant
- [ ] Business-critical processing flows tested where relevant
- [ ] E2E scope remains focused on high-value behaviour
- [ ] Unnecessary E2E coverage avoided

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Functional Testing

- [ ] Feature behaviour validated against verified requirements
- [ ] Valid inputs tested
- [ ] Outputs validated
- [ ] State transitions validated
- [ ] Error handling validated
- [ ] Boundary conditions tested
- [ ] Critical business rules validated
- [ ] Failure scenarios considered
- [ ] No blocking core workflow failure identified

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE`

Result:

PASS / FAIL / NOT EXECUTED

---

# Negative Testing

Evaluate applicable negative scenarios.

- [ ] Invalid data tested
- [ ] Empty values tested
- [ ] Missing required values tested
- [ ] Malformed requests tested
- [ ] Boundary values tested
- [ ] Unsupported data tested
- [ ] Missing resources considered
- [ ] Timeout behaviour considered
- [ ] External dependency failure considered
- [ ] Duplicate submission considered
- [ ] Invalid application state considered
- [ ] Unauthorized operation considered where relevant
- [ ] Insufficient permissions considered where relevant

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Regression Validation

For defects and material changes:

- [ ] Existing relevant functionality identified
- [ ] Critical related workflows evaluated
- [ ] Regression risk assessed
- [ ] Existing automated regression tests reviewed
- [ ] Original defect reproduced where practical
- [ ] Regression test added where practical
- [ ] Fix validated where execution is available
- [ ] Related behaviour validated
- [ ] No unsupported claim of regression protection made

Regression Risk:

`LOW / MEDIUM / HIGH / CRITICAL`

Execution:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Data Validation Testing

Apply when data processing is material.

- [ ] Input integrity validated
- [ ] Parsing validated
- [ ] Transformations validated
- [ ] Calculations validated
- [ ] Mappings validated
- [ ] Duplicate handling validated
- [ ] Missing values considered
- [ ] Boundary values considered
- [ ] Persistence validated where applicable
- [ ] Export validated where applicable
- [ ] Rounding validated where applicable
- [ ] Error recovery considered

For Excel or data-oriented applications:

- [ ] Required columns validated
- [ ] Optional columns validated
- [ ] Invalid formats considered
- [ ] Empty datasets considered
- [ ] Duplicate records considered
- [ ] Unexpected values considered
- [ ] Output consistency validated

Synthetic test data, when used, is explicitly identified.

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Frontend Validation

Apply when frontend functionality is affected.

- [ ] Loading state validated
- [ ] Success state validated
- [ ] Empty state validated
- [ ] Validation state validated
- [ ] API error state validated
- [ ] Authentication failure state validated where relevant
- [ ] Authorization failure state validated where relevant
- [ ] Partial failure considered
- [ ] Retry behaviour considered
- [ ] Form submission validated where relevant
- [ ] Duplicate-action behaviour considered
- [ ] Routing validated where relevant
- [ ] State transitions validated
- [ ] Backend contract integration validated

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Angular Validation

Apply only when Angular is involved.

- [ ] Component behaviour validated
- [ ] Service interaction validated
- [ ] Routing behaviour validated
- [ ] Forms validated where applicable
- [ ] API integration validated
- [ ] Corporate component integration validated where applicable
- [ ] Applicable Angular testing requirements followed
- [ ] Corporate requirements not invented

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Streamlit Validation

Apply only when Streamlit is involved.

- [ ] Lifecycle identified
- [ ] Input behaviour validated
- [ ] Data processing validated
- [ ] State behaviour validated
- [ ] Error handling validated
- [ ] Integration behaviour validated
- [ ] Output correctness validated
- [ ] Critical business workflow validated
- [ ] Prototype limitations documented when applicable
- [ ] Successful prototype testing not represented as validation of a future Angular production UI

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Backend Validation

Apply when backend functionality is affected.

- [ ] Business logic validated
- [ ] API behaviour validated
- [ ] Persistence validated where applicable
- [ ] Transaction behaviour validated where applicable
- [ ] External integrations validated where applicable
- [ ] Error behaviour validated
- [ ] Input validation behaviour validated
- [ ] Contract compatibility validated

Technology-specific repository conventions have been respected for:

`Python / Java / Existing technology / N/A`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# MCP Validation

Apply only when MCP exists.

- [ ] Tool discovery validated where relevant
- [ ] Tool name validated
- [ ] Tool input contract validated
- [ ] Tool output contract validated
- [ ] Invalid input handling validated
- [ ] Resource contract validated where applicable
- [ ] Prompt contract validated where applicable
- [ ] Authentication behaviour validated where applicable
- [ ] Authorization behaviour validated where applicable
- [ ] State-changing behaviour validated
- [ ] Error behaviour validated
- [ ] External integration failures considered
- [ ] Regression coverage added for fixed MCP contract defects where practical

QA validates behaviour.

Security Engineer owns security implications.

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Security-Control Functional Validation

Apply when requested by Security Engineer or when security-sensitive behaviour requires functional validation.

- [ ] Unauthorized access rejection tested where applicable
- [ ] Insufficient-permission rejection tested where applicable
- [ ] Expired credentials tested where applicable
- [ ] Invalid token behaviour tested where applicable
- [ ] Restricted-resource behaviour tested where applicable
- [ ] Invalid input rejection tested where applicable
- [ ] Relevant security regression tested where applicable

QA reports observed behaviour.

QA does not independently replace Security Engineer's security assessment or severity classification.

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# SonarQube and CI/CD Evidence

SonarQube is not a replacement for QA.

- [ ] SonarQube evidence reviewed when relevant and available
- [ ] CI/CD test evidence reviewed when available
- [ ] Test execution evidence distinguished from static-analysis results
- [ ] SonarQube PASS not treated as QA PASS
- [ ] Static-analysis findings not unnecessarily duplicated by QA
- [ ] Missing CI/CD evidence explicitly reported

SonarQube:

`PASS / FAIL / NOT AVAILABLE / NOT EXECUTED / N/A`

QA Functional Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Test Coverage

Coverage is evidence, not proof of correctness.

- [ ] Coverage evidence reviewed when available
- [ ] Verified project thresholds respected when applicable
- [ ] Mandatory corporate thresholds not invented
- [ ] Critical behaviour without tests identified
- [ ] Coverage gaps documented
- [ ] High numeric coverage not treated as proof of correctness
- [ ] Low coverage evaluated according to functionality and risk

Coverage Evidence:

`AVAILABLE / NOT AVAILABLE / NOT APPLICABLE`

Result:

PASS / FAIL / N/A

---

# Test Execution Evidence

For every relevant test category distinguish:

- [ ] Test exists
- [ ] Test execution verified
- [ ] Result verified
- [ ] CI/CD evidence identified where applicable
- [ ] NOT EXECUTED reported explicitly
- [ ] NOT AVAILABLE reported explicitly
- [ ] No test existence interpreted as execution
- [ ] No build success interpreted as functional PASS

Allowed states:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Defect Review

For each material defect:

- [ ] Component identified
- [ ] Severity supported by impact
- [ ] Evidence documented
- [ ] Preconditions documented where relevant
- [ ] Expected behaviour based on verified requirements
- [ ] Actual behaviour documented
- [ ] Functional or business impact documented
- [ ] Regression status identified
- [ ] Reproduction status explicit
- [ ] Reproduction steps not invented when execution did not occur

Allowed severity:

```text
CRITICAL
MAJOR
MINOR
```

Result:

PASS / FAIL / N/A

---

# Critical QA Gates

QA must recommend BLOCK when an applicable demonstrated critical condition exists.

- [ ] No critical business workflow is broken
- [ ] No material data-corruption risk is demonstrated
- [ ] No material data-loss risk is demonstrated
- [ ] No mandatory API or integration contract is broken
- [ ] No critical regression remains unresolved
- [ ] No required critical test is failing
- [ ] No required access-control behaviour is functionally broken
- [ ] No production-critical integration is demonstrably broken

If an applicable item fails:

QA Gate = FAILED

QA Recommendation = BLOCK

Result:

PASS / FAIL / N/A

---

# QA Evidence Summary

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Technology Context:

`_____________________`

Unit Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Integration Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Contract Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

E2E Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Regression Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Negative Tests:

`DEFINED / EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Security-Control Validation:

`EXECUTED - PASS / EXECUTED - FAIL / NOT EXECUTED / NOT AVAILABLE / N/A`

Coverage Evidence:

`AVAILABLE / NOT AVAILABLE / N/A`

Missing QA Evidence:

`_____________________`

---

# Regression Risk Assessment

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

# QA Gate Result

Allowed values:

```text
PASSED
CONDITIONAL
FAILED
```

Result:

`_____________________`

---

# QA Recommendation

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

# QA Engineer Sign-Off

Reviewer:

`_____________________`

Date:

`_____________________`

QA Gate:

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

---

# Definition of QA Readiness

A solution is considered QA-ready for its intended lifecycle when:

- Requirements are understood.
- Acceptance criteria are known or missing information is explicit.
- Testing depth matches lifecycle and risk.
- Critical flows have been evaluated.
- Relevant negative scenarios have been considered.
- Contract compatibility has been evaluated where applicable.
- Regression risk has been evaluated.
- Data processing has been validated where applicable.
- Frontend behaviour has been validated where applicable.
- Backend behaviour has been validated where applicable.
- MCP behaviour has been validated where applicable.
- Security controls have been functionally validated when required.
- Existing tests have been distinguished from executed tests.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Build success has not been treated as functional PASS.
- SonarQube PASS has not been treated as QA PASS.
- Coverage percentages have not been invented.
- Material defects are evidence-based.
- Reproduction steps have not been invented.
- Critical functional blockers are explicit.
- Missing test evidence is explicit.
- Regression risk is understood.
- QA Gate has been produced.
- QA Recommendation is traceable to verified evidence.
