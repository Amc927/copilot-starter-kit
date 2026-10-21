# Traceability Model

Version: 2.0

---

# Purpose

The Traceability Model defines how material engineering information is connected across the AI Engineering Team System.

Its objective is to make engineering activity explainable and reviewable without inventing execution metadata that the platform does not provide.

Traceability may connect:

- Requests
- Objectives
- Requirements
- Assumptions
- Lifecycle
- Workflows
- Agents
- Skills
- Delegations
- Tools
- Evidence
- Tests
- Evaluations
- Findings
- Quality Gates
- Conditions
- Missing evidence
- Human approvals
- Formal risk treatment
- Residual risk
- Final engineering decisions

Traceability depth must reflect:

- Lifecycle
- Risk
- Business criticality
- Security impact
- Deployment impact
- Reversibility
- Governance requirements
- Platform capability

Trace what actually happened.

Do not fabricate what the execution environment did not provide.

---

# Related Governance Artifacts

This model works with:

```text
decision-log-template.md
decision-authority.md
quality-gates.md
feature-workflow.md
bugfix-workflow.md
security-workflow.md
release-checklist.md
```

These artifacts have different responsibilities.

## decision-authority.md

Defines:

- Domain authority
- Conflict resolution
- Human governance
- Formal risk-treatment boundaries
- Final engineering decision rules

## quality-gates.md

Defines:

- Gate applicability
- Gate owners
- Gate evidence
- Gate states
- Gate aggregation

## decision-log-template.md

Defines:

- How material decision evidence may be recorded
- Optional metadata
- Participating agents
- Active skills
- Evidence
- Gates
- Conditions
- Missing information
- Human approval
- Risk treatment
- Final decision

## Workflows

Define repeatable engineering execution flows.

The Traceability Model connects these artifacts but does not replace them.

---

# Core Principles

Always apply:

- Trace actual events
- Preserve evidence provenance
- Preserve uncertainty
- Record only actual participants
- Record only actual tool execution
- Record only actual validation
- Minimize sensitive data
- Keep lifecycle proportionality
- Preserve domain authority
- Preserve historical decision context where required

Mandatory rules:

```text
AGENT DEFINED != AGENT PARTICIPATED
SKILL AVAILABLE != SKILL ACTIVATED
TOOL CONFIGURED != TOOL EXECUTED
TEST DEFINED != TEST EXECUTED
WORKFLOW DEFINED != WORKFLOW EXECUTED
GATE APPLICABLE != GATE PASSED
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
HUMAN APPROVAL REQUIRED != HUMAN APPROVAL GRANTED
RESIDUAL RISK RECORDED != FORMAL RISK ACCEPTED
```

---

# Traceability Scope

Not every interaction requires full enterprise traceability.

Traceability must be proportional to the execution.

## Low-Risk Execution

May require only:

- Objective
- Material evidence
- Result
- Limitations

## Material Engineering Change

May require:

- Scope
- Lifecycle
- Participating agents
- Active skills
- Evidence
- Tests
- Applicable gates
- Conditions
- Missing evidence
- Final decision

## High-Risk or Production Change

May additionally require:

- Deployment evidence
- Security evidence
- Human approval
- Recovery evidence
- Tool execution
- Detailed gate evidence
- Residual risk
- Governance evidence

## Regulated or Governance-Sensitive Change

May require additional traceability according to verified corporate or project requirements.

Do not invent additional audit requirements.

---

# Lifecycle Traceability

Traceability depth must reflect lifecycle.

## Experiment

Capture applicable:

- Objective
- Hypothesis
- Main evidence
- Result
- Limitations
- Next decision

Detailed gate and operational traceability may not be necessary unless risk requires it.

## Prototype / PoC

Capture applicable:

- Objective
- Lifecycle
- Technology
- Participating specialists
- Active skills
- Validation evidence
- Limitations
- Security considerations
- Production migration considerations
- Final conclusion

Do not represent prototype evidence as production evidence.

## MVP

Capture applicable:

- Requirements
- Architecture
- Implementation
- Tests
- Gates
- Deployment
- Risks
- Conditions
- Final decision

## Production

Capture appropriate evidence for:

- Scope
- Architecture
- Implementation
- Tests
- Security
- Code Review
- Deployment
- Performance
- Documentation
- Human governance
- Recovery
- Applicable Quality Gates
- Final engineering decision

Traceability must remain proportional to actual production risk.

---

# Traceability Questions

A material trace should allow an independent reviewer to answer applicable questions.

## Request

```text
What was requested?
```

## Objective

```text
What outcome was required?
```

## Lifecycle

```text
What lifecycle applied?
```

## Requirements

```text
Which requirements were verified?
Which assumptions remained?
```

## Workflow

```text
Which workflow actually executed?
```

## Agent Participation

```text
Which agents actually participated?
Why were those agents selected?
```

## Skills

```text
Which engineering skills were actually applied?
```

## Delegation

```text
Which tasks were delegated?
To which specialist?
Why?
```

## Tools

```text
Which tools actually executed?
Did those tools have side effects?
```

## Evidence

```text
Which evidence supported the findings?
```

## Validation

```text
Which tests or evaluations actually executed?
```

## Findings

```text
What material findings existed?
```

## Quality Gates

```text
Which gates applied?
Which gates passed, became conditional, failed, or lacked evidence?
```

## Human Governance

```text
Was human approval required?
Was approval actually provided?
```

## Risk

```text
What residual risk remained?
Was formal risk treatment required?
```

## Decision

```text
Why was the final engineering decision produced?
```

---

# Traceability Model

A typical material engineering trace may follow:

```text
Request / Objective
        ↓
Requirements + Assumptions
        ↓
Lifecycle + Scope
        ↓
Workflow
        ↓
Participating Agents
        ↓
Active Skills
        ↓
Delegations
        ↓
Tools Executed
        ↓
Evidence
        ↓
Tests / Evaluations
        ↓
Findings
        ↓
Applicable Quality Gates
        ↓
Blockers / Conditions / Missing Evidence
        ↓
Human Governance
        ↓
Residual Risk / Formal Risk Treatment
        ↓
Final Engineering Decision
```

Not every execution requires every node.

Do not create artificial records for non-applicable stages merely to complete the model.

---

# Trace Identifiers

Identifiers may improve traceability when provided by the platform or project.

Possible identifiers include:

- Change ID
- Execution ID
- Trace ID
- Agent Activity ID
- Finding ID
- Feature ID
- Incident ID
- Release ID
- Pull Request ID
- Work Item ID
- Commit
- Repository revision

These identifiers are optional unless a verified process requires them.

Do not fabricate an identifier.

If a relevant identifier is unavailable, use:

```text
NOT AVAILABLE
```

If the identifier does not apply, use:

```text
NOT APPLICABLE
```

---

# Change Identifier

A verified Change ID may represent a business or technical request.

Example format may exist in the project.

Do not impose:

```text
CHG-0001
```

as a required format unless project governance defines it.

A request may exist without a formal Change ID.

---

# Execution Identifier

An Execution ID may identify one execution of:

- Workflow
- Review
- Validation
- Release decision
- Agentic workflow

A single request may have multiple executions.

Examples may include:

- Initial review
- Remediation
- Re-review
- Release validation

Do not invent an Execution ID when the platform does not provide one.

---

# Trace Identifier

A Trace ID may connect related execution activity.

Use a Trace ID only when:

- Platform supports it
- Workflow supports it
- Project governance requires it

Do not generate one solely for documentation completeness unless the actual implementation owns identifier generation.

---

# Agent Activity Identifier

An Agent Activity ID may identify a specific specialist execution.

It is useful when:

- Multiple agent executions occur
- Agent retries occur
- Delegation is material
- Auditability requires individual activity tracking

It is not universally required.

Do not fabricate activity identifiers.

---

# Finding Identifier

A Finding ID may support remediation tracking.

Use existing identifiers from:

- Security tools
- Issue trackers
- SonarQube
- Ethical Hacking
- QA
- Incident systems
- Project tracking

Do not generate a finding identifier merely because a template contains one.

Finding traceability can also use:

- Component
- Evidence
- Severity
- Description
- Source

when no formal identifier exists.

---

# Traceability Relationships

Relationships should reflect actual system behaviour.

Do not assume universal cardinality.

Possible relationships include:

```text
Request
→ one or more executions
```

```text
Execution
→ zero, one, or more workflows
```

```text
Execution
→ one or more participating agents
```

```text
Agent
→ zero or more skills
```

```text
Agent
→ zero or more delegated activities
```

```text
Execution
→ zero or more tool calls
```

```text
Evidence
→ one or more findings
```

```text
Finding
→ zero or more Quality Gates
```

```text
Quality Gate
→ zero or more blockers or conditions
```

```text
Multiple Quality Gates
→ Final Engineering Decision
```

The implementation must not force a relationship that does not match actual execution.

---

# Request Traceability

Record applicable:

- Objective
- User need
- Business objective
- Change type
- Scope
- Target environment
- Lifecycle
- Risk

Possible structure:

```yaml
request:
  reference: "NOT AVAILABLE"
  objective: ""
  change_type: ""
  lifecycle: ""
  target_environment: ""
  scope: []
  risk_level: ""
```

Do not generalize inferred requirements into verified user intent.

---

# Requirements Traceability

Trace:

- Verified requirements
- Acceptance criteria
- Constraints
- Assumptions
- Missing requirements

Possible structure:

```yaml
requirements:
  verified: []
  assumptions: []
  constraints: []
  missing: []
```

For material assumptions record when useful:

```yaml
assumption: ""
evidence: ""
impact_if_incorrect: ""
validation_required: ""
```

---

# Architecture Traceability

When architecture is material, trace applicable:

- Approved architecture
- Technology decision
- ADR
- System boundaries
- Data ownership
- Integration decision
- Deployment architecture
- Prototype-to-production decision

Possible structure:

```yaml
architecture:
  applicability: ""
  evidence: []
  decisions: []
  unresolved_questions: []
```

Solution Architect owns architectural decisions.

Documentation or traceability records must not invent architecture.

---

# Agent Participation Traceability

Record only agents actually participating.

Possible structure:

```yaml
agents:
  - name: ""
    responsibility: ""
    execution_status: ""
    evidence: ""
```

Allowed execution status:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Normally, agents that did not execute should not be listed as participating.

Do not infer agent participation from gate applicability.

---

# Skill Traceability

Record engineering skills when they are actually applied.

Possible structure:

```yaml
skills:
  - name: ""
    applied_by: ""
    purpose: ""
    evidence: ""
```

Possible skills include:

```text
Python Engineering Skill
Java Engineering Skill
Python MCP Engineering Skill
Endesa Corporate Angular Engineering Skill
LLM Engineering Skill
Agentic Systems Engineering Skill
```

Do not report a skill as active merely because the skill file exists.

---

# Delegation Traceability

When delegation materially occurs, trace:

- Delegating agent
- Target agent
- Objective
- Scope
- Evidence provided
- Expected output
- Result
- Failure
- Stopping condition

Possible structure:

```yaml
delegations:
  - from: ""
    to: ""
    objective: ""
    scope: []
    status: ""
    result_reference: ""
```

Do not fabricate delegated activity.

Detect and record circular-delegation protection where material.

---

# Tool Traceability

Record only tools actually executed.

Possible structure:

```yaml
tools:
  - tool: ""
    invoked_by: ""
    purpose: ""
    execution_status: ""
    side_effects: ""
    target_environment: ""
    evidence: ""
```

Allowed execution status:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

For state-changing tools record when relevant:

- Authorization
- Target
- Side effect
- Validation
- Recovery
- Human approval

Do not expose sensitive tool inputs or outputs unnecessarily.

---

# Evidence Traceability

Material findings and decisions should link to supporting evidence.

Possible evidence categories include:

- Repository
- Requirement
- Architecture
- ADR
- API contract
- Test
- CI/CD
- SonarQube
- Security tooling
- Ethical Hacking / Assurance
- Deployment
- Runtime
- Performance
- Documentation
- Tool output
- Human approval

Possible structure:

```yaml
evidence:
  - type: ""
    reference: ""
    classification: ""
    relevance: ""
    limitations: ""
```

Evidence classification:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

Preserve provenance when material.

---

# Test and Evaluation Traceability

Distinguish definition from execution.

Use:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Trace applicable:

- Unit tests
- Integration tests
- Contract tests
- E2E tests
- Regression tests
- Negative tests
- Security-control tests
- Performance tests
- LLM evaluations
- Agentic evaluations

Possible structure:

```yaml
validation:
  unit_tests: ""
  integration_tests: ""
  contract_tests: ""
  end_to_end_tests: ""
  regression_tests: ""
  security_control_tests: ""
  performance_tests: ""
  llm_evaluation: ""
  agentic_evaluation: ""
```

Do not report a test as passed solely because test source exists.

---

# Finding Traceability

A finding should trace applicable:

- Source
- Agent
- Domain
- Component
- Severity
- Evidence
- Issue
- Impact
- Remediation
- Validation
- Status

Possible structure:

```yaml
findings:
  - id: "NOT AVAILABLE"
    source: ""
    agent: ""
    domain: ""
    component: ""
    severity: ""
    evidence: []
    issue: ""
    impact: ""
    remediation: ""
    validation: ""
    status: ""
```

Do not invent Finding IDs.

---

# Finding State

Finding state must reflect the owning process.

Do not impose a universal lifecycle such as:

```text
OPEN
→ MITIGATED
→ VERIFIED
→ CLOSED
```

Possible states may include:

```text
OPEN
IN PROGRESS
REMEDIATION PROPOSED
REMEDIATED
VALIDATION REQUIRED
VERIFIED
ACCEPTED
CLOSED
NOT APPLICABLE
```

Use only states supported by the applicable domain or tracking system.

Important:

```text
REMEDIATION PROPOSED != REMEDIATED
REMEDIATED != VERIFIED
VERIFIED != FORMAL RISK ACCEPTED
```

Do not mark a finding closed without applicable evidence.

---

# Quality Gate Traceability

Use the gate model defined in:

`quality-gates.md`

Possible gates:

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

For each applicable gate trace:

```yaml
gate:
  name: ""
  owner: ""
  applicability: ""
  result: ""
  evidence: []
  blockers: []
  conditions: []
  missing_evidence: []
```

Applicability:

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

Result:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Do not record an unevaluated gate as PASSED.

---

# Blocking Finding Traceability

For each unresolved blocker trace:

```yaml
blocker:
  gate: ""
  domain: ""
  owner: ""
  severity: ""
  evidence: []
  impact: ""
  remediation_required: ""
  validation_required: ""
```

Final decisions must preserve blocking findings.

Do not omit a blocker because other gates passed.

---

# Condition Traceability

Conditional approval requires traceable conditions.

Possible structure:

```yaml
condition:
  description: ""
  responsible_area: ""
  required_action: ""
  evidence_required: ""
  validation: ""
  status: ""
```

Possible status:

```text
OPEN
COMPLETED
NOT VERIFIED
NOT APPLICABLE
```

Do not invent an individual owner.

Prefer responsible areas unless a specific owner is verified.

---

# Missing Evidence Traceability

Missing evidence must remain visible.

Possible structure:

```yaml
missing_evidence:
  item: ""
  expected_source: ""
  impact: ""
  required_validation: ""
```

Impact:

```text
BLOCKING
NON-BLOCKING
INFORMATIONAL
```

Missing evidence must not disappear from the trace simply because a final recommendation was produced.

---

# Conflict Traceability

Use:

`decision-authority.md`

for conflict resolution.

Trace applicable:

- Domains
- Agents
- Disagreement
- Evidence
- Domain authority
- Resolution
- Status

Possible structure:

```yaml
conflict:
  domains: []
  agents: []
  disagreement: ""
  evidence: []
  domain_authority: ""
  resolution: ""
  status: ""
```

Status:

```text
RESOLVED
UNRESOLVED
ESCALATED
```

Do not use a global specialist-authority hierarchy.

---

# Human Approval Traceability

Human approval must be recorded separately from agent recommendations.

Possible structure:

```yaml
human_approval:
  applicability: ""
  status: ""
  authority: ""
  scope: ""
  evidence: ""
```

Applicability:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Status:

```text
GRANTED
DENIED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Do not invent:

- Person
- Role
- Approval
- Scope
- Timestamp

Approval must be supported by evidence.

---

# Formal Risk Treatment Traceability

Formal risk treatment is separate from ordinary engineering approval.

Possible structure:

```yaml
formal_risk_treatment:
  applicability: ""
  status: ""
  authority: ""
  evidence: ""
  residual_risk: ""
```

Possible status:

```text
ACCEPTED
REMEDIATION REQUIRED
TRANSFERRED
AVOIDED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Only record:

```text
ACCEPTED
```

when verified governance evidence confirms formal acceptance.

No engineering agent may invent risk acceptance.

---

# Residual Risk Traceability

Record residual risk when applicable.

Use:

```text
LOW
MEDIUM
HIGH
CRITICAL
NOT DETERMINED
NOT APPLICABLE
```

Trace:

- Risk
- Evidence
- Controls
- Remaining exposure
- Required treatment
- Governance status

Residual risk may exist even when an engineering decision is APPROVE.

Recording residual risk does not constitute accepting that risk.

---

# LLM Traceability

Apply only when material LLM functionality exists.

Trace applicable:

- LLM use case
- Model role
- Prompt/template version when available
- Context sources
- Retrieval
- Grounding evidence
- Structured-output validation
- Tools
- Evaluation
- Security findings
- Performance
- Limitations

Apply:

`LLM Engineering Skill`

Do not log complete sensitive prompts or outputs unnecessarily.

---

# Agentic Traceability

Apply only when material agentic behaviour exists.

Trace applicable:

- Agent responsibilities
- Routing
- Delegation
- Tool permissions
- Tool execution
- State
- Memory
- Human approval
- Stopping conditions
- Errors
- Evaluation
- Security
- Final outcome

Apply:

`Agentic Systems Engineering Skill`

Do not report an agent as participating merely because the agent exists in the system.

---

# Deployment Traceability

When deployment is material, trace applicable:

- Artifact
- Configuration
- Environment
- Pipeline
- Deployment
- Validation
- Database migration
- Rollback
- Recovery
- Operational evidence

Possible execution states:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Planned deployment does not equal successful deployment.

---

# Security Traceability

Security evidence may require restricted visibility.

Trace only what is appropriate for the Decision Log or general trace.

Possible references include:

- Risk Assessment
- Security Annex
- SonarQube
- Dependency analysis
- Ethical Hacking
- Assurance
- Security finding
- Remediation
- Re-check

Do not expose:

- Secrets
- Exploit payloads
- Credential material
- Sensitive vulnerability details

unless the authorized security process explicitly requires it.

---

# Performance Traceability

When performance is material, preserve the evidence classification:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

Trace applicable:

- Performance requirement
- Workload
- Baseline
- Benchmark
- Profiling
- Load evidence
- Bottleneck
- Recommendation
- Validation

Do not report an optimization as improved without before-and-after execution evidence.

---

# Final Decision Traceability

The final engineering decision must use:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Trace:

```yaml
final_decision:
  decision: ""
  decision_owner: "Orchestrator"
  supporting_gates: []
  blockers: []
  conditions: []
  missing_evidence: []
  human_governance: ""
  rationale: ""
```

The final decision must comply with:

- `decision-authority.md`
- `quality-gates.md`

The Orchestrator owns the final engineering decision.

The Orchestrator does not own formal risk acceptance.

---

# Decision Rationale Traceability

The rationale should connect:

```text
Evidence
↓
Findings
↓
Quality Gates
↓
Blockers / Conditions / Missing Evidence
↓
Human Governance
↓
Final Engineering Decision
```

Avoid rationale such as:

```text
Everything looks good.
```

Prefer evidence-based rationale.

Example:

```text
QA Gate PASSED based on executed regression and contract tests.
Security Gate was NOT APPLICABLE to the documentation-only change.
Documentation Gate PASSED after verification against the current API contract.
No blocking finding remains.
Final Decision: APPROVE.
```

---

# Re-Execution and Re-Review Traceability

A request may be reviewed more than once.

Examples:

- Initial assessment
- Remediation
- Re-review
- Post-deployment validation
- Security re-check

When identifiers are available, link related executions.

When no platform identifier exists, preserve the relationship descriptively without inventing an ID.

A new result must not silently replace evidence from an earlier material execution when history is required.

---

# Correction Traceability

When a trace record is corrected, preserve when applicable:

- Original record reference
- Reason for correction
- Changed fields
- Correcting authority
- Evidence
- Timestamp when provided

Do not silently rewrite historical records where governance requires auditability.

Do not invent correction metadata.

---

# Retention

Traceability retention must be based on verified:

- Corporate policy
- Project governance
- Security requirements
- Regulatory requirements
- Platform capabilities
- Data classification

Do not invent:

- Retention duration
- Deletion policy
- Legal requirements
- Archive requirements

When retention requirements cannot be verified, record:

```text
Retention requirement not verified.
```

---

# Access Control

Traceability data may contain sensitive engineering or business information.

Apply access proportional to:

- Data sensitivity
- Security findings
- Operational details
- User data
- Business confidentiality
- Audit need

Use Least Privilege.

Do not assume all traces should be broadly accessible.

---

# Privacy and Data Minimization

Record only information necessary for:

- Engineering decision
- Audit
- Validation
- Operations
- Governance

Avoid unnecessarily recording:

- Personal data
- User content
- Complete prompts
- Complete tool outputs
- Sensitive payloads
- Secrets
- Credentials

Use references or redacted summaries when appropriate.

---

# Traceability Validation

Before considering a material trace complete, verify:

- Required relationships are reconstructable.
- Participants are actual.
- Skills are actually applicable.
- Tool execution is real.
- Evidence references are valid.
- Tests distinguish definition from execution.
- Gate states are accurate.
- Conditions remain visible.
- Missing evidence remains visible.
- Human approval is not fabricated.
- Formal risk acceptance is not fabricated.
- Final decision follows governance.
- Sensitive data is appropriately protected.

---

# Traceability Anti-Patterns

Avoid:

## Mandatory Artificial IDs

Generating fake identifiers merely because the trace model contains identifier fields.

## False Participation

Listing agents that were not invoked.

## False Skill Activation

Listing skills that were available but not applied.

## False Tool Execution

Listing tools that were configured but not executed.

## False Test PASS

Treating test definitions as successful execution.

## False Gate PASS

Treating applicable but unevaluated gates as PASSED.

## Missing Evidence Suppression

Dropping unavailable evidence from the final trace.

## Universal Finding Lifecycle

Forcing every domain finding through the same state model.

## Universal Relationship Cardinality

Forcing one-to-one or one-to-many relationships that do not represent actual execution.

## Human Approval Fabrication

Inventing an approver, approval, role, or timestamp.

## Risk Acceptance Fabrication

Treating engineering approval as formal risk acceptance.

## Sensitive Trace Logging

Persisting unnecessary secrets, credentials, prompts, payloads, or security details.

## Unlimited Retention Assumption

Assuming trace records should be stored forever without verified policy.

## Audit for Audit's Sake

Recording large amounts of low-value information without lifecycle or risk justification.

---

# Minimal Trace Model

For lower-risk material executions, a trace may be:

```yaml
trace_version: "2.0"

context:
  objective: ""
  lifecycle: ""
  scope: []

participating_agents: []

active_skills: []

evidence: []

validation: {}

quality_gates: {}

blocking_findings: []

conditions: []

missing_evidence: []

final_decision:
  decision: ""
  rationale: ""
  decision_owner: "Orchestrator"
```

Do not add fake metadata to make the trace appear more complete.

---

# Extended Trace Model

For higher-risk, production, security-sensitive, regulated, LLM, agentic, or complex executions:

```yaml
trace_version: "2.0"

metadata:
  execution_id: "NOT AVAILABLE"
  parent_execution_id: "NOT APPLICABLE"
  trace_id: "NOT AVAILABLE"
  change_id: "NOT AVAILABLE"
  feature_id: "NOT APPLICABLE"
  incident_id: "NOT APPLICABLE"
  release_id: "NOT APPLICABLE"
  pull_request_id: "NOT AVAILABLE"
  work_item_id: "NOT AVAILABLE"
  timestamp: "NOT AVAILABLE"
  repository: "NOT AVAILABLE"
  branch: "NOT AVAILABLE"
  commit: "NOT AVAILABLE"

context:
  objective: ""
  change_type: ""
  lifecycle: ""
  target_environment: ""
  scope: []
  risk_level: ""

requirements:
  verified: []
  assumptions: []
  constraints: []
  missing: []

architecture:
  applicability: ""
  evidence: []
  decisions: []
  unresolved_questions: []

workflows: []

participating_agents: []

active_skills: []

delegations: []

tools: []

evidence: []

validation:
  unit_tests: "NOT APPLICABLE"
  integration_tests: "NOT APPLICABLE"
  contract_tests: "NOT APPLICABLE"
  end_to_end_tests: "NOT APPLICABLE"
  regression_tests: "NOT APPLICABLE"
  security_control_tests: "NOT APPLICABLE"
  performance_tests: "NOT APPLICABLE"
  llm_evaluation: "NOT APPLICABLE"
  agentic_evaluation: "NOT APPLICABLE"

findings: []

quality_gates:
  architecture_gate: "NOT APPLICABLE"
  backend_gate: "NOT APPLICABLE"
  frontend_gate: "NOT APPLICABLE"
  security_gate: "NOT APPLICABLE"
  qa_gate: "NOT APPLICABLE"
  code_review_gate: "NOT APPLICABLE"
  devops_gate: "NOT APPLICABLE"
  performance_gate: "NOT APPLICABLE"
  documentation_gate: "NOT APPLICABLE"
  llm_gate: "NOT APPLICABLE"
  agentic_gate: "NOT APPLICABLE"

blocking_findings: []

conditions: []

missing_evidence: []

conflicts: []

human_approval:
  applicability: "NOT DETERMINED"
  status: "NOT VERIFIED"
  evidence: "NOT AVAILABLE"

formal_risk_treatment:
  applicability: "NOT DETERMINED"
  status: "NOT VERIFIED"
  evidence: "NOT AVAILABLE"

residual_risk:
  level: "NOT DETERMINED"
  evidence: []
  controls: []
  limitations: []

final_decision:
  decision: ""
  decision_owner: "Orchestrator"
  supporting_gates: []
  blockers: []
  conditions: []
  missing_evidence: []
  rationale: ""
```

Default values are placeholders.

Default values do not represent actual execution results.

---

# Integration Requirements

The Traceability Model should remain compatible with:

```text
decision-log-template.md
decision-authority.md
quality-gates.md
feature-workflow.md
bugfix-workflow.md
security-workflow.md
release-checklist.md
```

When these artifacts evolve, evaluate whether trace fields or vocabularies must also change.

Do not allow governance vocabulary to drift silently.

---

# Definition of Complete Traceability

Traceability is complete for its intended lifecycle and risk when:

- The objective can be identified.
- The lifecycle can be identified.
- The scope can be identified.
- Verified requirements can be distinguished from assumptions.
- Actual workflow execution can be identified where applicable.
- Actual participating agents can be identified.
- Active skills can be identified.
- Material delegation can be reconstructed where applicable.
- Executed tools can be identified where applicable.
- Evidence provenance is available.
- Material tests and evaluations distinguish definition from execution.
- Findings are traceable to evidence.
- Applicable Quality Gates are identifiable.
- Gate states use canonical vocabulary.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Failed gates and blockers remain visible.
- Conditions remain visible.
- Missing evidence remains visible.
- Conflicts are traceable when applicable.
- Domain authority is respected.
- Human approval is traceable when applicable.
- Formal risk treatment is separate from engineering approval.
- Residual risk is explicit when applicable.
- LLM evidence is traceable when material LLM functionality exists.
- Agentic execution is traceable when material agentic behaviour exists.
- Deployment execution is distinguished from deployment planning.
- Performance claims preserve their evidence classification.
- Identifiers are not fabricated.
- Timestamps are not fabricated.
- Participants are not fabricated.
- Tool execution is not fabricated.
- Sensitive information is minimized.
- Retention requirements are evidence-based.
- Final engineering decision is traceable to evidence and applicable Quality Gates.
- An independent reviewer can understand why the decision was produced without requiring the workflow to be re-run.

---

# Goal

Provide lifecycle-appropriate, secure, evidence-based traceability that connects material engineering requests, requirements, workflows, actual agent and skill participation, tool execution, validation, findings, Quality Gates, human governance, residual risk, and final decisions without inventing identifiers, timestamps, execution, approvals, ownership, or formal risk acceptance.