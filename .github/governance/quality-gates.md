# Quality Gates

Version: 2.0

---

# Purpose

Quality Gates define evidence-based validation points used to determine whether an engineering change satisfies the requirements applicable to its scope, lifecycle, risk, architecture, technology, and deployment context.

Quality Gates provide standardized domain decisions.

They do not replace specialist engineering judgement.

Not every change requires every gate.

Gate applicability must be determined before evaluation.

The objectives are to ensure that:

- Applicable engineering concerns are validated.
- Irrelevant gates are not executed unnecessarily.
- Missing evidence is not converted into PASS.
- Critical blockers remain visible.
- Conditional approval does not bypass mandatory controls.
- Specialist authority is respected.
- Final engineering decisions remain traceable to evidence.

---

# Core Principles

Always apply:

- Evidence before PASS
- Lifecycle-aware validation
- Risk-based gate selection
- Domain-specific authority
- Minimum necessary gates
- Explicit applicability
- Explicit missing evidence
- No fabricated execution
- No fabricated approval
- No universal gate hierarchy

Mandatory rules:

```text
NOT EXECUTED != PASSED
NOT AVAILABLE != PASSED
DEFINED != EXECUTED
CONFIGURED != EXECUTED
AGENT DEFINED != AGENT PARTICIPATED
```

---

# Lifecycle Context

Gate applicability and required evidence must reflect the approved lifecycle.

Supported lifecycle values:

```text
Experiment
Prototype / PoC
MVP
Production
```

## Experiment

Apply only gates required to validate:

- Technical feasibility
- Critical correctness
- Critical security
- Critical data integrity
- Experiment-specific objectives

Do not require production-level gates without justification.

## Prototype / PoC

Apply gates required to validate:

- Business or technical assumptions
- Critical functionality
- Important integrations
- Critical security boundaries
- Data handling
- Explicit prototype limitations

A successful PoC does not imply production readiness.

## MVP

Evaluate applicable:

- Architecture
- Implementation
- Functional quality
- Security
- Deployment
- Performance
- Documentation

according to actual impact and risk.

## Production

Evaluate all gates materially applicable to safe production delivery.

Do not assume every gate applies automatically.

Applicability still depends on:

- Change scope
- Architecture
- Security impact
- Functional impact
- Deployment impact
- Performance impact
- Documentation requirements
- AI / LLM functionality
- Agentic functionality

---

# Gate Applicability

Before evaluating gates, determine which gates apply.

Possible gate states include:

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

Gate applicability must be supported by:

- Scope
- Lifecycle
- Requirements
- Architecture
- Technology
- Risk
- Change type
- Deployment impact
- Security impact
- Functional impact

Do not mark a gate as PASSED simply because it is not relevant.

Use:

```text
NOT APPLICABLE
```

when it does not apply.

Use:

```text
NOT DETERMINED
```

when applicability cannot yet be established.

When gate applicability is answer-critical and cannot be determined, the final recommendation may require:

```text
NEEDS MORE INFO
```

---

# Gate Result Vocabulary

An applicable gate must use one of:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
```

A non-applicable gate uses:

```text
NOT APPLICABLE
```

## PASSED

Use only when:

- The gate applies.
- Required evidence is available.
- Required validation has been performed.
- No blocking domain finding remains.

## CONDITIONAL

Use when:

- The gate applies.
- No critical blocker remains.
- Remaining issues are non-critical.
- Required conditions are explicit.
- Required follow-up evidence is explicit.

## FAILED

Use when:

- The gate applies.
- A mandatory or critical blocker remains.
- Required validation demonstrates failure.

## NOT EXECUTED

Use when:

- The gate applies or may apply.
- Required evaluation has not been executed.

## NOT AVAILABLE

Use when:

- The gate applies.
- Required evidence cannot currently be retrieved or verified.

## NOT APPLICABLE

Use when:

- The gate does not apply to the current scope.

---

# Gate Result vs Recommendation

A gate result and a specialist recommendation are different concepts.

Example:

```text
Security Gate:
CONDITIONAL

Security Recommendation:
CONDITIONAL APPROVAL
```

Gate vocabulary:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Recommendation vocabulary:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Do not mix these vocabularies.

---

# Gate Evidence Rule

Every applicable gate must identify supporting evidence.

Evidence may include:

- Repository code
- Repository configuration
- Approved architecture
- Approved requirements
- Checklists
- Test execution
- CI/CD execution
- SonarQube
- Dependency analysis
- Security testing
- Ethical Hacking / Assurance
- Deployment evidence
- Performance measurements
- Documentation
- Human approval

A checklist completed without execution evidence does not prove execution occurred.

A tool configured in the repository does not prove it executed.

---

# Missing Evidence Rule

Missing evidence must be explicit.

For material missing evidence record:

```text
Evidence:
Status:
Impact:
Validation required:
```

Impact may be:

```text
BLOCKING
NON-BLOCKING
INFORMATIONAL
```

If required evidence is unavailable and no safe gate decision can be produced:

```text
Gate Result:
NOT AVAILABLE

Recommendation:
NEEDS MORE INFO
```

Do not guess a PASSED result.

---

# Architecture Gate

## Owner

Solution Architect

## Applicability

Evaluate when the change materially affects:

- System architecture
- Technology selection
- System boundaries
- Service boundaries
- Data ownership
- Major integration patterns
- Deployment architecture
- Prototype-to-production architecture
- Technology migration

## PASSED

Use when applicable evidence demonstrates:

- Approved architecture is respected.
- Required system boundaries are clear.
- Technology decisions are justified.
- Material integrations are architecturally valid.
- No blocking architectural risk remains.

## CONDITIONAL

Use when:

- No critical architecture blocker remains.
- Architectural debt is explicit.
- Follow-up work is defined.
- Remaining risk is acceptable for the lifecycle.

## FAILED

Use when applicable conditions include:

- Critical architecture violation
- Unsatisfied verified requirement
- Unauthorized technology migration
- Invalid system boundary
- Critical prototype-to-production assumption
- Architecture creates an unresolved mandatory security or operational conflict

## Evidence

Possible evidence:

- Architecture review
- HLD
- Detailed design
- ADR
- Repository architecture
- Approved technology decision

---

# Backend Gate

## Owner

Backend Engineer

## Applicability

Evaluate when backend implementation is materially affected.

Examples:

- APIs
- Business logic
- Persistence
- Data processing
- Backend integration
- Python
- Java
- Python MCP

## PASSED

Use when:

- Approved architecture is respected.
- Implementation is complete for the verified scope.
- Required contracts are implemented.
- Data integrity is preserved.
- Input validation is appropriate.
- Error handling is appropriate.
- Required implementation tests have supporting evidence.
- No blocking backend defect remains.

## CONDITIONAL

Use when:

- No critical backend blocker remains.
- Remaining technical debt is non-critical.
- Test or implementation conditions are explicit.
- Remaining risk is understood.

## FAILED

Use when applicable conditions include:

- Critical implementation defect
- Critical data-integrity risk
- Broken mandatory backend contract
- Unsafe database change
- Unauthorized technology change
- Critical required backend test failure

Backend Gate does not replace:

- QA Gate
- Security Gate
- Code Review Gate

---

# Frontend Gate

## Owner

Frontend Systems Engineer

## Applicability

Evaluate when frontend implementation is materially affected.

Examples:

- Angular
- Streamlit
- Existing frontend framework
- Forms
- State
- API integration
- Routes
- User workflows

## PASSED

Use when:

- Approved architecture is respected.
- Required user behaviour is implemented.
- Required UI states are handled.
- API integration is compatible.
- Accessibility has been considered appropriately.
- Frontend security concerns have been addressed or escalated.
- Required implementation tests have supporting evidence.
- No blocking frontend defect remains.

## CONDITIONAL

Use when:

- No critical frontend blocker remains.
- Non-critical UX, accessibility, testing, or technical debt remains.
- Conditions are explicit.

## FAILED

Use when applicable conditions include:

- Critical user flow is broken.
- Mandatory API contract is incompatible.
- Critical frontend implementation defect exists.
- Critical required accessibility behaviour is broken.
- Security-sensitive frontend behaviour is demonstrably unsafe.
- Unauthorized framework migration exists.
- Required critical frontend test fails.

Frontend Gate does not replace QA Gate or Security Gate.

---

# Security Gate

## Owner

Security Engineer

## Applicability

Evaluate when security is materially relevant.

Examples include:

- Authentication
- Authorization
- Sensitive data
- Secrets
- Credentials
- Certificates
- External exposure
- API security
- Database security
- File security
- Infrastructure security
- Dependency vulnerability
- MCP
- AI / LLM
- Agentic systems
- Security remediation
- Verified mandatory security process

## Evidence

Consider applicable:

- Corporate security requirements
- Project-specific requirements
- Risk Assessment
- Security Annex
- Secure Coding
- Threat modeling
- SonarQube
- Dependency analysis
- Dynamic security testing
- API security testing
- Ethical Hacking / Assurance
- Manual security review
- QA security-control validation
- Remediation evidence

## PASSED

Use when:

- Applicable security controls are satisfied.
- Required security evidence is available.
- No critical blocker remains.
- Mandatory security gates pass where applicable.
- Residual risk is acceptable under the applicable process.

## CONDITIONAL

Use when:

- No critical security blocker remains.
- Remaining findings are non-critical.
- Remediation is explicit.
- Required validation is explicit.
- Mandatory controls are not being bypassed.

## FAILED

Use when an applicable unresolved condition exists such as:

- Critical authentication bypass
- Critical authorization bypass
- Critical privilege escalation
- Critical sensitive-data exposure
- Exposed sensitive credentials
- Critical injection
- Missing verified mandatory security control
- Failed mandatory security assurance
- Critical unresolved Ethical Hacking finding without required treatment
- Failed verified mandatory security gate with blocking findings

Security Gate PASS does not imply all other gates pass.

---

# SonarQube Evidence

SonarQube may contribute to:

- Security Gate
- Code Review Gate
- CI/CD evidence

SonarQube itself is not a universal engineering gate unless verified project or corporate requirements make it mandatory.

Possible states:

```text
PASS
FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Apply:

```text
SonarQube PASS != Security Gate PASSED
SonarQube PASS != QA Gate PASSED
SonarQube PASS != Code Review Gate PASSED
SonarQube PASS != Production readiness
```

If SonarQube is a verified mandatory gate:

- Verify execution.
- Preserve the actual Quality Gate result.
- Do not treat missing analysis as PASS.
- Escalate mandatory failures.

---

# QA Gate

## Owner

QA Engineer

## Applicability

Evaluate when functional validation is materially required.

Examples:

- Feature changes
- Bug fixes
- Integration changes
- User-flow changes
- API behaviour changes
- Regression risk
- Security-control functional validation
- Data-processing changes

## Evidence

Consider applicable:

- Acceptance criteria
- Unit-test execution
- Integration tests
- Contract tests
- E2E tests
- Regression tests
- Negative tests
- Data validation
- Security-control behaviour

## PASSED

Use when:

- Required tests have supporting execution evidence.
- Critical flows pass.
- Required contracts are compatible.
- No blocking functional defect remains.
- Regression risk is controlled for the lifecycle.

## CONDITIONAL

Use when:

- No critical functional blocker remains.
- Remaining defects or test gaps are non-critical.
- Conditions are explicit.
- Remaining regression risk is understood.

## FAILED

Use when:

- Critical workflow fails.
- Core business functionality is broken.
- Material data-loss or corruption behaviour is demonstrated.
- Mandatory contract is broken.
- Critical regression remains.
- Required critical test fails.

QA Gate must not use:

```text
Test exists
```

as equivalent to:

```text
Test passed
```

---

# Code Review Gate

## Owner

Code Reviewer

## Applicability

Evaluate when implementation-quality review is materially required.

Examples:

- Production code change
- Security-sensitive implementation
- Material refactor
- Complex defect fix
- Contract implementation
- High-risk implementation change

## Evidence

Consider:

- Repository context
- Changed code
- Contracts
- Tests
- Architecture
- Dependency changes
- SonarQube evidence when applicable

## PASSED

Use when:

- Implementation is materially correct.
- Maintainability is acceptable.
- Architecture is respected.
- Contracts are correctly implemented.
- Test quality is appropriate.
- No blocking implementation defect remains.

## CONDITIONAL

Use when:

- No critical implementation blocker remains.
- Material non-critical issues are explicit.
- Required remediation is explicit.

## FAILED

Use when:

- Critical implementation defect exists.
- Critical data-integrity risk exists.
- Mandatory contract implementation is broken.
- Critical regression is introduced.
- Implementation violates approved architecture in a way that prevents safe delivery.
- Mandatory critical test is demonstrably failing.

Code Review Gate does not replace SonarQube, QA, or Security.

---

# DevOps Gate

## Owner

DevOps Engineer

## Applicability

Evaluate when delivery or operational behaviour is materially affected.

Examples:

- CI/CD
- Build
- Artifact
- Configuration
- Secrets integration
- Deployment
- Infrastructure
- Containers
- Runtime
- Database deployment
- Environment changes
- Production release

## PASSED

Use when:

- Applicable delivery requirements are satisfied.
- Mandatory pipeline gates pass.
- Required configuration is available.
- Deployment validation is sufficient for the lifecycle.
- Required rollback or recovery exists for the deployment risk.
- No critical operational blocker remains.

## CONDITIONAL

Use when:

- No critical deployment blocker remains.
- Remaining operational gaps are non-critical.
- Conditions are explicit.
- Remaining operational risk is understood.

## FAILED

Use when applicable conditions include:

- Production deployment is demonstrably unsafe.
- Mandatory pipeline gate fails.
- Critical configuration is invalid or missing.
- Required production secret is unavailable or exposed insecurely.
- Unsafe database deployment ordering exists.
- Deployment validation fails.
- High-risk production change has no viable required recovery path.

Do not fail a PoC solely because production-grade rollback, monitoring, tracing, or HA is absent.

---

# Performance Gate

## Owner

Performance Engineer

## Applicability

Evaluate when performance is materially relevant.

Examples:

- Verified performance requirement
- Performance-sensitive change
- Significant data growth
- Material concurrency
- Known bottleneck
- Performance regression
- Critical workload
- Capacity concern

## Evidence

Consider:

- Benchmarks
- Profiling
- Load testing
- Runtime metrics
- Query evidence
- Browser profiling
- Infrastructure evidence

Findings should distinguish:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

## PASSED

Use when:

- Applicable verified performance requirements are satisfied.
- No blocking performance finding remains.
- Required performance evidence is available.
- Performance-regression risk is controlled.

## CONDITIONAL

Use when:

- No critical performance blocker remains.
- Remaining concerns are non-critical.
- Required measurements or remediation are explicit.

## FAILED

Use when:

- Verified critical performance target is not met.
- Required workload causes resource exhaustion.
- Critical user flow is unusable against a verified requirement.
- Severe memory leak is demonstrated.
- Critical performance regression remains.
- Required production workload cannot be supported.

Do not fail solely because a theoretical optimization exists.

---

# Documentation Gate

## Owner

Documentation Engineer

## Applicability

Evaluate when documentation is materially required for:

- Safe implementation
- Integration
- Deployment
- Operation
- Security
- Support
- Architecture traceability
- API usage
- Production readiness

## PASSED

Use when:

- Required documentation exists.
- Documentation is materially accurate.
- Required evidence is represented correctly.
- No dangerous contradiction remains.
- Documentation is appropriate for its lifecycle and audience.

## CONDITIONAL

Use when:

- No critical documentation blocker remains.
- Remaining documentation gaps are non-critical.
- Conditions are explicit.

## FAILED

Use when:

- Documentation exposes real secrets.
- Critical deployment procedure is dangerously incorrect.
- Critical recovery procedure is dangerously incorrect.
- Required mandatory operational documentation is absent and prevents safe operation.
- Critical API documentation contradicts the actual mandatory contract.
- Production documentation falsely presents an unvalidated prototype as production-ready.

Documentation Gate is not universally non-blocking.

Its blocking impact depends on actual risk.

---

# LLM Gate

## Owner

Applicable engineering workflow using:

`LLM Engineering Skill`

Primary ownership normally remains with the responsible architecture or implementation specialist, with Security, QA, Performance, and other specialists contributing within their domains.

## Applicability

Evaluate only when material LLM functionality exists.

Examples:

- RAG
- Classification
- Extraction
- Summarization
- Structured generation
- LLM-powered assistant
- Tool-using LLM workflow

## Evidence

Consider:

- LLM applicability
- Grounding
- Context
- Retrieval
- Structured output
- Evaluation
- Security
- Output validation
- Observability
- Performance
- Cost when relevant

## PASSED

Use when:

- LLM usage is justified.
- Required grounding is adequate.
- Required evaluation evidence is available.
- Required output validation exists.
- No critical LLM blocker remains.

## CONDITIONAL

Use when:

- No critical blocker remains.
- Remaining model, retrieval, evaluation, or operational risks are non-critical.
- Conditions are explicit.

## FAILED

Use when applicable:

- Critical sensitive-data leakage exists.
- Critical authorization bypass exists through the LLM workflow.
- Critical prompt injection enables privileged action.
- Unauthorized retrieval exposes protected data.
- Critical output controls required for a high-impact workflow are absent.
- Mandatory production evaluation fails critically.

When LLM functionality is agentic, also evaluate the Agentic Gate.

---

# Agentic Gate

## Owner

Applicable engineering workflow using:

`Agentic Systems Engineering Skill`

Domain ownership remains with the applicable specialists.

## Applicability

Evaluate only when material agentic behaviour exists.

Examples:

- Dynamic planning
- Delegation
- Agent routing
- Autonomous tool use
- Multi-agent behaviour
- Persistent agent memory
- State-changing autonomous actions

## Evidence

Consider:

- Agentic necessity
- Agent responsibilities
- Authority
- Delegation
- Tool permissions
- Side effects
- Human approval
- State
- Memory
- Loop prevention
- Security
- Traceability
- Evaluation

## PASSED

Use when:

- Agentic behaviour is justified.
- Authority is explicit.
- Tools follow Least Privilege.
- Required human approval is implemented.
- Delegation is bounded.
- Stopping conditions exist.
- No critical agentic blocker remains.

## CONDITIONAL

Use when:

- No critical blocker remains.
- Remaining agentic risks are non-critical.
- Conditions and evaluation requirements are explicit.

## FAILED

Use when applicable:

- Unrestricted privileged tool execution exists.
- Critical delegation abuse exists.
- Critical data-exfiltration path exists.
- Autonomous destructive production action can occur without approval.
- Critical prompt injection can trigger privileged action.
- Mandatory human approval can be bypassed.
- High-risk workflow has no safe stopping condition.
- Critical false approval or governance bypass exists.

---

# Gate Selection by Change Type

Change type may help identify candidate gates.

It must not create a universal gate list.

## Feature

Consider according to scope:

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

Select only applicable gates.

## Bug Fix

Usually consider:

- Responsible implementation gate
- QA
- Code Review

Also consider:

- Security
- DevOps
- Performance
- Documentation

when affected.

## Refactor

Usually consider:

- Responsible implementation gate
- Code Review
- QA

Architecture Gate applies when boundaries or architecture are materially affected.

Performance applies when performance risk exists.

## Security Change

Usually consider:

- Security
- Responsible implementation gate
- QA
- Code Review

DevOps applies when deployment or infrastructure is affected.

## Infrastructure Change

Usually consider:

- DevOps
- Security when applicable
- QA when functional behaviour requires validation
- Performance when runtime characteristics are affected
- Architecture when platform boundaries materially change

## Documentation-Only Change

Usually consider:

- Documentation Gate

Additional gates apply only when the documentation change exposes a substantive engineering conflict requiring specialist validation.

## Performance Change

Usually consider:

- Performance
- Responsible implementation gate
- QA
- Code Review

Security applies if security controls are affected.

## LLM Change

Consider:

- LLM Gate
- Security
- QA
- Performance where material
- Responsible implementation gate
- Code Review

Agentic Gate applies only when agentic behaviour exists.

## Agentic Change

Consider:

- Agentic Gate
- LLM Gate when LLM functionality exists
- Security
- QA
- Performance where material
- Responsible implementation gate
- Code Review
- DevOps when runtime or deployment is affected

---

# Production Release Gate Selection

A production release does not automatically require every possible gate.

Before release identify all materially applicable production gates based on:

- Change scope
- Architecture
- Technology
- Functional impact
- Security impact
- Deployment impact
- Data impact
- Performance impact
- Documentation requirements
- AI / LLM functionality
- Agentic functionality

All verified mandatory applicable gates must satisfy the required governance state before approval.

Do not execute irrelevant gates simply because the target environment is production.

---

# Gate Aggregation

The Orchestrator aggregates applicable gate results.

There is no universal priority order such as:

```text
Security
> QA
> Performance
> DevOps
> Architecture
```

Instead:

1. Identify applicable gates.
2. Identify FAILED gates.
3. Identify critical blocking findings.
4. Identify CONDITIONAL gates.
5. Identify NOT EXECUTED or NOT AVAILABLE mandatory evidence.
6. Identify specialist conflicts.
7. Identify human-approval requirements.
8. Produce the final engineering decision.

---

# Failed Gate Rule

If an applicable mandatory gate is:

```text
FAILED
```

and the failure represents an unresolved mandatory or critical blocker:

```text
Final Decision:
BLOCK
```

until:

- Remediation occurs
- Required validation proves resolution
- Or formal authorized treatment exists where governance permits it

The Orchestrator may not silently convert FAILED into PASSED.

---

# Conditional Gate Rule

A CONDITIONAL gate may support:

```text
CONDITIONAL APPROVAL
```

when:

- No critical blocker remains.
- Applicable mandatory controls are not bypassed.
- Conditions are explicit.
- Responsible work streams are explicit.
- Required validation is explicit.

Multiple CONDITIONAL gates require cumulative-risk evaluation.

Do not assume that multiple medium findings automatically create BLOCK.

Evaluate actual combined impact.

---

# NOT EXECUTED Rule

If an applicable mandatory gate is:

```text
NOT EXECUTED
```

determine whether the missing execution is required before safe decision.

If required:

```text
Final Decision:
NEEDS MORE INFO
```

or:

```text
BLOCK
```

only when verified governance explicitly makes non-execution itself blocking.

Do not invent a failed result when the true state is not executed.

---

# NOT AVAILABLE Rule

If required evidence is:

```text
NOT AVAILABLE
```

use:

```text
NEEDS MORE INFO
```

when a safe determination cannot be made.

Do not guess PASS or FAIL.

---

# NOT APPLICABLE Rule

A gate marked:

```text
NOT APPLICABLE
```

must include enough context to understand why it does not apply when material.

Do not use NOT APPLICABLE simply to avoid an inconvenient gate.

---

# Final Decision Rules

The final engineering decision uses exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## APPROVE

Use when:

- All applicable mandatory gates requiring execution are PASSED.
- No unresolved critical blocker remains.
- Required evidence is available.
- Required human approval has been obtained when applicable.
- No unresolved conflict prevents safe delivery.

## CONDITIONAL APPROVAL

Use when:

- No critical blocker remains.
- Applicable gates allow conditional progression.
- Conditions are explicit.
- Required follow-up is explicit.
- Mandatory controls are not bypassed.
- Required human approval is satisfied when applicable.

## BLOCK

Use when:

- An applicable unresolved critical blocker exists.
- A mandatory applicable gate fails.
- A verified blocking control is absent.
- Safe delivery cannot continue.

## NEEDS MORE INFO

Use when:

- Answer-critical evidence is unavailable.
- Mandatory gate execution evidence is unavailable.
- Applicability cannot be determined.
- Requirements are unclear.
- Specialist conflict cannot be resolved safely.
- Human approval status is required but unavailable.

---

# Human Approval Governance

Human approval is not a universal gate.

Evaluate it when required by risk or governance.

Possible applicability states:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Typical cases requiring evaluation include:

- Production changes
- Destructive actions
- Irreversible migration
- Formal risk acceptance
- High-impact permission changes
- Credential changes
- Public exposure
- Emergency changes
- Critical uncertainty
- Agentic production actions
- Governance changes

Approval must not be reported as granted without evidence.

---

# Formal Risk Acceptance

No Quality Gate grants formal risk acceptance.

Agents and the Orchestrator may identify:

- Residual risk
- Compensating controls
- Required treatment
- Required governance decision

Formal risk acceptance belongs to the applicable authorized human or corporate governance process.

Do not use:

```text
CONDITIONAL APPROVAL
```

as a substitute for formal risk acceptance when formal acceptance is required.

---

# Cross-Gate Conflicts

When gates conflict:

1. Identify the domains.
2. Preserve each specialist result.
3. Identify actual evidence.
4. Identify blocking conditions.
5. Request clarification if necessary.
6. Apply domain-specific authority.
7. Escalate unresolved governance decisions.

Example:

```text
Security Gate:
PASSED

QA Gate:
FAILED
```

Final decision cannot be APPROVE while the critical QA blocker remains.

Example:

```text
QA Gate:
PASSED

Security Gate:
FAILED
```

Final decision cannot be APPROVE while the critical Security blocker remains.

No gate wins merely because of a global priority ranking.

---

# Gate Execution Summary

For material workflows record applicable gates using a structure such as:

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

Only report gates relevant to the actual workflow when a shorter output is preferable.

---

# Gate Conditions Format

For every CONDITIONAL gate record when applicable:

```text
Condition:
Responsible area:
Required action:
Evidence required:
Validation:
```

Conditions must be actionable.

Avoid vague conditions such as:

```text
Improve quality later.
```

---

# Blocking Finding Format

For every material gate blocker record:

```text
Gate:
Owner:
Finding:
Severity:
Evidence:
Impact:
Required remediation:
Validation required:
```

Do not fabricate severity or evidence.

---

# Missing Gate Evidence Format

For required evidence that is unavailable record:

```text
Gate:
Missing evidence:
Expected source:
Impact:
Required next validation:
```

Do not report the expected source as if it had already been retrieved.

---

# Traceability

Gate evaluation should be traceable to the degree required by lifecycle and risk.

Record when provided by the execution environment:

- Execution identifier
- Lifecycle
- Scope
- Participating agents
- Gate owner
- Evidence
- Gate result
- Blocking findings
- Conditions
- Missing evidence
- Human-approval status
- Final engineering decision
- Timestamp

Do not fabricate:

- Execution identifiers
- Change identifiers
- Timestamps
- Agent participation
- Tool execution
- Human approval

---

# Audit Requirements

A material Quality Gate decision should allow a reviewer to determine:

- Why the gate applied
- Who owned the gate
- Which evidence was reviewed
- Whether required execution occurred
- Why the gate passed, became conditional, failed, or lacked evidence
- Which blockers existed
- Which conditions remained
- What validation is still required
- How the gate contributed to the final engineering decision

Audit depth must remain proportional to lifecycle and risk.

---

# Quality Gate Anti-Patterns

Avoid:

## Every Gate for Every Change

Applying all gates regardless of scope.

## False PASS

Representing missing evidence as success.

## Gate Priority Hierarchy

Using a universal gate ranking instead of domain authority.

## Checklist as Evidence

Treating a checklist definition as executed validation.

## Test File as Test PASS

Treating test existence as execution evidence.

## SonarQube as Universal Gate

Treating SonarQube PASS as complete QA, Security, Code Review, or production approval.

## Conditional Approval as Bypass

Using conditions to avoid mandatory blockers.

## NOT APPLICABLE Abuse

Marking a gate irrelevant without supporting context.

## Invented Mandatory Gate

Declaring a gate mandatory without verified governance or project evidence.

## Production Gate Inflation

Requiring every specialist gate merely because the target environment is production.

## Prototype Gate Inflation

Applying production-grade validation to disposable prototypes without risk justification.

## False Human Approval

Reporting an approval that was not provided.

---

# Quality Gate Output Format

## Gate Context

Report:

- Change scope
- Lifecycle
- Risk
- Applicable technology
- Environment when relevant

## Gate Applicability

List applicable and non-applicable gates.

## Gate Results

Report only actual evidence-backed states.

## Blocking Findings

List unresolved blocking conditions.

## Conditions

List non-blocking conditions.

## Missing Evidence

List any evidence preventing a stronger gate result.

## Human Approval

When relevant:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

## Residual Risk

When applicable use:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

## Final Engineering Decision

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## Rationale

Explain how applicable gate evidence supports the decision.

---

# Definition of Done

Quality Gate evaluation is complete when:

- Change scope is understood.
- Lifecycle has been considered.
- Risk has been considered.
- Gate applicability has been evaluated.
- Irrelevant gates have not been executed unnecessarily.
- Applicable gate owners are identified.
- Required evidence has been identified.
- Gate execution status is explicit.
- NOT EXECUTED has not been treated as PASSED.
- NOT AVAILABLE has not been treated as PASSED.
- DEFINED has not been treated as EXECUTED.
- Applicable architecture concerns have been evaluated.
- Applicable backend concerns have been evaluated.
- Applicable frontend concerns have been evaluated.
- Applicable security concerns have been evaluated.
- Applicable QA concerns have been evaluated.
- Applicable Code Review concerns have been evaluated.
- Applicable DevOps concerns have been evaluated.
- Applicable performance concerns have been evaluated.
- Applicable documentation concerns have been evaluated.
- LLM Gate has been evaluated when material LLM functionality exists.
- Agentic Gate has been evaluated when material agentic behaviour exists.
- SonarQube has not been treated as universal approval.
- Test existence has not been treated as test execution.
- Conditional approval has not bypassed mandatory controls.
- Formal risk acceptance has not been invented.
- Required human approval has been evaluated.
- Blocking findings are explicit.
- Conditions are explicit.
- Missing evidence is explicit.
- Gate conflicts have been resolved by domain authority or escalated.
- Final engineering decision is traceable to applicable gate evidence.

---

# Goal

Ensure that every engineering change is evaluated only through the quality gates that materially apply to its lifecycle, scope, risk, architecture, technology, and delivery context, and that no gate is passed without evidence, no mandatory blocker is hidden by conditional approval, and no final engineering decision is produced without traceable domain-specific validation.