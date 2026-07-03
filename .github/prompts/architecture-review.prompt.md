---
name: Architecture Review Prompt
description: Standardized architecture review framework for evaluating software systems, services, applications, AI platforms, MCP servers, and multi-agent systems.
model: Auto (copilot)
---

# Architecture Review Prompt

## Objective

Perform a comprehensive architectural assessment of the proposed system, change, implementation, design, or platform.

The objective is to evaluate:

- Architectural correctness
- Scalability
- Maintainability
- Reliability
- Security alignment
- Operational complexity
- Long-term sustainability

Focus on system design rather than implementation details.

---

# Architecture Principles

Always evaluate against:

- Separation of Concerns
- High Cohesion
- Low Coupling
- Security by Design
- API First
- Observability by Default
- Scalability
- Maintainability
- Testability

Architecture should optimize for long-term system health rather than short-term convenience.

---

# Review Context

Before starting, identify:

## System Category

Classify the system:

```text
Monolith
Modular Monolith
Microservices
Event Driven System
Serverless Architecture
Data Platform
MCP Server
AI Agent Platform
Multi-Agent System
RAG System
Hybrid Platform
```

---

## Business Context

Determine:

- Business objective
- Critical business flows
- Success criteria
- System constraints

Questions:

- Why does this system exist?
- What business problem does it solve?
- What are the operational expectations?

---

## Technical Context

Identify:

- Main technologies
- Integrations
- Datastores
- External dependencies
- Deployment model

---

# System Boundary Review

Evaluate:

- responsibilities
- ownership
- dependencies
- service boundaries

Questions:

- Are responsibilities clearly separated?
- Are boundaries well defined?
- Does any component own too many concerns?

---

# Component Review

For each major component evaluate:

## Purpose

What responsibility does it own?

---

## Dependencies

Which systems does it depend on?

---

## Complexity

Is complexity justified?

---

## Failure Impact

What happens if this component becomes unavailable?

---

# Data Flow Review

Evaluate how information moves through the system.

Review:

- request flows
- event flows
- persistence flows
- integration flows

Questions:

- Is data movement efficient?
- Are unnecessary hops present?
- Are bottlenecks likely?

---

# Integration Review

Evaluate:

- internal integrations
- third-party integrations
- API contracts
- event contracts

Questions:

- Are interfaces stable?
- Is coupling excessive?
- Are dependencies manageable?

---

# Scalability Review

Evaluate:

## Horizontal Scaling

Can the solution scale across instances?

---

## Vertical Scaling

Can resources be increased when necessary?

---

## Data Scaling

Will databases scale appropriately?

---

## User Growth

Can the architecture support expected growth?

---

## AI Growth

For AI applications evaluate:

- context growth
- tool growth
- agent growth
- memory growth

---

# Maintainability Review

Evaluate:

- architectural clarity
- code ownership
- modularity
- future change cost

Questions:

- Can new features be added safely?
- Are boundaries understandable?
- Is technical debt accumulating?

---

# Reliability Review

Evaluate:

- fault tolerance
- recovery mechanisms
- graceful degradation
- resilience patterns

Questions:

- What failures are expected?
- What failures are catastrophic?
- Can the system recover automatically?

---

# Observability Review

Verify:

- logs
- metrics
- traces
- monitoring

Questions:

- Can failures be diagnosed?
- Can bottlenecks be identified?
- Can incidents be investigated?

---

# Security Alignment Review

Validate architectural security.

Review:

- trust boundaries
- privilege models
- authentication architecture
- authorization architecture

Questions:

- Are trust assumptions explicit?
- Are security controls properly placed?

Security implementation details should be delegated to the Security Engineer.

---

# AI Architecture Review

Apply when AI components exist.

Evaluate:

## Prompt Layer

- prompt ownership
- prompt governance
- prompt versioning

---

## Tool Layer

- permissions
- responsibility separation
- execution controls

---

## Retrieval Layer

- source quality
- retrieval strategy
- context boundaries

---

## Agent Layer

- agent responsibilities
- delegation model
- orchestration design

---

## Decision Layer

- authority rules
- governance
- conflict resolution

---

# MCP Architecture Review

Apply when MCP servers are involved.

Review:

## Tool Architecture

- tool ownership
- responsibilities
- boundaries

---

## Resource Architecture

- resource exposure
- data ownership
- access patterns

---

## Transport Architecture

- local deployment
- remote deployment
- scaling considerations

---

## Multi-Server Design

- modularity
- ownership
- operational complexity

---

# Technical Debt Review

Identify:

## Existing Debt

Current architectural weaknesses.

---

## Introduced Debt

New debt introduced by the proposal.

---

## Debt Severity

Classify:

```text
LOW
MEDIUM
HIGH
CRITICAL
```

---

# Alternative Analysis

For significant architectural decisions provide:

## Alternative A

Pros

Cons

Complexity

Risk

---

## Alternative B

Pros

Cons

Complexity

Risk

---

## Recommended Option

Provide justification.

---

# Risk Classification

## Critical

System integrity threatened.

Result:

```text
BLOCK
```

---

## High

Significant long-term platform risk.

Result:

```text
CONDITIONAL APPROVAL
or
BLOCK
```

---

## Medium

Manageable architectural concerns.

Result:

```text
CONDITIONAL APPROVAL
```

---

## Low

Improvement opportunities.

Result:

```text
APPROVE
```

---

# Final Output Format

## Executive Summary

Provide a high-level assessment.

---

## Current Architecture

Describe the current state.

---

## Architecture Assessment

Evaluate:

- structure
- boundaries
- dependencies
- scalability

---

## Risks

### Critical Risks

Description

Impact

Recommendation

---

### High Risks

Description

Impact

Recommendation

---

### Medium Risks

Description

Recommendation

---

### Low Risks

Description

Recommendation

---

## Technical Debt

Document identified technical debt.

---

## Alternative Analysis

Compare alternative approaches.

---

## Recommendation

Provide the preferred architecture and rationale.

---

## Architecture Gate Result

Allowed values:

```text
PASSED

CONDITIONAL

FAILED
```

---

## Final Recommendation

Allowed values:

```text
APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO
```

Provide justification.

---

# Success Criteria

An architecture review is complete when:

- system boundaries are evaluated
- data flow is analyzed
- scalability is assessed
- maintainability is reviewed
- observability is considered
- technical debt is identified
- alternatives are documented
- recommendations are justified

The review must focus on long-term system sustainability rather than implementation preferences.