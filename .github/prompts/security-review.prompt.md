---
name: Security Review Prompt
description: Standardized security review framework for evaluating software changes, APIs, applications, infrastructure components, MCP servers, AI agents, and LLM-powered systems.
model: Auto (copilot)
---

# Security Review Prompt

## Objective

Perform a comprehensive security assessment of the provided change, system, architecture, implementation, or design.

The goal is to identify:

- Exploitable vulnerabilities
- Security weaknesses
- Trust boundary violations
- Data protection concerns
- Authentication risks
- Authorization risks
- Infrastructure risks
- AI/LLM security risks

Focus on real-world exploitability rather than theoretical concerns.

---

# Security Review Principles

Always apply:

- Zero Trust
- Least Privilege
- Defense in Depth
- Secure by Design
- Assume Breach

Security recommendations must be:

- actionable
- risk-based
- technically justified

---

# Review Context

Before beginning, determine:

## System Type

Classify the system as one or more of:

```text
Web Application
Backend Service
API
Microservice
Database
Mobile Application
Desktop Application
Infrastructure Component
Cloud Service
MCP Server
AI Agent
LLM Application
RAG System
Multi-Agent System
```

---

## Data Classification

Identify data being processed:

```text
Public
Internal
Confidential
Sensitive
Regulated
```

Examples:

- Personal Data
- Financial Data
- Credentials
- Tokens
- Internal Documents
- Intellectual Property

---

## Trust Boundaries

Identify:

- user input boundaries
- external integrations
- third-party services
- internal services
- privileged components

Document every trust boundary discovered.

---

# Security Review Checklist

## Authentication

Review:

- identity verification
- session management
- token handling
- credential storage
- MFA controls

Questions:

- Can authentication be bypassed?
- Are tokens protected?
- Are expired credentials handled correctly?

---

## Authorization

Review:

- role enforcement
- permission validation
- object-level access controls

Questions:

- Can users access data belonging to others?
- Are permissions verified server-side?
- Is privilege escalation possible?

---

## Input Validation

Review:

- request validation
- schema validation
- parameter handling

Questions:

- Is untrusted input accepted?
- Could injection attacks occur?
- Is validation performed consistently?

---

## Data Protection

Review:

- encryption
- sensitive data storage
- data transmission
- logging practices

Questions:

- Is sensitive information exposed?
- Is data encrypted appropriately?
- Are secrets handled securely?

---

## API Security

Review:

- authentication
- authorization
- rate limiting
- data exposure
- error handling

Questions:

- Can APIs be abused?
- Is excessive data exposed?
- Are API contracts secure?

---

## Infrastructure Security

Review:

- network exposure
- secret management
- deployment configuration
- access controls

Questions:

- Are secrets protected?
- Is infrastructure unnecessarily exposed?
- Are least-privilege principles followed?

---

# OWASP Review

Evaluate against:

## Broken Access Control

Review authorization boundaries.

---

## Cryptographic Failures

Review encryption usage and key handling.

---

## Injection

Review:

- SQL Injection
- Command Injection
- Template Injection
- Prompt Injection

---

## Insecure Design

Review system architecture.

---

## Security Misconfiguration

Review:

- environments
- services
- infrastructure

---

## Vulnerable Components

Review dependencies and third-party integrations.

---

## Authentication Failures

Review identity controls.

---

## Integrity Failures

Review deployment and supply chain risks.

---

## Logging and Monitoring Failures

Review:

- audit trails
- incident visibility
- monitoring coverage

---

# AI / LLM Security Review

Only apply when AI systems are involved.

Review:

## Prompt Injection

Can external content manipulate behavior?

---

## Indirect Prompt Injection

Can retrieved content modify instructions?

---

## Context Poisoning

Can knowledge sources influence results maliciously?

---

## Tool Abuse

Can a model invoke tools in unsafe ways?

---

## Data Leakage

Can sensitive information be exposed through prompts, context, retrieval, or outputs?

---

## Autonomous Actions

Can the model perform actions without sufficient controls?

---

# MCP Security Review

Only apply when MCP servers are present.

Review:

## Tool Permissions

Are tools restricted appropriately?

---

## Resource Access

Can resources expose sensitive data?

---

## Transport Security

Review:

- HTTP exposure
- authentication
- authorization

---

## Server Trust Boundary

Identify:

- client trust assumptions
- tool execution risks
- external integrations

---

# Risk Classification

## Critical

Immediate exploitation possible.

Examples:

- authorization bypass
- credential exposure
- sensitive data leakage

Recommendation:

```text
BLOCK
```

---

## High

Exploitation likely under realistic conditions.

Recommendation:

```text
BLOCK
or
CONDITIONAL APPROVAL
```

depending on severity.

---

## Medium

Limited exploitability or mitigating controls exist.

Recommendation:

```text
CONDITIONAL APPROVAL
```

---

## Low

Best-practice improvements.

Recommendation:

```text
APPROVE
```

with recommendations.

---

# Final Output Format

## Executive Summary

Provide an overall assessment.

---

## Threat Model

Document:

- assets
- trust boundaries
- attack surfaces

---

## Findings

### Critical Findings

For each issue:

- Description
- Impact
- Exploitability
- Recommendation

---

### High Risk Findings

For each issue:

- Description
- Impact
- Recommendation

---

### Medium Risk Findings

For each issue:

- Description
- Recommendation

---

### Low Risk Findings

For each issue:

- Description
- Recommendation

---

## Security Gate Result

Allowed values:

```text
PASSED
CONDITIONAL
FAILED
```

---

## Risk Summary

Document:

- highest severity
- overall risk level
- number of findings

---

## Final Recommendation

Allowed values:

```text
APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO
```

Provide justification for the recommendation.

---

# Success Criteria

A security review is considered complete when:

- trust boundaries have been identified
- attack surfaces have been evaluated
- security findings have been documented
- risks have been classified
- mitigations have been proposed
- a final recommendation has been produced

The review must focus on real security risk rather than theoretical concerns.