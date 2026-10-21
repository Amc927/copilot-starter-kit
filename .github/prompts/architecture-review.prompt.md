---
name: Architecture Review Prompt
description: Evidence-based architecture review framework for evaluating software systems, applications, services, integrations, prototypes, production platforms, MCP capabilities, LLM systems, and agentic systems according to lifecycle, requirements, repository evidence, and governance.
model: Auto (copilot)
---

# Architecture Review Prompt

Version: 2.0

---

# Objective

Perform an evidence-based architectural assessment of the proposed or existing system, change, design, implementation, or platform.

Evaluate whether the architecture:

- Satisfies verified requirements
- Fits the intended lifecycle
- Respects existing architecture where applicable
- Uses justified technology
- Defines clear system boundaries
- Defines clear data ownership
- Supports required integrations
- Supports required security boundaries
- Supports required deployment characteristics
- Remains maintainable
- Remains operable
- Can satisfy verified performance requirements
- Avoids unnecessary architectural complexity
- Supports future evolution where required

Focus on system design and architectural decisions.

Do not replace implementation review, QA, Security, Performance, or DevOps specialist authority.

---

# Architecture Authority

Architecture decisions belong to:

`Solution Architect`

The architecture review may identify implications requiring specialist validation from:

- Backend Engineer
- Frontend Systems Engineer
- Security Engineer
- QA Engineer
- Code Reviewer
- DevOps Engineer
- Performance Engineer
- Documentation Engineer

The Orchestrator owns the final engineering decision.

Formal risk acceptance belongs to the applicable authorized governance process.

---

# Governance References

Use:

`quality-gates.md`

for Architecture Gate applicability, status, evidence, and gate aggregation.

Use:

`decision-authority.md`

for authority, conflicts, escalation, and final decision governance.

Do not create a separate authority hierarchy inside this prompt.

---

# Evidence-First Rule

Base architectural conclusions on available evidence.

Possible evidence includes:

- Verified business requirements
- Acceptance criteria
- Repository code
- Repository structure
- Existing architecture documentation
- HLD
- Detailed design
- ADRs
- API contracts
- Data models
- Existing integrations
- Runtime configuration
- CI/CD
- Deployment configuration
- Infrastructure as Code
- Security requirements
- Risk Assessment
- Security Annex
- Performance requirements
- Existing production evidence
- Approved corporate documentation

Do not invent:

- Requirements
- Technologies
- Corporate standards
- Corporate libraries
- Corporate components
- APIs
- Integrations
- Databases
- Security controls
- Deployment platforms
- Performance targets
- Operational requirements
- System ownership

---

# Evidence Classification

Use when appropriate:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

Never represent:

```text
INFERRED
NOT VERIFIED
```

as:

```text
VERIFIED
```

When answer-critical architectural evidence is unavailable, use:

`NEEDS MORE INFO`

when necessary.

---

# Current vs Proposed vs Approved Architecture

Always distinguish:

```text
CURRENT
PROPOSED
APPROVED
NOT DETERMINED
```

## CURRENT

Architecture demonstrated by current evidence.

## PROPOSED

Architecture suggested for consideration but not yet approved.

## APPROVED

Architecture supported by an authorized architectural decision.

## NOT DETERMINED

Available evidence is insufficient to classify architectural status.

Do not describe a proposed architecture as approved architecture.

Do not describe existing implementation automatically as approved architecture.

---

# Lifecycle Context

Identify the intended lifecycle:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Architectural depth must reflect lifecycle.

## Experiment

Prioritize:

- Technical feasibility
- Minimal architecture
- Safe execution
- Clear assumptions
- Fast learning

Avoid unnecessary production complexity.

## Prototype / PoC

Prioritize:

- Business or technical validation
- Clear system boundaries
- Data-flow feasibility
- Integration feasibility
- Reusable business logic
- Explicit prototype limitations
- Production migration awareness

Prototype technology does not automatically define production technology.

## MVP

Prioritize:

- Maintainability
- Core security
- Stable contracts
- Testability
- Deployment
- Expected evolution
- Reasonable operational characteristics

## Production

Evaluate architecture for:

- Security
- Maintainability
- Reliability
- Operability
- Deployment
- Data integrity
- Performance
- Scalability when required
- Recovery
- Supportability
- Appropriate observability
- Future evolution

Do not apply production architecture automatically to disposable experiments.

Do not allow prototype shortcuts to become production architecture without validation.

---

# Business Context

Identify verified:

- Business objective
- User need
- Critical business flows
- Success criteria
- Constraints
- Availability requirements
- Security requirements
- Performance requirements
- Operational expectations

Questions:

- Why does the system or change exist?
- Which problem must it solve?
- Which behaviour is critical?
- Which constraints are mandatory?
- What happens if the system is unavailable?
- What lifecycle is intended?

Do not design architecture around requirements that have not been verified.

---

# Repository-First Review

Before proposing architecture, inspect available repository evidence.

Identify:

- Existing languages
- Existing frontend technology
- Existing backend technology
- Frameworks
- Runtime versions
- Existing project structure
- Existing service boundaries
- Existing APIs
- Existing data stores
- Existing external integrations
- Authentication
- Authorization
- Existing deployment model
- Existing infrastructure
- Existing tests
- Existing CI/CD
- Existing documentation
- Existing technical debt

Prefer evolution of established architecture over unnecessary replacement.

Existing implementation is evidence, not proof that the architecture is optimal.

---

# Architecture Applicability

Determine whether a material architecture decision is actually required.

Architecture review is typically required for:

- New application
- New service
- New subsystem
- New frontend
- New backend
- New datastore
- New integration pattern
- Technology change
- Technology migration
- System-boundary change
- Data-ownership change
- Deployment-architecture change
- Prototype-to-production transition
- MCP adoption
- Material LLM architecture
- Material agentic architecture

A localized implementation change fitting established architecture may not require a new architectural decision.

Avoid architecture changes for problems that can safely be solved within existing approved boundaries.

---

# Architecture Principles

Evaluate principles according to actual requirements.

Consider:

- Separation of Concerns
- High Cohesion
- Appropriate Coupling
- Clear Ownership
- Explicit Contracts
- Security by Design
- Data Integrity
- Maintainability
- Testability
- Operability
- Simplicity
- Evolutionary Architecture

Do not impose universally:

- API First
- Microservices
- Event-driven architecture
- Horizontal scaling
- Asynchronous processing
- Caching
- High availability
- Distributed tracing
- Serverless
- Containers

Each pattern requires justification from requirements and context.

---

# Technology Decision

Technology selection must be evidence-based.

Evaluate:

- Existing repository technology
- Approved corporate/platform capability
- Team supportability when verified
- Lifecycle
- Functional requirements
- Security
- Data
- Integration
- Deployment
- Maintainability
- Performance
- Migration cost
- Operational complexity

Skill availability must not determine technology.

Examples:

```text
Python Engineering Skill exists
!=
Python must be selected
```

```text
Java Engineering Skill exists
!=
Java must be selected
```

```text
Angular Engineering Skill exists
!=
Angular must be selected
```

Do not introduce a technology migration without explicit architectural justification.

---

# Python Architecture

When Python is current or proposed technology, evaluate:

- Lifecycle suitability
- Repository consistency
- Application boundaries
- Data-processing role
- API role when applicable
- Deployment implications
- Performance requirements
- Maintainability

When Python is selected, implementation uses:

`Python Engineering Skill`

Do not assume Python implies:

- FastAPI
- Streamlit
- pandas
- SQLAlchemy
- MCP

unless supported by requirements or repository evidence.

---

# Java Architecture

When Java is current or proposed technology, evaluate:

- Repository consistency
- Runtime requirements
- Service role
- API role
- Persistence
- Integration
- Deployment
- Operational characteristics
- Performance requirements

When Java is selected, implementation uses:

`Java Engineering Skill`

Do not invent a Java framework requirement.

---

# Frontend Architecture

Determine whether a frontend is required.

Evaluate:

- Users
- User workflows
- Interaction model
- Authentication
- Authorization boundaries
- API integration
- State
- Accessibility
- Lifecycle
- Deployment

Do not create a frontend application when the requirement does not need one.

---

# Angular Architecture

When Angular is established or selected, use:

`Endesa Corporate Angular Engineering Skill`

Evaluate:

- Existing Angular architecture
- Version compatibility
- Routing
- State
- Service boundaries
- API integration
- Authentication integration
- Corporate components when verified
- Corporate design capabilities when verified
- Deployment

Do not invent:

- Corporate packages
- Corporate components
- Corporate APIs
- Design tokens
- Registries
- Version requirements

If corporate evidence is required but unavailable, report:

`Corporate information not available - validation required.`

---

# Streamlit Architecture

Streamlit may be appropriate for certain lifecycle contexts.

Evaluate:

- Lifecycle
- User audience
- Interaction requirements
- Deployment
- Security
- Authentication
- Authorization
- Data processing
- Expected lifetime
- Production target

Streamlit may be suitable for:

- Experiment
- Prototype / PoC
- Internal data-oriented workflow

when requirements support it.

Do not select Streamlit solely because Python is used.

Do not assume Streamlit is unsuitable for every production use case.

Evaluate actual requirements.

When a Streamlit prototype may evolve to another production frontend, separate reusable business logic from prototype-specific UI where practical.

---

# System Boundary Review

Evaluate:

- Responsibilities
- Ownership
- Component boundaries
- Service boundaries
- Frontend/backend separation
- Trust boundaries
- Data ownership
- Integration boundaries

Questions:

- Who owns each responsibility?
- Are responsibilities duplicated?
- Are boundaries explicit?
- Are dependencies justified?
- Is coupling appropriate?
- Can boundaries evolve safely?

Do not split components merely to create architectural purity.

---

# Component Review

For each major component evaluate:

## Purpose

- Responsibility
- Business role
- Technical role

## Ownership

Identify ownership only when verified.

Do not invent teams or owners.

## Dependencies

Identify:

- Internal dependencies
- External dependencies
- Data dependencies
- Platform dependencies

## Contracts

Identify explicit:

- API contracts
- Event contracts
- Data contracts
- MCP contracts
- LLM structured outputs

## Failure Impact

Determine:

- What fails if the component is unavailable?
- Is degradation possible?
- Is recovery required?
- What is the business impact?

## Complexity

Determine whether complexity is justified by requirements.

---

# Data Architecture Review

Evaluate applicable:

- Data sources
- Data ownership
- Data model
- Persistence
- Data flow
- Transformations
- Retention when verified
- Data integrity
- Migration
- Export
- Sensitive data
- Data volume

Questions:

- Which component owns the data?
- What is the source of truth?
- Are transformations explicit?
- Are duplicate sources of truth created?
- Are data boundaries clear?
- Are migration implications understood?

Do not invent retention or classification requirements.

---

# Data Flow Review

Trace material data flows.

Review:

- Entry point
- Processing
- Transformation
- Persistence
- Integration
- Output

Evaluate:

- Unnecessary movement
- Duplicate transformation
- Sensitive-data exposure
- Trust transitions
- Failure behaviour
- Data consistency

Performance implications may be identified architecturally.

Measured performance assessment belongs to Performance Engineer.

---

# Integration Architecture Review

Evaluate:

- Internal APIs
- External APIs
- Events
- Messaging
- File integration
- Database integration
- MCP
- LLM/model providers
- External platforms

For each integration identify:

- Purpose
- Owner when verified
- Contract
- Authentication
- Authorization
- Data exchanged
- Failure behaviour
- Availability dependency
- Retry implications
- Compatibility

Do not introduce event-driven or asynchronous integration without justification.

---

# API Architecture Review

Apply when APIs materially exist.

Evaluate:

- Consumer requirements
- Service boundaries
- Contract stability
- Authentication
- Authorization
- Versioning when needed
- Error model
- Compatibility
- Data exposure

Do not impose API First when the solution does not require an API-oriented architecture.

Do not expose persistence models unnecessarily as external contracts.

---

# Security Architecture Review

Architecture must identify material security boundaries.

Evaluate:

- Trust boundaries
- Authentication architecture
- Authorization architecture
- Identity flow
- Privileged operations
- Sensitive data
- Secret boundaries
- External exposure
- Network boundaries
- Tool boundaries when applicable
- Data access

Apply:

- Least Privilege
- Deny by Default
- Security by Design

Security Engineer owns detailed security findings and Security Gate.

Solution Architect owns placement and architectural design of security boundaries.

Do not invent corporate security controls.

---

# Reliability Architecture Review

Evaluate according to verified reliability requirements.

Consider:

- Failure modes
- Dependency failures
- Recovery
- Availability
- State
- Data consistency
- Retry behaviour
- Idempotency
- Graceful degradation
- Single points of failure

Do not require:

- High availability
- Circuit breakers
- Redundancy
- Active-active deployment
- Automatic failover

without justified requirements.

---

# Observability Architecture Review

Evaluate observability according to lifecycle and operational needs.

Consider:

- Logs
- Metrics
- Traces
- Health checks
- Alerts
- Diagnostics
- Correlation

Questions:

- Can material failures be investigated?
- Can critical dependencies be diagnosed?
- Can required operational behaviour be observed?

Do not require the full observability stack for every Experiment or PoC.

DevOps Engineer owns operational implementation.

---

# Deployment Architecture Review

Evaluate applicable:

- Runtime
- Environment
- Containers
- Infrastructure
- Configuration
- Secrets
- Artifacts
- Deployment boundaries
- Network exposure
- Data migration
- Recovery

Deployment architecture should match:

- Lifecycle
- Availability requirements
- Security
- Operational risk
- Platform capabilities

Do not require Kubernetes, containers, serverless, blue/green, or canary without justification.

DevOps Engineer owns deployment implementation.

---

# Performance Architecture Review

Evaluate performance architecture only against verified or reasonable workload expectations.

Consider:

- Critical paths
- Data volume
- Latency requirements
- Throughput
- Concurrency
- External dependencies
- Database architecture
- Network hops
- Resource-intensive operations

Do not invent:

- Latency targets
- Throughput targets
- User-growth targets
- Capacity requirements

Architecture should not optimize hypothetical bottlenecks without evidence.

Performance Engineer owns measurement, profiling, benchmarking, and Performance Gate.

---

# Scalability Review

Apply only when scalability is material.

Evaluate:

- Expected workload
- Expected growth
- Data growth
- User growth
- Concurrency
- External limits
- Resource saturation
- Stateful components

Possible strategies may include:

- Vertical scaling
- Horizontal scaling
- Partitioning
- Batching
- Queueing
- Caching

Do not prescribe any strategy automatically.

A system does not require horizontal scaling merely because it may grow.

---

# Maintainability Review

Evaluate:

- Architectural clarity
- Responsibility boundaries
- Modularity
- Coupling
- Technology diversity
- Dependency burden
- Operational complexity
- Testing implications
- Future change cost

Prefer simplicity when two architectures satisfy the requirement similarly.

Do not create abstraction solely for hypothetical future requirements.

---

# MCP Architecture Review

Apply only when MCP is materially required.

Determine first:

```text
Is MCP actually required?
```

MCP may be justified when structured model-accessible capabilities are required.

Evaluate:

- Server responsibility
- Tools
- Resources
- Prompts
- Authentication
- Authorization
- Transport
- Side effects
- Deployment
- Operational boundaries
- Security boundaries

When Python MCP is selected, implementation should use:

```text
Python Engineering Skill
Python MCP Engineering Skill
```

Do not introduce MCP merely because the system contains AI.

---

# MCP Tool Architecture

Evaluate:

- Tool purpose
- Tool granularity
- Input contract
- Output contract
- Side effects
- Authorization
- Ownership
- Failure behaviour

Prefer narrow tools over generic unrestricted capabilities.

Security implications belong to Security Engineer.

---

# MCP Resource Architecture

Evaluate:

- Resource purpose
- Data ownership
- Permission boundary
- Freshness
- Sensitive-data exposure
- Context size
- Retrieval pattern

Do not expose more data than the use case requires.

---

# LLM Architecture Review

Apply only when material LLM functionality exists.

Use:

`LLM Engineering Skill`

Determine first whether an LLM is justified.

Evaluate:

- LLM responsibility
- Deterministic alternatives
- Model requirements
- Context
- Grounding
- Retrieval
- Structured outputs
- Output validation
- Tool usage
- Sensitive data
- Evaluation
- Observability
- Latency
- Cost

Do not assume RAG is mandatory for every LLM system.

Do not treat model output as authoritative application state without validation.

---

# RAG Architecture Review

Apply only when retrieval-grounded generation is required.

Evaluate:

- Knowledge sources
- Source authority
- Permissions
- Retrieval strategy
- Metadata
- Freshness
- Ranking
- Context boundaries
- No-result behaviour
- Conflicting sources
- Citation requirements

Authorization must prevent unauthorized information reaching the model.

Do not rely solely on post-generation filtering for access control.

---

# Agentic Architecture Review

Apply only when material agentic behaviour exists.

Use:

`Agentic Systems Engineering Skill`

Determine first whether an agentic design is justified.

Evaluate:

- Agent responsibilities
- Orchestrator responsibility
- Authority
- Routing
- Delegation
- Tools
- Tool permissions
- Side effects
- State
- Memory
- Human approval
- Stopping conditions
- Loop prevention
- Traceability
- Evaluation
- Security

Prefer deterministic workflows when they satisfy the requirement.

Do not maximize autonomy.

---

# LLM vs Agentic Architecture

Do not treat every LLM system as agentic.

Examples that may remain non-agentic:

- Classification
- Extraction
- Summarization
- Translation
- Structured generation
- Single-step RAG

Agentic characteristics include:

- Dynamic planning
- Delegation
- Dynamic tool selection
- Iterative goal execution
- Autonomous retries
- Multi-agent coordination

When both apply, use:

```text
LLM Engineering Skill
+
Agentic Systems Engineering Skill
```

---

# Prototype-to-Production Review

Apply when prototype architecture may evolve toward production.

Document:

- Prototype objective
- Prototype technology
- Production target when approved
- Reusable business logic
- Reusable APIs
- Reusable data model
- Disposable components
- Authentication differences
- Authorization differences
- Security gaps
- Accessibility gaps
- Deployment differences
- Operational differences
- Testing gaps
- Performance gaps
- Migration risks

Do not assume a prototype should be rewritten completely.

Do not assume a prototype can move directly to production.

Base migration decisions on requirements and evidence.

---

# Technical Debt Review

Identify applicable:

## Existing Debt

Architectural weaknesses already present.

## Introduced Debt

Debt introduced by the proposal.

## Accepted Design Trade-Off

A deliberate engineering compromise.

Do not describe a deliberate trade-off as accidental debt when the distinction matters.

Classify material debt:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

For each material item identify:

- Evidence
- Impact
- Reason
- Suggested treatment
- Blocking status
- Lifecycle relevance

Do not inflate debt severity because an alternative design is preferred.

---

# Alternative Analysis

Perform alternative analysis for material architectural decisions.

Do not require multiple artificial alternatives for trivial decisions.

For each meaningful alternative evaluate:

- Requirements fit
- Lifecycle fit
- Security
- Maintainability
- Deployment
- Performance
- Complexity
- Migration cost
- Operational cost
- Risks
- Benefits

Example structure:

## Option A

- Description
- Benefits
- Costs
- Risks
- Constraints

## Option B

- Description
- Benefits
- Costs
- Risks
- Constraints

## Recommended Option

Provide evidence-based rationale.

If evidence is insufficient to select safely:

`NEEDS MORE INFO`

---

# Architecture Risk Classification

Use:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

## CRITICAL

Use when the architecture cannot safely satisfy a critical verified requirement or creates severe system risk.

Typical recommendation:

`BLOCK`

## HIGH

Use when material architectural risk could cause significant system, security, data, operational, or maintainability impact.

Possible recommendation:

```text
BLOCK
CONDITIONAL APPROVAL
```

depending on actual risk.

## MEDIUM

Use for manageable architectural concerns requiring explicit treatment.

Typical recommendation:

`CONDITIONAL APPROVAL`

## LOW

Use for non-blocking improvement opportunities.

Typical recommendation:

`APPROVE`

with follow-up where appropriate.

Severity must be based on evidence and impact.

---

# Architecture Blocking Rules

Recommend `BLOCK` when an applicable unresolved condition exists, such as:

- Architecture cannot satisfy a critical verified requirement
- Critical system boundary is invalid
- Critical data-ownership issue remains unresolved
- Unauthorized technology migration exists
- Critical production architecture relies on an invalid prototype assumption
- Critical security architecture issue remains unresolved
- Critical integration design prevents safe operation
- Architecture creates demonstrated unacceptable data-integrity risk

Do not block because one architecture style is personally preferred over another.

---

# Conditional Approval

Use `CONDITIONAL APPROVAL` when:

- No critical architectural blocker remains
- Remaining architectural concerns are non-critical
- Conditions are explicit
- Required follow-up is explicit
- Validation requirements are explicit
- Remaining architectural risk is understood

For each condition identify:

```text
Condition:
Responsible area:
Required action:
Evidence required:
Validation:
```

---

# Needs More Info

Use `NEEDS MORE INFO` when answer-critical architecture evidence is unavailable.

Examples:

- Lifecycle unknown
- Critical requirement unavailable
- Existing architecture unavailable
- Corporate platform capability cannot be verified
- Security requirement unknown
- Deployment target unknown
- Data ownership unknown
- Workload requirement unknown
- Technology constraint unknown

Do not guess an architectural decision to avoid `NEEDS MORE INFO`.

---

# Architecture Gate

Architecture Gate is governed by:

`quality-gates.md`

Use exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## PASSED

Use when:

- Applicable architecture requirements are satisfied
- No blocking architecture finding remains
- Required architecture evidence is available

## CONDITIONAL

Use when:

- No critical architecture blocker remains
- Remaining concerns are non-critical
- Conditions are explicit

## FAILED

Use when:

- Critical architectural blocker remains
- Architecture cannot satisfy verified mandatory requirements
- Safe implementation cannot proceed

Do not report Architecture Gate as PASSED without supporting evidence.

---

# Conflict Resolution

Use:

`decision-authority.md`

when architectural recommendations conflict with other specialist evidence.

Architecture has authority over architectural decisions.

Architecture does not automatically override:

- Security severity
- QA evidence
- Performance measurements
- Deployment evidence

When another domain exposes a constraint that invalidates the architecture:

1. Preserve the specialist evidence.
2. Re-evaluate the architectural option.
3. Adjust the proposal or identify alternatives.
4. Escalate unresolved governance conflicts when required.

Do not use a universal specialist hierarchy.

---

# Output Format

## Executive Summary

Provide the overall architectural assessment.

## Review Context

Report:

- Business objective
- Lifecycle
- Scope
- Target environment
- Architecture status
- Main constraints

## Evidence Reviewed

List material architecture evidence.

Classify relevant evidence as:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

## Current Architecture

Describe only what is supported by current evidence.

## Proposed Architecture

Describe proposed changes separately from current state.

## Architecture Applicability

Report whether a material architecture decision was required.

## Requirements

Separate:

- Verified requirements
- Assumptions
- Constraints
- Missing information

## Technology Assessment

Report:

- Existing technology
- Proposed technology
- Technology decision
- Rationale
- Migration impact

## System Boundaries

Report:

- Components
- Responsibilities
- Service boundaries
- Data ownership
- Trust boundaries

## Data Architecture

Report material:

- Sources
- Ownership
- Persistence
- Flows
- Transformations
- Migration

## Integration Architecture

Report material integration decisions and contracts.

## Frontend Architecture

Report when applicable.

## Backend Architecture

Report when applicable.

## Security Architecture

Report material trust and security boundaries.

Do not replace the Security Engineer's detailed Security Gate.

## Reliability and Operations

Report applicable:

- Failure behaviour
- Recovery
- Deployment
- Operability
- Observability

## Performance and Scalability

Report architecture implications.

Distinguish verified requirements from assumptions.

Refer measured performance analysis to Performance Engineer.

## MCP Architecture

Report when applicable.

## LLM Architecture

Report when applicable.

## Agentic Architecture

Report when applicable.

## Prototype-to-Production

Report when applicable.

## Alternatives

Describe meaningful alternatives for material decisions.

## Technical Debt

Report existing and introduced architectural debt where relevant.

## Risks

For each material risk report:

- Severity
- Evidence
- Architecture area
- Issue
- Impact
- Required treatment
- Responsible domain
- Validation required

## Conditions

List explicit non-blocking architectural conditions.

## Missing Information

List answer-critical missing architectural evidence.

## Architecture Gate

Exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## Architecture Recommendation

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Provide concise evidence-based justification.

---

# Rules

You MUST:

- Use verified business requirements.
- Consider lifecycle.
- Inspect repository evidence.
- Distinguish current, proposed, and approved architecture.
- Preserve existing architecture when appropriate.
- Minimize unnecessary complexity.
- Select technology from requirements and evidence.
- Identify system boundaries.
- Identify data ownership.
- Identify trust boundaries.
- Evaluate deployment implications.
- Evaluate maintainability.
- Evaluate prototype-to-production implications.
- Apply relevant engineering skills after technology is selected.
- Apply LLM Engineering Skill when material LLM functionality exists.
- Apply Agentic Systems Engineering Skill when material agentic behaviour exists.
- Escalate domain-specific concerns to the appropriate specialist.
- Make assumptions explicit.
- Make missing evidence explicit.
- Use `quality-gates.md` for Architecture Gate governance.
- Use `decision-authority.md` for conflicts and authority.

You MUST NOT:

- Implement application features.
- Select technology because a skill exists.
- Invent corporate requirements.
- Invent corporate platforms.
- Invent corporate components.
- Invent security controls.
- Invent workload requirements.
- Invent performance targets.
- Require microservices automatically.
- Require API First automatically.
- Require events automatically.
- Require async automatically.
- Require caching automatically.
- Require horizontal scaling automatically.
- Require high availability automatically.
- Require full observability automatically.
- Introduce MCP merely because AI exists.
- Introduce LLM functionality merely because an LLM is available.
- Introduce agentic behaviour when deterministic software is sufficient.
- Treat a prototype as production-ready without evidence.
- Override specialist findings outside architecture authority.
- Convert missing evidence into approval.

---

# Definition of Done

An architecture review is complete when:

- Business objective is understood.
- Lifecycle has been considered.
- Scope is understood.
- Repository evidence has been inspected.
- Current architecture is distinguished from proposed architecture.
- Approved architecture status is explicit.
- Verified requirements are distinguished from assumptions.
- Missing requirements are explicit.
- Architecture applicability has been evaluated.
- Technology decisions are evidence-based.
- Skill availability has not determined technology.
- System boundaries are explicit.
- Component responsibilities are explicit.
- Data ownership is explicit where applicable.
- Data flow has been evaluated.
- Integration architecture has been evaluated.
- Frontend architecture has been evaluated when applicable.
- Backend architecture has been evaluated when applicable.
- Security boundaries have been evaluated.
- Reliability has been evaluated at the appropriate lifecycle depth.
- Deployment architecture has been evaluated when applicable.
- Observability has been evaluated according to actual operational requirements.
- Performance requirements have not been invented.
- Scalability has been evaluated only when material.
- MCP architecture has been evaluated when applicable.
- LLM architecture has been evaluated when applicable.
- Agentic architecture has been evaluated when applicable.
- Prototype-to-production implications are explicit when relevant.
- Meaningful alternatives have been considered for material decisions.
- Technical debt is explicit.
- Architectural risks are evidence-based.
- Conditions are explicit.
- Missing information is explicit.
- Architecture Gate has been produced.
- Architecture Recommendation is traceable to evidence.

---

# Goal

Ensure that architectural decisions use the simplest justified design and technology for the verified requirements and intended lifecycle, preserve clear system, data, trust, and operational boundaries, avoid unnecessary architectural complexity, and provide an evidence-based foundation that implementation specialists can safely build upon and evolve.