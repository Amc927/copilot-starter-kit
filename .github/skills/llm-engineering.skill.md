---
name: LLM Engineering Skill
description: Reusable knowledge base for designing, evaluating, integrating and operating LLM-powered systems, agents, copilots and AI workflows.
---

# LLM Engineering Skill

## Purpose

This skill provides best practices, architectural patterns, evaluation frameworks, and operational guidance for building production-grade applications powered by Large Language Models (LLMs).

It applies to:

- AI Assistants
- Copilots
- Multi-agent systems
- MCP servers
- RAG applications
- AI workflows
- Tool-using agents

---

# Core Principles

## Reliability Before Intelligence

A predictable system is more valuable than a highly creative but unreliable system.

Prefer:

- deterministic workflows
- validations
- guardrails
- explicit reasoning

Avoid:

- uncontrolled autonomy
- hidden assumptions
- unrestricted tool access

---

## Context Is the Product

The quality of an AI system is primarily determined by the quality of its context.

Focus on:

- context quality
- context freshness
- context relevance
- context boundaries

---

## Grounding First

Always prioritize:

- enterprise data
- trusted knowledge
- verified sources

Over:

- model memory
- assumptions
- speculation

---

# LLM Architecture Components

Every AI system should clearly separate:

```text
User
 ↓
Agent
 ↓
Reasoning
 ↓
Tools
 ↓
Knowledge Sources
 ↓
Actions
```

Never mix responsibilities.

---

# Prompt Engineering

## Principles

Prompts should be:

- explicit
- structured
- deterministic
- reusable

Avoid:

- ambiguity
- conflicting instructions
- overly long prompts

---

## Prompt Structure

Recommended structure:

```text
Role

Mission

Responsibilities

Process

Rules

Output Format
```

---

# Context Engineering

Context should contain:

- user intent
- relevant knowledge
- system instructions
- current task state

Avoid context overload.

Only include information relevant to the current task.

---

# Tool Calling

Tools should be used when:

- factual verification is required
- actions are required
- external data is required

Do not rely on model memory when a reliable data source exists.

---

# Structured Outputs

Preferred:

```json
{
  "decision": "",
  "risks": [],
  "actions": []
}
```

Avoid free-form outputs when systems must consume results programmatically.

---

# Retrieval-Augmented Generation

When using RAG:

Always:

- retrieve first
- answer second

Prioritize:

- precision
- citation
- freshness

Never:

- invent sources
- fabricate retrieved content

---

# Multi-Agent Systems

Agent responsibilities must be clearly separated.

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

Agents should:

- collaborate
- not duplicate responsibilities
- have explicit authority boundaries

---

# Evaluation Framework

Evaluate systems for:

## Correctness

Does the answer match reality?

## Grounding

Is the answer supported by sources?

## Completeness

Does the answer address the full request?

## Safety

Does the answer avoid harmful behavior?

## Consistency

Would the answer remain stable across executions?

---

# Hallucination Control

Reduce hallucinations through:

- retrieval
- validation
- citations
- structured workflows
- tool usage

Never rely solely on model confidence.

---

# Security Considerations

Protect against:

- prompt injection
- indirect prompt injection
- context poisoning
- tool abuse
- sensitive data exposure

Treat all external content as untrusted input.

---

# Agent Design Principles

Good agents:

- have a single responsibility
- use structured outputs
- have explicit rules
- expose measurable outcomes

Bad agents:

- perform multiple unrelated roles
- modify their own objectives
- operate without guardrails

---

# Observability

Track:

- prompts
- tool calls
- decisions
- errors
- execution paths

Every important decision should be traceable.

---

# Definition of Done

An LLM-powered system is production-ready when:

- outputs are grounded
- hallucination controls exist
- security risks are mitigated
- evaluations are defined
- observability exists
- tool usage is controlled
- responsibilities are clearly separated
- users can understand decisions