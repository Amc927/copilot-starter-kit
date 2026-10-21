# Bug Fix Workflow

Version: 2.0

---

# Purpose

This workflow defines the evidence-based process for identifying, reproducing, analyzing, fixing, validating, and governing software defects.

The objective is to restore verified expected behaviour while:

- Addressing the actual defect when determinable
- Preserving architecture
- Minimizing regression risk
- Protecting data integrity
- Protecting security
- Preserving compatibility
- Controlling operational risk
- Producing traceable validation evidence

This workflow may apply to:

- Functional defects
- Regression defects
- Production incidents
- User-reported issues
- Integration failures
- Data-processing errors
- API defects
- Frontend defects
- Backend defects
- Infrastructure defects
- Performance defects
- Security defects
- MCP defects
- LLM defects
- Agentic-system defects
- Documentation defects when incorrect documentation causes or contributes to software or operational failure

Not every defect requires every agent or every Quality Gate.

Routing and validation must reflect:

- Scope
- Lifecycle
- Technology
- Risk
- Impact
- Available evidence

---

# Workflow Principles

Always apply:

- Evidence before conclusion
- Reproduce before claiming reproduction
- Root cause before broad remediation when practical
- Correctness before convenience
- Regression prevention
- Minimum necessary change
- Minimum necessary agent routing
- Lifecycle-aware validation
- Risk-based Quality Gates
- Specialist authority by domain
- Explicit uncertainty
- Traceable decisions

Mandatory rules:

```text
Bug reported != Bug reproduced
Suspected root cause != Confirmed root cause
Test defined != Test executed
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
Agent defined != Agent participated
```

---

# Evidence Classification

Classify material conclusions when useful as:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

Do not present inferred information as verified fact.

---

# Defect Reproduction Status

Use exactly one of:

```text
REPRODUCED
OBSERVED
INFERRED
NOT REPRODUCED
NOT EXECUTED
NOT AVAILABLE
```

## REPRODUCED

Use when the reported defect has been intentionally reproduced through execution.

## OBSERVED

Use when the defective behaviour was directly observed through available runtime evidence but was not independently reproduced.

Examples may include:

- Verified logs
- Monitoring evidence
- Existing failing test
- Verified incident evidence

## INFERRED

Use when repository evidence strongly suggests the defect but runtime reproduction is unavailable.

## NOT REPRODUCED

Use when reproduction was attempted but the reported behaviour did not occur.

## NOT EXECUTED

Use when reproduction was not attempted.

## NOT AVAILABLE

Use when the environment, data, access, or evidence required for reproduction is unavailable.

Never report:

```text
REPRODUCED
```

without execution evidence.

---

# Root Cause Status

Use exactly one of:

```text
CONFIRMED
PROBABLE
NOT DETERMINED
NOT APPLICABLE
```

## CONFIRMED

Use when sufficient evidence supports the actual cause of the defect.

## PROBABLE

Use when available evidence strongly suggests a cause but complete confirmation is unavailable.

## NOT DETERMINED

Use when the root cause cannot safely be established.

## NOT APPLICABLE

Use only when root-cause analysis is genuinely unnecessary for the scoped workflow.

Never represent:

```text
PROBABLE
```

as:

```text
CONFIRMED
```

A fix may proceed against a probable cause only when the risk is understood and validation can demonstrate that the required behaviour is restored.

---

# Lifecycle Context

Identify the approved lifecycle when relevant:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Bug-fix depth must reflect lifecycle and risk.

## Experiment

Prioritize:

- Defect understanding
- Feasibility
- Critical correctness
- Critical safety

Do not impose unnecessary production process.

## Prototype / PoC

Prioritize:

- Required business behaviour
- Integration feasibility
- Data correctness
- Critical failure behaviour
- Prototype limitations

Do not represent a fixed PoC as production-ready.

## MVP

Evaluate appropriate:

- Core behaviour
- Regression safety
- Maintainability
- Important integrations
- Security
- Deployment impact

## Production

Evaluate appropriate:

- Critical behaviour
- Regression
- Security
- Data integrity
- Compatibility
- Deployment
- Recovery
- Performance
- Documentation
- Operational impact

---

# Workflow Overview

```text
Bug Intake
    ↓
Scope and Lifecycle
    ↓
Evidence Collection
    ↓
Reproduction
    ↓
Impact and Risk
    ↓
Minimum Agent Routing
    ↓
Root Cause Analysis
    ↓
Fix Strategy
    ↓
Implementation
    ↓
Regression Validation
    ↓
Applicable Quality Gates
    ↓
Findings Aggregation
    ↓
Conflict Resolution
    ↓
Orchestrator Final Decision
```

Stages may iterate when new evidence invalidates an earlier conclusion.

Do not create open-ended cycles.

---

# Stage 1 - Bug Intake

## Owner

Orchestrator

## Objective

Understand the reported defect without assuming the report is already verified.

Collect available:

- Defect summary
- Reported behaviour
- Expected behaviour
- Affected application
- Affected environment
- Lifecycle
- Reproduction steps
- Frequency
- First known occurrence
- Recent relevant changes
- Business impact
- User impact

Additional evidence may include:

- Logs
- Screenshots
- Error messages
- Test failures
- Monitoring evidence
- Incident references
- API examples
- Input files
- Output files
- Configuration
- Pipeline evidence

Do not invent missing reproduction information.

---

# Stage 2 - Scope and Context

## Owner

Orchestrator

Identify:

- Lifecycle
- Affected components
- Technology
- Environment
- Backend impact
- Frontend impact
- Data impact
- Integration impact
- Security impact
- Deployment impact
- Performance impact
- Documentation impact
- MCP applicability
- LLM applicability
- Agentic applicability

Technology may include:

- Python
- Java
- Angular
- Streamlit
- Existing repository technologies

Do not change technology during bug fixing unless an architectural decision explicitly requires it.

---

# Stage 3 - Initial Classification

Classify the defect into one or more applicable categories.

## Functional Defect

Examples:

- Incorrect calculation
- Incorrect business rule
- Invalid workflow
- Missing expected behaviour

## Integration Defect

Examples:

- API contract failure
- External-service failure
- Data synchronization defect
- Incorrect dependency behaviour

## Data Defect

Examples:

- Incorrect transformation
- Data inconsistency
- Duplicate processing
- Data corruption
- Incorrect persistence

## Frontend Defect

Examples:

- Broken UI state
- Form failure
- Routing failure
- Incorrect API integration
- Accessibility regression

## Backend Defect

Examples:

- Business-logic failure
- Persistence failure
- Transaction failure
- API implementation defect

## Security Defect

Examples:

- Authentication failure
- Authorization failure
- Data exposure
- Secret exposure
- Security-control regression

## Performance Defect

Examples:

- Latency regression
- Resource exhaustion
- Database bottleneck
- Data-processing slowdown

## Deployment / Infrastructure Defect

Examples:

- Configuration failure
- Pipeline failure
- Runtime failure
- Deployment failure
- Environment mismatch

## MCP Defect

Examples:

- Invalid tool contract
- Tool failure
- Resource failure
- Incorrect state-changing behaviour

## LLM Defect

Examples:

- Grounding failure
- Invalid structured output
- Retrieval defect
- Citation defect
- Model regression

## Agentic Defect

Examples:

- Incorrect routing
- Delegation failure
- Tool-selection failure
- Loop
- Authority violation

Classification may change as evidence improves.

---

# Stage 4 - Evidence Collection

## Objective

Collect enough evidence to reproduce, understand, or safely classify the defect.

Inspect applicable:

- Repository code
- Repository configuration
- Existing tests
- API contracts
- Data contracts
- Database configuration
- External integrations
- CI/CD
- Deployment configuration
- Runtime configuration
- Logs
- Monitoring
- Previous findings
- Existing documentation
- Relevant architecture

When a technology-specific issue exists, identify the corresponding engineering skill.

Examples:

```text
Python
→ Python Engineering Skill
```

```text
Java
→ Java Engineering Skill
```

```text
Angular
→ Endesa Corporate Angular Engineering Skill
```

```text
Python MCP
→ Python Engineering Skill
+ Python MCP Engineering Skill
```

```text
LLM
→ LLM Engineering Skill
```

```text
Agentic system
→ Agentic Systems Engineering Skill
```

Do not activate irrelevant skills.

---

# Stage 5 - Reproduction

## Objective

Determine whether the reported defect can be verified.

Attempt reproduction when:

- Safe
- Useful
- Technically possible
- Required for reliable diagnosis

Avoid unsafe reproduction against production when it may cause:

- Data loss
- Data corruption
- Security exposure
- Irreversible state changes
- Business disruption

Use a safer environment or existing production evidence when appropriate.

Report exactly one:

```text
REPRODUCED
OBSERVED
INFERRED
NOT REPRODUCED
NOT EXECUTED
NOT AVAILABLE
```

Record:

- Environment
- Preconditions
- Inputs
- Steps
- Expected behaviour
- Actual behaviour
- Evidence

Do not invent reproduction steps.

---

# Stage 6 - Expected Behaviour Validation

Before calling behaviour defective, verify the expected behaviour.

Possible sources:

- Acceptance criteria
- Approved requirement
- Existing contract
- Business rule
- Architecture
- Existing verified tests
- Current documentation when authoritative
- User-provided requirement

Classify expected behaviour as:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
```

If expected behaviour is answer-critical and cannot be established:

```text
NEEDS MORE INFO
```

may be required.

Do not fix behaviour toward an invented expectation.

---

# Stage 7 - Impact and Risk Assessment

Assess actual or plausible impact from available evidence.

Consider:

- Business impact
- User impact
- Data integrity
- Security
- Availability
- Compatibility
- Performance
- Deployment
- Scope
- Frequency
- Recoverability
- Workaround
- Lifecycle

Use severity when helpful:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

Severity should reflect actual impact and context.

Do not inflate severity to increase priority.

Domain specialists retain authority for their domain-specific risk classification.

---

# Stage 8 - Minimum Agent Routing

## Owner

Orchestrator

Select only agents required for the defect.

Do not invoke every specialist automatically.

## Backend Engineer

Route when the defect materially affects:

- Python
- Java
- Backend service
- API implementation
- Business logic
- Database
- Backend integration
- Python MCP implementation

## Frontend Systems Engineer

Route when the defect materially affects:

- Angular
- Streamlit UI
- Existing frontend technology
- Form
- Route
- State
- Frontend API integration
- User interaction

A defect may require both Backend and Frontend Engineers.

## QA Engineer

Route when functional validation, regression validation, contract validation, or reproduction evidence is materially required.

QA should normally participate when a production or MVP defect requires formal validation, but applicability remains risk-based.

## Code Reviewer

Route when implementation-quality review is materially required.

Examples:

- Production code fix
- Complex fix
- High-risk fix
- Refactor performed during remediation
- Security-sensitive implementation

Do not make Code Reviewer mandatory for trivial non-production changes without justification.

## Security Engineer

Route when the defect affects:

- Authentication
- Authorization
- Sensitive data
- Secrets
- Credentials
- Security controls
- External exposure
- Vulnerability
- MCP security
- AI / LLM security
- Agentic security

## Performance Engineer

Route when:

- Performance is the defect
- The fix materially changes performance behaviour
- A performance regression is plausible and significant
- Capacity or resource exhaustion is involved

## DevOps Engineer

Route when the defect affects:

- CI/CD
- Build
- Configuration
- Deployment
- Infrastructure
- Runtime
- Containers
- Secrets integration
- Environment behaviour

## Solution Architect

Route when:

- Architecture may be the root cause
- Fix requires boundary change
- Technology change is proposed
- Cross-system architecture is affected
- An implementation fix cannot safely satisfy the requirement

## Documentation Engineer

Route when:

- Documentation caused or contributed to the defect
- API documentation changes
- Configuration documentation changes
- Deployment procedure changes
- Operational procedure changes
- User-facing documentation changes

Do not report an agent as participating if it was not invoked.

---

# Stage 9 - Root Cause Analysis

## Objective

Determine why the defect occurred.

Analyze applicable:

- Failing component
- Trigger
- Invalid assumption
- Missing validation
- Incorrect state transition
- Contract mismatch
- Data inconsistency
- Concurrency
- Configuration
- Deployment
- Regression
- Security control
- Dependency
- External service
- Performance bottleneck
- Retrieval
- LLM output handling
- Agent routing or delegation

Ask:

- What directly caused the observed behaviour?
- Why was the condition possible?
- Why was it not prevented?
- Why was it not detected earlier?
- Could the same cause affect other paths?

Report:

```text
Root Cause Status:
CONFIRMED / PROBABLE / NOT DETERMINED / NOT APPLICABLE
```

And when available:

- Root cause
- Contributing factors
- Affected components
- Related risk
- Similar exposure elsewhere

Do not invent a root cause merely to complete the workflow.

---

# Stage 10 - Fix Strategy

## Objective

Define the smallest safe change that restores verified expected behaviour.

Evaluate:

- Root cause
- Scope
- Architecture
- Compatibility
- Security
- Data
- Regression
- Deployment
- Performance
- Lifecycle

Prefer:

- Root-cause remediation
- Minimal change
- Existing repository patterns
- Existing technology
- Explicit contracts
- Regression protection

Avoid:

- Broad unrelated refactoring
- Technology migration
- Architecture redesign
- New dependencies

unless justified by the actual defect.

If architecture must change:

```text
→ Solution Architect
```

before implementation proceeds.

---

# Stage 11 - Implementation

Implementation belongs to the responsible engineering agent.

## Backend

Use applicable:

- Backend Engineer
- Python Engineering Skill
- Java Engineering Skill
- Python MCP Engineering Skill

## Frontend

Use:

- Frontend Systems Engineer
- Endesa Corporate Angular Engineering Skill when Angular applies

For Streamlit, respect the approved lifecycle and Python engineering requirements.

## Infrastructure

Use:

`DevOps Engineer`

Do not expand the fix beyond the verified scope without justification.

---

# Stage 12 - Regression Protection

Every material bug fix must evaluate whether regression protection is appropriate.

Where practical:

1. Reproduce the original failure.
2. Add or identify a test that demonstrates the failure.
3. Apply the fix.
4. Execute the relevant test.
5. Verify the test passes.
6. Validate related behaviour.

Possible regression evidence states:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Never report regression protection solely because a test was written.

For defects where automated regression testing is impractical:

- Document why.
- Define alternative validation.
- Record remaining risk.

---

# Stage 13 - Fix Validation

Validate that:

- Required behaviour is restored.
- Root cause is addressed when determinable.
- Original defect is no longer reproducible when execution permits.
- Required contracts remain compatible.
- No material new defect was introduced.
- Data integrity is preserved.
- Security controls remain valid.
- Deployment behaviour remains valid.
- Performance remains acceptable when material.

Validation responsibility depends on affected domains.

---

# QA Validation

When QA applies, QA Engineer evaluates:

- Expected behaviour
- Defect reproduction status
- Fix behaviour
- Critical flows
- Regression
- Negative scenarios
- Contracts
- Security-control behaviour when requested

Do not report:

```text
QA PASS
```

without QA execution evidence.

---

# Code Review Validation

When Code Review applies, Code Reviewer evaluates:

- Correctness
- Maintainability
- Architecture compliance
- Contract implementation
- Error handling
- Test quality
- Regression risk
- Security-sensitive implementation concerns
- Performance-sensitive implementation concerns

Code Review does not replace QA or Security.

---

# Security Validation

When Security applies, Security Engineer evaluates:

- Security root cause
- Security impact
- Exploitability
- Remediation
- Security regression
- Required security evidence
- Residual risk

QA may validate observable security-control behaviour.

Security Engineer owns security finding status.

---

# Performance Validation

When Performance applies, Performance Engineer distinguishes:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

Performance regression must not be claimed without comparative evidence.

For Python/pandas performance, use:

`Python Engineering Skill`

for technology-specific remediation guidance.

---

# Deployment Validation

When DevOps applies, validate applicable:

- Build
- Pipeline
- Configuration
- Deployment
- Database migration
- Runtime
- Recovery
- Rollback
- Environment

Use:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Do not report deployment success without execution evidence.

---

# LLM Bug Validation

Apply only when material LLM functionality is involved.

Use:

`LLM Engineering Skill`

Evaluate applicable:

- Prompt behaviour
- Grounding
- Retrieval
- Structured output
- Citation
- Output validation
- Tool interaction
- Evaluation regression
- Security

Do not classify every LLM variability case as a software defect.

Expected behaviour and evaluation criteria must be verified.

---

# Agentic Bug Validation

Apply only when material agentic behaviour is involved.

Use:

`Agentic Systems Engineering Skill`

Evaluate applicable:

- Routing
- Delegation
- Authority
- Tool selection
- Tool permissions
- Side effects
- State
- Memory
- Stopping conditions
- Human approval
- Loops
- Governance

Agentic-system defects may require Security, QA, DevOps, or other specialist review depending on impact.

---

# Stage 14 - Quality Gate Applicability

Use:

`quality-gates.md`

to determine which gates actually apply.

Possible gates include:

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

Do not define a universal mandatory gate list for all bug fixes.

Gate applicability depends on:

- Scope
- Lifecycle
- Risk
- Technology
- Security impact
- Functional impact
- Deployment impact
- Performance impact
- Documentation impact
- AI / LLM behaviour
- Agentic behaviour

---

# Stage 15 - Quality Gate Evaluation

For each applicable gate use:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Apply:

```text
NOT EXECUTED != PASSED
NOT AVAILABLE != PASSED
```

Do not mark a gate PASSED because its owner was not invoked.

Do not mark a gate PASSED solely because a checklist exists.

---

# Stage 16 - Findings Aggregation

## Owner

Orchestrator

Aggregate only actual evidence.

Include applicable:

- Defect reproduction status
- Expected behaviour
- Root Cause Status
- Impact
- Agents actually participating
- Active skills
- Implementation result
- Test evidence
- Regression evidence
- Specialist findings
- Gate results
- Conditions
- Missing evidence

Do not fabricate missing specialist results.

---

# Stage 17 - Conflict Resolution

Use:

`decision-authority.md`

for authority and conflict resolution.

Do not use a universal hierarchy such as:

```text
Security
> QA
> Performance
> DevOps
```

Instead:

1. Identify the disagreement.
2. Identify the affected domain.
3. Identify the domain authority.
4. Compare evidence.
5. Request clarification when necessary.
6. Escalate unresolved governance questions.

Example:

```text
Backend Recommendation:
APPROVE

QA Gate:
FAILED
```

If QA identifies a critical unresolved functional blocker:

```text
Final Decision:
BLOCK
```

not because QA is globally above Backend, but because the unresolved blocker belongs to QA's domain.

---

# Stage 18 - Final Decision

## Owner

Orchestrator

Use exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## APPROVE

Use when:

- Verified expected behaviour has been restored.
- Applicable mandatory gates pass.
- No unresolved critical blocker remains.
- Required evidence is available.
- Required human approval has been obtained when applicable.

A confirmed root cause is desirable but is not universally required if:

- Behaviour is safely restored.
- Validation is sufficient.
- Remaining uncertainty is explicit.
- Governance permits approval.

## CONDITIONAL APPROVAL

Use when:

- No critical blocker remains.
- Remaining issues are non-critical.
- Conditions are explicit.
- Required follow-up is explicit.
- Mandatory controls are not bypassed.

## BLOCK

Use when:

- A critical defect remains.
- An applicable mandatory gate fails.
- Fix introduces unsafe behaviour.
- Required mandatory control is absent.
- Safe delivery cannot continue.

## NEEDS MORE INFO

Use when:

- Expected behaviour cannot be verified.
- Answer-critical evidence is unavailable.
- Reproduction status is required but unavailable.
- Root cause uncertainty prevents a safe fix.
- Mandatory validation is unavailable.
- Specialist conflict cannot be resolved safely.

---

# Human Approval

Evaluate human approval according to governance and risk.

Particular attention is required for:

- Production emergency changes
- Destructive changes
- Data repair
- Irreversible migrations
- Security exceptions
- Formal risk acceptance
- High-impact permission changes
- Agentic production actions

Do not report human approval as granted without evidence.

---

# Production Incident Handling

A production incident may require accelerated remediation.

Acceleration must not create fabricated evidence.

During an incident:

- Contain impact when possible.
- Preserve evidence.
- Distinguish mitigation from permanent fix.
- Record temporary workarounds.
- Identify follow-up remediation.
- Validate recovery.
- Apply human governance when required.

A workaround that restores service is not automatically the confirmed root-cause fix.

---

# Data Repair

When the defect corrupted or incorrectly modified data, distinguish:

```text
Application Fix
Data Repair
```

They are separate concerns.

Evaluate:

- Affected records
- Source of truth
- Repair method
- Backup
- Validation
- Idempotency
- Auditability
- Security
- Human approval
- Rollback or compensation

Do not modify production data without applicable authorization.

---

# Temporary Workaround

When permanent remediation cannot be completed immediately, document:

- Workaround
- Scope
- Limitation
- Risk
- Expiration or follow-up requirement when known
- Required permanent fix
- Validation

Do not represent a temporary workaround as root-cause resolution.

---

# Required Output

A material bug-fix workflow should report applicable sections.

## Bug Summary

- Reported defect
- Affected system
- Lifecycle
- Environment

## Expected Behaviour

Report:

- Expected behaviour
- Evidence source
- Verification status

## Reproduction

Use exactly one:

```text
REPRODUCED
OBSERVED
INFERRED
NOT REPRODUCED
NOT EXECUTED
NOT AVAILABLE
```

Include supporting evidence.

## Impact Assessment

Report:

- Business impact
- User impact
- Data impact
- Security impact
- Operational impact

## Root Cause

Use:

```text
CONFIRMED
PROBABLE
NOT DETERMINED
NOT APPLICABLE
```

Describe supporting evidence.

## Participating Agents

List only agents actually participating.

## Active Skills

List only applicable skills.

## Fix Strategy

Describe:

- Proposed or implemented remediation
- Scope
- Compatibility implications
- Known trade-offs

## Implementation Result

Report actual implementation status.

## Regression Evidence

Use applicable:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## Validation Evidence

Report verified:

- Tests
- Contracts
- Security
- Performance
- Deployment
- LLM / Agentic evaluation

as applicable.

## Quality Gates

List only applicable gates and actual states.

## Conditions

List outstanding non-blocking actions.

## Missing Evidence

List answer-critical unavailable evidence.

## Residual Risk

When applicable use:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

Residual risk does not constitute formal risk acceptance.

## Final Decision

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## Decision Rationale

Explain how evidence and applicable gates support the outcome.

---

# Traceability

Record only trace information actually available from the execution environment.

Possible fields include:

- Execution identifier
- Change identifier
- Incident identifier
- Lifecycle
- Environment
- Participating agents
- Active skills
- Tools executed
- Gate results
- Human approval
- Timestamp

Do not fabricate unavailable identifiers or timestamps.

Do not report an agent as participating if it was not invoked.

---

# Workflow Anti-Patterns

Avoid:

## Fixing Without Understanding Expected Behaviour

Changing code before establishing what correct behaviour should be.

## False Reproduction

Reporting a bug as reproduced without execution evidence.

## Forced Root Cause

Inventing a root cause because the workflow expects one.

## Symptom-Only Fix

Hiding the visible error while leaving the material cause unchanged without clearly documenting the workaround.

## Broad Refactor During Bug Fix

Expanding a localized fix into unrelated technical restructuring.

## Universal Agent Routing

Invoking all specialists for every defect.

## Universal Gates

Running every Quality Gate regardless of scope.

## False Regression Protection

Claiming regression protection because a test was written but not executed.

## False PASS

Converting NOT EXECUTED or NOT AVAILABLE into PASS.

## Architecture Drift

Changing technology or system boundaries without Solution Architect approval.

## Security Bypass

Disabling a control to make the defect disappear.

## Production Evidence Fabrication

Inventing logs, deployment results, trace IDs, incident IDs, or approvals.

## Workaround as Resolution

Representing temporary mitigation as permanent remediation.

---

# Definition of Done

A bug-fix workflow is complete when:

- The reported defect is understood.
- Lifecycle has been considered.
- Scope has been identified.
- Technology context has been identified.
- Expected behaviour has been verified or missing information is explicit.
- Reproduction status is explicit.
- Reproduction is not claimed without evidence.
- Impact has been evaluated.
- Required specialists have been selected.
- Unnecessary agents have not been invoked.
- Applicable engineering skills have been identified.
- Root Cause Status is explicit.
- Probable root causes are not represented as confirmed.
- Fix scope is explicit.
- Approved architecture has been preserved.
- Implementation belongs to the correct specialist.
- Regression protection has been evaluated.
- Test existence has been distinguished from test execution.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Functional validation has been performed when applicable.
- Security validation has been performed when applicable.
- Performance validation has been performed when applicable.
- Deployment validation has been performed when applicable.
- LLM evaluation has been performed when applicable.
- Agentic evaluation has been performed when applicable.
- Applicable Quality Gates have been identified using `quality-gates.md`.
- Irrelevant gates have not been represented as PASSED.
- Findings have been aggregated from actual evidence.
- Conflicts have been handled according to `decision-authority.md`.
- Human approval has been evaluated when required.
- Temporary workarounds have been distinguished from permanent fixes.
- Data repair has been separated from application remediation when applicable.
- Blocking findings are explicit.
- Conditions are explicit.
- Missing evidence is explicit.
- Trace information has not been fabricated.
- Final decision is traceable to evidence.

---

# Goal

Restore verified expected behaviour through the smallest safe and maintainable change, supported by explicit reproduction and root-cause evidence where available, protected by appropriate regression validation, and approved only through the Quality Gates that materially apply to the defect's lifecycle, scope, technology, and risk.