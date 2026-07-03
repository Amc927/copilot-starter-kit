---
name: Agentic Systems Engineering Skill
description: Reusable knowledge base for designing, orchestrating, governing and evaluating multi-agent AI systems.
---

# Agentic Systems Engineering Skill

## Purpose

This skill provides principles, architectures, governance models, execution patterns, and best practices for building multi-agent AI systems.

It applies to:

- AI Engineering Teams
- Autonomous Agents
- Copilot Systems
- Multi-Agent Frameworks
- Agentic Workflows
- MCP-based Agent Systems
- Orchestration Platforms

---

# Core Principle

An agentic system is a coordinated organization of specialized agents working toward a common objective.

The goal is not to maximize autonomy.

The goal is to maximize:

- correctness
- reliability
- traceability
- safety
- maintainability

---

# Agent Design Principles

Every agent must have:

- a single responsibility
- a clearly defined scope
- explicit inputs
- explicit outputs
- authority boundaries

Bad agents:

- perform multiple unrelated functions
- redefine objectives
- operate without constraints

Good agents:

- solve one problem well
- collaborate through structured interfaces
- produce deterministic outputs

---

# Agent Hierarchy

Recommended pattern:

```text
Orchestrator
        │
        ▼
Specialist Agents
        │
        ▼
Decision Layer
```

Responsibilities:

### Orchestrator

- route tasks
- decompose work
- aggregate results
- resolve conflicts
- make final decisions

### Specialist Agents

- provide expert analysis
- validate specific concerns
- return structured findings

### Decision Layer

- apply governance rules
- apply quality gates
- determine final outcome

---

# Agent Communication

Agents communicate using structured contracts.

Avoid:

```text
free-form conversation
```

Prefer:

```json
{
  "agent": "",
  "findings": [],
  "risks": [],
  "recommendation": ""
}
```

---

# Delegation Model

Delegation should be:

- intentional
- traceable
- limited

A task must only be delegated when another agent owns the expertise.

Never delegate responsibility.

The delegating agent remains accountable.

---

# Agent Routing

Routing decisions should consider:

- task type
- affected components
- risk level
- required expertise

Example:

Feature

→ Backend
→ QA

Security impact

→ Security
→ QA

Infrastructure

→ DevOps
→ Security

---

# Conflict Resolution

Agents may disagree.

Conflicts must be resolved through predefined authority rules.

Example:

```text
Security
    >
QA
    >
Performance
    >
Implementation Agents
```

Authority must be documented.

---

# Quality Gates

Agent outputs should not directly trigger release decisions.

Instead:

```text
Agent Findings
       ↓
Quality Gates
       ↓
Decision
```

Benefits:

- consistency
- governance
- auditability

---

# Decision Models

Every execution must end with one decision.

Allowed values:

```text
APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO
```

Avoid ambiguous outcomes.

---

# State Management

Agent systems must maintain:

- execution state
- task state
- workflow state
- decision state

Avoid hidden memory.

All important state should be observable.

---

# Context Management

Each agent receives only:

- relevant context
- current task information
- required dependencies

Avoid sending the entire system context.

Context overload reduces quality.

---

# Memory Strategy

Use memory only when beneficial.

Examples:

Useful memory:

- project preferences
- architecture decisions
- recurring workflows

Avoid storing:

- temporary execution details
- transient conversations

---

# Observability

Every execution should produce:

- execution identifier
- participating agents
- findings
- decisions
- timestamps

Minimal model:

```json
{
  "execution_id": "",
  "agents": [],
  "decision": "",
  "risks": []
}
```

---

# Failure Handling

Agent failures must be expected.

Handle:

- missing data
- invalid outputs
- unavailable tools
- contradictory findings

Fallbacks should be defined.

---

# Human-in-the-Loop

Required when:

- risk is high
- authority limits are reached
- security concerns exist
- production impact is significant

Humans approve strategy.

Agents support decisions.

---

# Security Principles

Never allow:

- unrestricted tool use
- unrestricted code execution
- unrestricted internet access
- unrestricted data access

Apply:

- least privilege
- zero trust
- explicit permissions

---

# Scalability

Agent count should not grow indefinitely.

When complexity increases:

Prefer:

- reusable skills
- reusable workflows
- reusable governance

Avoid:

- creating agents for every problem

---

# Anti-Patterns

Avoid:

### Agent Explosion

Too many agents solving similar problems.

### Circular Delegation

Agent A →
Agent B →
Agent C →
Agent A

### Authority Confusion

Unclear decision ownership.

### Hidden State

Critical information stored outside observable systems.

### Autonomous Production Changes

Agents modifying production without approval.

---

# Definition of Done

An agentic system is production-ready when:

- responsibilities are clear
- authority rules exist
- routing logic exists
- quality gates exist
- observability exists
- decisions are traceable
- failures are handled
- security controls are enforced