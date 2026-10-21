# Feature Workflow

Version: 2.0

---

# Purpose

This workflow defines the evidence-based process for understanding, designing, implementing, validating, and governing new software features.

The objective is to deliver the required business capability while:

- Satisfying verified requirements
- Preserving approved architecture
- Selecting technology from evidence rather than preference
- Applying lifecycle-appropriate engineering
- Protecting security and data
- Maintaining compatibility
- Controlling regression risk
- Supporting safe deployment
- Producing traceable validation evidence

This workflow may apply to:

- Backend features
- Frontend features
- Full-stack features
- API capabilities
- Data-processing features
- Database changes
- External integrations
- Infrastructure-related capabilities
- Streamlit prototypes
- Angular applications
- Python services
- Java services
- MCP capabilities
- LLM-powered functionality
- Agentic systems

Not every feature requires every agent, skill, or Quality Gate.

Routing and validation must reflect:

- Business objective
- Scope
- Lifecycle
- Existing architecture
- Technology
- Risk
- Deployment impact
- Available evidence

---

# Workflow Principles

Always apply:

- Requirements before implementation
- Evidence before assumptions
- Repository before technology preference
- Architecture before implementation when architecture decisions are required
- Minimum necessary complexity
- Minimum necessary agent routing
- Lifecycle-aware engineering
- Risk-based validation
- Explicit contracts
- Security by Design
- Regression prevention
- Traceable decisions
- Explicit uncertainty

Mandatory rules:

```text
Requested feature != Verified requirement
Proposed architecture != Approved architecture
Skill availability != Technology selection
Test defined != Test executed
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
Agent defined != Agent participated
Prototype success != Production readiness
```

---

# Evidence Classification

Classify material feature information when useful as:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

Do not represent:

```text
INFERRED
NOT VERIFIED
```

as:

```text
VERIFIED
```

---

# Lifecycle Context

Determine the intended lifecycle when relevant:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Lifecycle influences:

- Architecture depth
- Technology selection
- Testing
- Security validation
- Deployment
- Performance
- Documentation
- Operational readiness

## Experiment

Prioritize:

- Technical feasibility
- Learning
- Minimal justified architecture
- Safe execution
- Critical correctness

Do not impose unnecessary production complexity.

## Prototype / PoC

Prioritize:

- Business validation
- User-flow validation
- Data-processing validation
- Integration feasibility
- Rapid feedback
- Explicit limitations

Prototype technology may differ from the production target.

## MVP

Prioritize:

- Usable business value
- Maintainability
- Core security
- Testability
- Deployment
- Expected evolution
- Regression protection

## Production

Prioritize:

- Security
- Reliability
- Maintainability
- Testability
- Operational readiness
- Deployment safety
- Performance
- Accessibility when applicable
- Traceability
- Appropriate documentation

Prototype shortcuts must not silently become production architecture.

---

# Workflow Overview

```text
Feature Request
      ↓
Requirements and Expected Outcome
      ↓
Lifecycle and Scope
      ↓
Repository and Existing Architecture
      ↓
Impact Assessment
      ↓
Architecture Decision if required
      ↓
Minimum Agent and Skill Routing
      ↓
Implementation Plan
      ↓
Implementation
      ↓
Validation
      ↓
Applicable Quality Gates
      ↓
Findings Aggregation
      ↓
Conflict Resolution
      ↓
Orchestrator Final Decision
```

Stages may iterate when new evidence changes requirements or reveals an architectural issue.

Do not allow uncontrolled iteration.

---

# Stage 1 - Feature Intake

## Owner

Orchestrator

## Objective

Understand the requested business capability before decomposing implementation.

Collect available:

- Feature title
- Business objective
- User need
- Functional requirements
- Acceptance criteria
- Expected behaviour
- Affected application
- Constraints
- Desired lifecycle
- Delivery context

When available also collect:

- Existing workflow
- UI designs
- Technical requirements
- Architecture proposal
- Data requirements
- Integration requirements
- Security requirements
- Performance requirements
- Deployment constraints
- Corporate requirements

Do not invent missing requirements.

---

# Stage 2 - Requirements Validation

Separate:

```text
Verified requirements
Assumptions
Constraints
Missing information
```

Validate when applicable:

- Business objective
- User outcome
- Acceptance criteria
- Data requirements
- Integration requirements
- Security requirements
- Performance requirements
- Accessibility requirements
- Operational requirements

If answer-critical requirements remain unavailable:

```text
NEEDS MORE INFO
```

may be required before architecture or implementation proceeds.

Do not translate a vague feature request directly into implementation assumptions.

---

# Stage 3 - Lifecycle Classification

## Owner

Orchestrator

with Solution Architect involvement when lifecycle materially affects architecture.

Classify:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Record supporting evidence.

When lifecycle cannot be determined and materially affects:

- Technology
- Architecture
- Security
- Testing
- Deployment
- Documentation

use:

```text
NEEDS MORE INFO
```

when necessary.

---

# Stage 4 - Repository Discovery

Before proposing implementation, inspect existing repository evidence.

Identify applicable:

- Existing language
- Frontend technology
- Backend technology
- Frameworks
- Runtime versions
- Project structure
- Existing APIs
- Data model
- Databases
- External integrations
- Authentication
- Authorization
- Testing
- CI/CD
- Deployment
- Containers
- Infrastructure
- Documentation
- Existing corporate capabilities

Repository evidence has priority over generic technology preference.

Existing technology should normally be preserved unless an approved architecture decision justifies change.

---

# Stage 5 - Scope and Impact Assessment

Determine affected areas.

Possible impact areas include:

```text
Architecture
Backend
Frontend
API
Database
Data processing
External integration
Security
Infrastructure
Deployment
Performance
Documentation
MCP
LLM
Agentic behaviour
```

Assess:

- Business impact
- User impact
- Data impact
- Security impact
- Compatibility impact
- Deployment impact
- Performance impact
- Operational impact
- Migration impact

Use a risk classification where helpful:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

Risk must be based on the actual feature context.

Do not inflate risk to force additional process.

---

# Stage 6 - Architecture Applicability

Determine whether the feature requires an architectural decision.

Solution Architect should participate when the feature involves material:

- Technology selection
- New application
- New service
- New subsystem
- New frontend
- New backend
- New database
- New integration pattern
- System-boundary change
- Data-ownership change
- Deployment architecture
- Technology migration
- Prototype-to-production decision
- MCP adoption
- Material LLM architecture
- Material agentic architecture

Do not invoke Solution Architect merely because implementation work exists.

For an existing feature fitting established architecture, implementation may proceed using existing approved boundaries.

---

# Stage 7 - Architecture Decision

Apply only when architecture decisions are required.

## Owner

Solution Architect

Evaluate:

- Requirements
- Lifecycle
- Existing architecture
- Existing technology
- Security
- Integrations
- Data
- Deployment
- Maintainability
- Performance
- Migration cost

Technology selection must not be driven by skill availability.

Examples:

```text
Python skill available
!=
Python must be selected
```

```text
Angular skill available
!=
Angular must be selected
```

When material architecture is selected, identify required engineering specialists and skills.

Use ADR when required by the project process.

---

# Stage 8 - Technology and Skill Mapping

Apply skills according to repository evidence and approved architecture.

## Python

Use:

`Python Engineering Skill`

when:

- Existing backend is Python
- Approved architecture selects Python
- Python data processing is required

## Java

Use:

`Java Engineering Skill`

when:

- Existing backend is Java
- Approved architecture selects Java

## Python MCP

Use:

```text
Python Engineering Skill
+
Python MCP Engineering Skill
```

when Python MCP functionality is materially required.

MCP must not be introduced merely because the feature uses AI.

## Angular

Use:

`Endesa Corporate Angular Engineering Skill`

when Angular is established or explicitly selected.

Corporate-specific rules require supporting evidence.

## Streamlit

Use Streamlit only when:

- Existing architecture uses Streamlit
- Solution Architect selects it
- Lifecycle and requirements justify it

Streamlit must not be selected solely because the backend uses Python.

## LLM

Use:

`LLM Engineering Skill`

when material LLM functionality exists.

## Agentic Systems

Use:

`Agentic Systems Engineering Skill`

when material agentic behaviour exists.

For an agentic LLM feature apply:

```text
LLM Engineering Skill
+
Agentic Systems Engineering Skill
```

Do not activate irrelevant skills.

---

# Stage 9 - Minimum Agent Routing

## Owner

Orchestrator

Select only agents required for the feature.

Do not use a universal route.

## Backend Engineer

Route when material work affects:

- Python
- Java
- APIs
- Business logic
- Persistence
- Backend integration
- Data processing
- Python MCP implementation

## Frontend Systems Engineer

Route when material work affects:

- Angular
- Streamlit UI
- Existing frontend framework
- UI components
- Forms
- State
- Routing
- Frontend API integration

A feature may require both Backend and Frontend Engineers.

## Security Engineer

Route when material work affects:

- Authentication
- Authorization
- Sensitive data
- Personal data
- Secrets
- Credentials
- External exposure
- Security boundaries
- API security
- MCP security
- LLM security
- Agentic-system security
- Verified corporate security controls

Do not route Security merely because the feature uses application code.

## QA Engineer

Route when the feature requires material:

- Acceptance validation
- Functional testing
- Contract testing
- Regression validation
- E2E validation
- Negative testing
- Security-control functional validation

QA depth must reflect lifecycle and risk.

## Code Reviewer

Route when implementation-quality review is materially required.

Examples:

- Production code
- Complex implementation
- Material refactor
- Sensitive contracts
- Security-sensitive implementation
- High regression risk

Do not make Code Reviewer mandatory for every disposable experiment.

## DevOps Engineer

Route when material work affects:

- CI/CD
- Build
- Artifact
- Configuration
- Infrastructure
- Runtime
- Deployment
- Containers
- Environment
- Secrets integration
- Database deployment
- Operational readiness

## Performance Engineer

Route when:

- Verified performance requirements exist
- Significant data volume exists
- Critical latency exists
- Material resource consumption exists
- Scalability is a requirement
- Feature creates material capacity risk

Do not route Performance solely because optimization is theoretically possible.

## Documentation Engineer

Route when required documentation materially changes.

Examples:

- Architecture
- API
- Developer setup
- Configuration
- Deployment
- Operations
- User behaviour
- Security
- Prototype-to-production guidance

Do not invoke Documentation solely to produce unnecessary documents.

---

# Stage 10 - Workstream Decomposition

Decompose only the work required by the feature.

Possible workstreams include:

## Architecture

- System boundaries
- Technology
- Data ownership
- Integration pattern
- Deployment architecture

## Backend

- API
- Business logic
- Data processing
- Persistence
- Integrations

## Frontend

- UI
- State
- Forms
- Routing
- API integration
- Accessibility

## Data

- Schema
- Migration
- Transformation
- Validation

## Security

- Authentication
- Authorization
- Secrets
- Data protection
- Threats

## DevOps

- Build
- CI/CD
- Configuration
- Infrastructure
- Deployment

## Performance

- Benchmark
- Profiling
- Scalability
- Capacity

## LLM

- Grounding
- Retrieval
- Prompt
- Structured output
- Evaluation

## Agentic

- Authority
- Routing
- Tools
- Delegation
- State
- Human approval

Do not create workstreams that do not contribute to the feature.

---

# Stage 11 - Implementation Plan

Before implementation, identify:

- Components to change
- Responsible engineer
- Active skill
- Contracts
- Data changes
- Tests required
- Security considerations
- Deployment impact
- Documentation impact
- Validation required

The plan should remain proportional to feature complexity.

Do not require extensive formal planning for trivial low-risk changes.

---

# Stage 12 - Backend Implementation

Apply only when backend work exists.

## Owner

Backend Engineer

Implement according to:

- Approved architecture
- Repository conventions
- Active engineering skill
- Explicit contracts
- Security requirements
- Test requirements

Preserve existing technology unless architecture explicitly approves change.

Backend Engineer must not independently redefine architecture.

---

# Stage 13 - Frontend Implementation

Apply only when frontend work exists.

## Owner

Frontend Systems Engineer

Implement according to:

- Approved architecture
- Lifecycle
- Repository conventions
- Active frontend skill
- API contracts
- UX requirements
- Accessibility
- Security boundaries
- Test requirements

For Angular apply:

`Endesa Corporate Angular Engineering Skill`

For Streamlit respect prototype versus production boundaries.

Frontend controls are not authoritative authorization controls.

---

# Stage 14 - MCP Implementation

Apply only when MCP functionality exists.

For Python MCP use:

```text
Backend Engineer
+
Python Engineering Skill
+
Python MCP Engineering Skill
```

Define applicable:

- Tools
- Resources
- Prompts
- Input contracts
- Output contracts
- Authentication
- Authorization
- Side effects
- Error behaviour
- Deployment

Security Engineer evaluates MCP security when material.

QA validates MCP behaviour when required.

---

# Stage 15 - LLM Implementation

Apply only when material LLM functionality exists.

Use:

`LLM Engineering Skill`

Define applicable:

- LLM role
- Model requirements
- Trusted instructions
- Context
- Grounding
- Retrieval
- Structured outputs
- Output validation
- Security
- Evaluation
- Observability
- Performance
- Cost

Do not assume RAG is mandatory.

Do not treat model output as authoritative without appropriate validation.

---

# Stage 16 - Agentic Implementation

Apply only when material agentic behaviour exists.

Use:

`Agentic Systems Engineering Skill`

Define applicable:

- Agent responsibilities
- Authority
- Routing
- Delegation
- Tools
- Permissions
- Side effects
- State
- Memory
- Human approval
- Stopping conditions
- Traceability
- Evaluation

Do not maximize autonomy without justification.

---

# Stage 17 - Test Strategy

Determine the smallest appropriate combination of tests.

Possible test levels:

- Unit
- Integration
- Contract
- E2E
- Regression
- Negative
- Data validation
- Security-control functional validation
- LLM evaluation
- Agentic workflow evaluation

Not every feature requires every test level.

Testing depth depends on:

- Lifecycle
- Business criticality
- Risk
- Contracts
- Data integrity
- Security
- Regression impact

---

# Stage 18 - Test Execution Evidence

For relevant tests distinguish:

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
Test defined != Test executed
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
```

Build success does not equal QA PASS.

SonarQube PASS does not equal QA PASS.

---

# Stage 19 - Contract Validation

Validate material contracts.

Possible contracts include:

- Frontend/backend API
- Service-to-service API
- External integration
- Database expectations
- Event/message contract
- MCP tool contract
- MCP resource contract
- LLM structured-output schema

Evaluate:

- Request
- Response
- Required fields
- Optional fields
- Types
- Errors
- Compatibility
- Consumer impact

A broken mandatory contract is a material finding.

---

# Stage 20 - Security Validation

Apply when Security Gate is applicable.

## Owner

Security Engineer

Use:

- Verified corporate requirements
- Project-specific requirements
- Secure Coding
- Threat analysis
- SonarQube
- Dependency analysis
- Dynamic testing
- Ethical Hacking / Assurance when applicable
- Manual security analysis

Do not invent corporate controls.

Do not treat SonarQube PASS as complete security approval.

Do not create formal risk acceptance.

---

# Stage 21 - QA Validation

Apply when QA Gate is applicable.

## Owner

QA Engineer

Validate applicable:

- Acceptance criteria
- Critical flows
- Functional behaviour
- Negative scenarios
- Contracts
- Regression risk
- Data behaviour
- Security-control behaviour when requested

QA must distinguish test definitions from actual execution.

---

# Stage 22 - Code Review

Apply when Code Review Gate is applicable.

## Owner

Code Reviewer

Review:

- Correctness
- Maintainability
- Architecture compliance
- Contracts
- Error handling
- Dependency changes
- Security-sensitive implementation
- Performance-sensitive implementation
- Test quality
- Regression risk

Code Review does not replace QA, Security, or SonarQube.

---

# Stage 23 - Performance Validation

Apply when Performance Gate is applicable.

## Owner

Performance Engineer

Classify findings as:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

Evaluate applicable:

- Critical paths
- Latency
- Throughput
- Resource consumption
- Database
- Data processing
- Frontend
- Infrastructure
- LLM
- Agentic behaviour

Do not report improvement without execution evidence.

For Python/pandas implementation guidance use:

`Python Engineering Skill`

---

# Stage 24 - Deployment Validation

Apply when DevOps Gate is applicable.

## Owner

DevOps Engineer

Evaluate applicable:

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

Use execution evidence:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Do not report successful deployment without execution evidence.

---

# Stage 25 - Documentation

Apply when Documentation Gate is applicable.

## Owner

Documentation Engineer

Update applicable:

- Architecture
- ADR
- API
- Data
- Developer guide
- Configuration
- Deployment
- Runbook
- Security
- Performance
- LLM
- Agentic
- Prototype-to-production

Documentation must reflect verified implementation.

Do not document proposed functionality as already implemented.

---

# Stage 26 - Prototype-to-Production Review

Apply when:

- Feature uses prototype technology
- Production target differs
- Prototype may evolve into MVP or Production

Identify:

- Prototype stack
- Production target when approved
- Reusable business logic
- Reusable APIs
- Disposable UI
- Authentication changes
- Authorization changes
- Data changes
- Deployment impact
- Accessibility gaps
- Security gaps
- Testing gaps
- Migration risk

Do not silently promote prototype architecture to production.

---

# Stage 27 - Quality Gate Applicability

Use:

`quality-gates.md`

Determine applicability for:

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

Do not define universal mandatory gates for all features.

Gate selection depends on actual scope and risk.

---

# Stage 28 - Quality Gate Evaluation

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

A gate must not be PASSED merely because its specialist was not invoked.

---

# Stage 29 - Findings Aggregation

## Owner

Orchestrator

Aggregate actual evidence only.

Include applicable:

- Requirements
- Lifecycle
- Architecture decisions
- Participating agents
- Active skills
- Implementation results
- Test evidence
- Contract results
- Security findings
- QA findings
- Code Review findings
- Performance findings
- DevOps findings
- Documentation findings
- LLM findings
- Agentic findings
- Gate results
- Conditions
- Missing evidence

Do not fabricate findings for agents that did not participate.

---

# Stage 30 - Conflict Resolution

Use:

`decision-authority.md`

for authority and conflict resolution.

Do not use a universal specialist hierarchy.

Resolve conflicts by:

1. Identifying the exact disagreement.
2. Identifying the affected domain.
3. Identifying domain authority.
4. Comparing evidence.
5. Requesting clarification where necessary.
6. Preserving unresolved disagreement.
7. Escalating when required.

Example:

```text
Backend Recommendation:
APPROVE

Security Gate:
FAILED
```

If an unresolved critical security blocker exists:

```text
Final Decision:
BLOCK
```

because the blocker belongs to the Security domain, not because Security is globally above Backend.

---

# Stage 31 - Human Approval

Evaluate human approval according to:

- Environment
- Impact
- Reversibility
- Security
- Governance
- Business criticality

Human approval should be explicitly evaluated for applicable:

- Production changes
- Destructive actions
- Irreversible migration
- Data deletion
- Permission changes
- Credential changes
- Public exposure
- Formal risk acceptance
- High-impact financial action
- Critical uncertainty
- Agentic production actions

Do not fabricate approval.

---

# Stage 32 - Final Decision

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

- Verified requirements are satisfied.
- Applicable mandatory gates pass.
- No unresolved critical blocker remains.
- Required evidence is available.
- Required human approval exists when applicable.

## CONDITIONAL APPROVAL

Use when:

- No critical blocker remains.
- Applicable gates support conditional progression.
- Remaining actions are explicit.
- Responsible areas are explicit.
- Required validation is explicit.
- Mandatory controls are not bypassed.

## BLOCK

Use when:

- Applicable mandatory gate fails.
- Critical blocker remains.
- Feature cannot safely satisfy verified requirements.
- Required mandatory control is absent.
- Safe implementation or delivery cannot proceed.

## NEEDS MORE INFO

Use when:

- Requirements are answer-critical but unavailable.
- Lifecycle cannot be determined when necessary.
- Architecture decision is unresolved.
- Required evidence is unavailable.
- Gate applicability cannot be determined.
- Specialist conflict cannot be resolved safely.
- Required human approval status is unavailable.

---

# Conditional Approval Requirements

For each condition report:

```text
Condition:
Responsible area:
Required action:
Evidence required:
Validation:
```

Do not use vague conditions.

Do not use conditional approval as a substitute for formal risk acceptance.

---

# Required Output

A material feature workflow should report applicable sections.

## Feature Summary

- Objective
- Users
- Scope
- Lifecycle

## Requirements

Separate:

- Verified requirements
- Assumptions
- Constraints
- Missing information

## Repository Context

Describe existing architecture and technology.

## Architecture

Report:

- Existing architecture
- New decisions
- ADR requirement
- Migration impact

## Technology

Report:

- Backend
- Frontend
- Database
- Integrations
- MCP
- LLM
- Agentic capabilities

## Participating Agents

List only agents actually participating.

## Active Skills

List only applicable skills.

## Implementation Plan

Describe workstreams and ownership.

## Implementation Result

Describe actual completed implementation.

Do not present planned work as completed work.

## Tests

For each relevant test category report:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## Contracts

Report relevant interface compatibility.

## Security

Report applicable Security Gate evidence.

## QA

Report applicable QA Gate evidence.

## Code Review

Report applicable Code Review Gate evidence.

## Performance

Report applicable Performance Gate evidence.

## DevOps

Report applicable DevOps Gate evidence.

## Documentation

Report applicable Documentation Gate evidence.

## LLM

Report applicable LLM Gate evidence.

## Agentic

Report applicable Agentic Gate evidence.

## Quality Gates

List only gates relevant to the actual workflow and their real state.

## Conditions

List non-blocking conditions.

## Missing Evidence

List unavailable evidence.

## Residual Risk

When applicable use:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

Residual risk reporting does not constitute formal risk acceptance.

## Human Approval

When relevant report:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Do not report approval as granted without evidence.

## Final Decision

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

## Decision Rationale

Explain how verified requirements, evidence, applicable gates, blockers, and conditions support the result.

---

# Traceability

Record only trace information actually provided by the execution environment.

Possible information includes:

- Execution identifier
- Feature identifier
- Lifecycle
- Environment
- Participating agents
- Active skills
- Delegations
- Tools executed
- Gate results
- Human approval
- Timestamp

Do not fabricate:

- Execution IDs
- Feature IDs
- Timestamps
- Agent participation
- Tool execution
- Human approval

---

# Workflow Anti-Patterns

Avoid:

## Universal Agent Routing

Invoking Backend, Frontend, QA, Code Review, Security, Performance, DevOps, and Documentation for every feature.

## Universal Quality Gates

Applying every gate to every feature.

## Architecture After Implementation

Implementing a material architectural decision before architecture is approved.

## Skill-Driven Technology Selection

Choosing technology because an engineering skill exists.

## Prototype-to-Production Drift

Allowing Streamlit or another prototype technology to become production architecture without review.

## Security as Final Review Only

Waiting until implementation is complete before considering security-sensitive design.

## Test Existence as PASS

Treating source test files as successful execution evidence.

## Build Success as QA PASS

Assuming compilation or pipeline success proves functional correctness.

## SonarQube as Universal Approval

Treating SonarQube PASS as complete QA, Security, Code Review, or production approval.

## LLM Everywhere

Using LLM functionality when deterministic software is sufficient.

## Agent Everywhere

Creating agentic behaviour when a deterministic workflow is sufficient.

## False Participation

Reporting specialists as participating when they were not invoked.

## False Execution

Reporting tools, tests, pipelines, or deployments as executed without evidence.

## Conditional Approval as Governance Bypass

Using conditions to avoid mandatory controls.

## Planned Work as Completed Work

Describing a design or recommendation as implemented functionality.

---

# Definition of Done

A feature workflow is complete when:

- The business objective is understood.
- Verified requirements are identified.
- Assumptions are explicit.
- Missing requirements are explicit.
- Lifecycle has been considered.
- Existing repository architecture has been inspected.
- Existing technology has been identified.
- Scope and impact have been evaluated.
- Architectural decisions have been made before implementation when required.
- Technology has not been selected merely because a skill exists.
- Required agents have been selected.
- Unnecessary agents have not been invoked.
- Applicable engineering skills have been identified.
- Backend implementation follows approved architecture when applicable.
- Frontend implementation follows approved architecture when applicable.
- Streamlit has not been selected automatically because Python is used.
- Corporate Angular capabilities have not been invented.
- MCP has only been introduced when justified.
- LLM functionality has only been introduced when justified.
- Agentic behaviour has only been introduced when justified.
- Test strategy reflects lifecycle and risk.
- Test definitions have been distinguished from test execution.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Required contracts have been validated.
- Security has been evaluated when applicable.
- Functional quality has been evaluated when applicable.
- Code Review has been performed when applicable.
- Performance has been evaluated when applicable.
- Deployment has been evaluated when applicable.
- Documentation has been evaluated when applicable.
- LLM evaluation has been performed when applicable.
- Agentic evaluation has been performed when applicable.
- Prototype-to-production implications are explicit when relevant.
- Applicable Quality Gates have been selected using `quality-gates.md`.
- Irrelevant gates have not been represented as PASSED.
- Conflicts have been handled according to `decision-authority.md`.
- Required human approval has been evaluated.
- Blocking findings are explicit.
- Conditions are explicit.
- Missing evidence is explicit.
- Trace information has not been fabricated.
- Planned work has not been represented as completed implementation.
- Final decision is traceable to verified evidence.

---

# Goal

Deliver each feature through the simplest justified architecture and implementation for its lifecycle, using only the agents, skills, tests, and Quality Gates that materially apply, while ensuring verified requirements, security, correctness, maintainability, deployment safety, and traceability are preserved without turning engineering governance into unnecessary process.