# Decision Log Template

Version: 2.0

---

# Purpose

The Decision Log records the evidence, participants, Quality Gates, conflicts, conditions, missing information, human governance, and final decision associated with a material engineering execution.

It supports:

- Traceability
- Auditability
- Governance review
- Decision transparency
- Release analysis
- Incident analysis
- Continuous improvement
- Historical decision context

A Decision Log should be produced when the lifecycle, risk, governance process, or project requirements justify recording the decision.

Not every low-risk interaction requires a permanent Decision Log.

The required level of detail must reflect:

- Lifecycle
- Scope
- Risk
- Target environment
- Security impact
- Deployment impact
- Regulatory or corporate requirements
- Reversibility
- Business criticality

Use:

`decision-authority.md`

for authority, conflict resolution, human governance, and final decision rules.

Use:

`quality-gates.md`

for gate applicability, gate status, evidence requirements, and gate aggregation.

---

# Logging Principles

Always apply:

- Evidence before assertion
- Actual participation only
- Actual execution only
- Explicit uncertainty
- Domain-specific authority
- Lifecycle-appropriate detail
- Minimum necessary sensitive data
- Traceable final rationale
- No fabricated metadata
- No fabricated approvals
- No fabricated risk acceptance

Mandatory rules:

```text
AGENT DEFINED != AGENT PARTICIPATED
SKILL AVAILABLE != SKILL ACTIVATED
TOOL CONFIGURED != TOOL EXECUTED
TEST DEFINED != TEST EXECUTED
GATE APPLICABLE != GATE EXECUTED
NOT EXECUTED != PASS
NOT AVAILABLE != PASS
HUMAN APPROVAL REQUIRED != HUMAN APPROVAL GRANTED
RESIDUAL RISK RECORDED != FORMAL RISK ACCEPTED
```

---

# Decision Log Integrity

The Decision Log should preserve the decision state that existed when the record was completed.

When the storage platform supports versioning, audit history, append-only storage, or immutable records, use those capabilities according to verified project governance.

This template does not itself guarantee immutability.

Do not claim that a Decision Log is immutable unless the storage mechanism provides supporting evidence.

Corrections should preserve:

- Original record
- Reason for correction
- Corrected information
- Correction authority when required
- Correction timestamp when provided by the platform
- Relationship between original and corrected records

Do not silently rewrite a historical decision.

---

# Sensitive Information

Decision Logs must not contain unnecessary:

- Passwords
- Secrets
- Tokens
- Private keys
- Credential-bearing headers
- Sensitive personal information
- Confidential payloads
- Full security exploit details
- Unredacted sensitive prompts
- Unnecessary tool outputs
- Production credentials

Use references, identifiers, summaries, or approved secure locations instead of embedding sensitive evidence directly.

Example:

```text
Security evidence:
Available in approved restricted security repository.

Secret value:
NOT RECORDED
```

---

# Evidence Classification

Use when applicable:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

## VERIFIED

Direct evidence supports the recorded information.

## PARTIALLY VERIFIED

Some evidence exists, but material information remains unavailable.

## INFERRED

The information is a reasonable interpretation of available evidence but has not been directly confirmed.

## NOT VERIFIED

Evidence is unavailable, contradictory, stale, or insufficient.

## NOT APPLICABLE

The information does not apply to the execution.

Do not record inferred information as verified fact.

---

# Execution Status Vocabulary

For agents, tools, tests, pipelines, evaluations, deployments, and other executable controls use:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Where a definition exists without execution, use:

```text
DEFINED
```

Do not convert:

```text
DEFINED
NOT EXECUTED
NOT AVAILABLE
```

into:

```text
EXECUTED - PASS
```

---

# Gate Result Vocabulary

For Quality Gates use:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Do not use:

```text
PASS
FAIL
NOT APPLICABLE
```

as gate-status aliases when the canonical vocabulary above applies.

---

# Recommendation Vocabulary

For specialist and final recommendations use:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
NOT APPLICABLE
```

`NOT APPLICABLE` may be used for a specialist recommendation only when the specialist domain does not apply.

The final engineering decision must use exactly one of:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

---

# Optional Trace Metadata

Trace metadata must only be recorded when provided by the execution environment, repository, governance process, or authorized user.

Possible metadata includes:

- Execution identifier
- Parent execution identifier
- Trace identifier
- Change identifier
- Feature identifier
- Incident identifier
- Release identifier
- Pull request identifier
- Work-item identifier
- Repository revision
- Branch
- Commit
- Timestamp
- Target environment

Do not fabricate missing identifiers or timestamps.

Use:

```text
NOT AVAILABLE
```

when a field is relevant but unavailable.

Use:

```text
NOT APPLICABLE
```

when the field does not apply.

---

# Decision Log Template

Use this structure for material engineering decisions.

## Record Metadata

```yaml
record_version: "2.0"
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
```

Replace default values only when verified information exists.

Do not invent example values in an actual Decision Log.

---

## Decision Context

```yaml
workflow: ""
objective: ""
change_type: ""
lifecycle: ""
target_environment: ""
scope: []
risk_level: ""
```

Allowed lifecycle values:

```text
Experiment
Prototype / PoC
MVP
Production
Not determined
```

Possible change types include:

```text
FEATURE
BUG FIX
REFACTOR
SECURITY
INFRASTRUCTURE
DOCUMENTATION
PERFORMANCE
LLM
AGENTIC
RELEASE
MIXED
```

Risk level:

```text
LOW
MEDIUM
HIGH
CRITICAL
NOT DETERMINED
NOT APPLICABLE
```

---

## Requirements and Assumptions

```yaml
verified_requirements: []
assumptions: []
constraints: []
missing_requirements: []
```

For every material assumption record when possible:

```yaml
assumption: ""
evidence: ""
impact_if_incorrect: ""
validation_required: ""
```

Do not silently convert assumptions into requirements.

---

## Participating Agents

List only agents actually invoked or materially participating in the execution.

```yaml
participating_agents:
  - agent: ""
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

If a non-executed agent is relevant to explain missing evidence, record that status explicitly.

Do not add every available agent automatically.

---

## Active Skills

List only skills actually applicable and used.

```yaml
active_skills:
  - skill: ""
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

Skill availability does not prove skill activation.

---

## Workflow Participation

```yaml
workflow_execution:
  workflow: ""
  status: ""
  stages_completed: []
  stages_not_executed: []
  limitations: []
```

Allowed status:

```text
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

A workflow definition existing in the repository does not prove that the workflow executed.

---

## Evidence Sources

Record the evidence materially used for the decision.

```yaml
evidence_sources:
  - source_type: ""
    source_reference: ""
    classification: ""
    relevance: ""
    limitations: ""
```

Possible source types include:

- Repository
- Approved requirement
- Architecture decision
- ADR
- API contract
- Test result
- CI/CD result
- SonarQube
- Security tooling
- Ethical Hacking / Assurance
- Deployment evidence
- Runtime evidence
- Performance measurement
- Documentation
- Tool output
- Human approval
- User-provided evidence

Evidence classification:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

Do not embed sensitive evidence when a secure reference is more appropriate.

---

## Tools Executed

Record only tools actually executed.

```yaml
tools_executed:
  - tool: ""
    purpose: ""
    execution_status: ""
    result_summary: ""
    side_effects: ""
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

For state-changing tools also record when applicable:

```yaml
target_environment: ""
authorization_status: ""
validation_status: ""
rollback_or_recovery: ""
```

Do not report a configured tool as executed.

Do not expose sensitive tool inputs or outputs.

---

## Test and Evaluation Evidence

```yaml
test_evidence:
  unit_tests: ""
  integration_tests: ""
  contract_tests: ""
  end_to_end_tests: ""
  regression_tests: ""
  negative_tests: ""
  security_control_tests: ""
  llm_evaluation: ""
  agentic_evaluation: ""
```

Allowed values:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Include supporting evidence when material.

Do not report test existence as test success.

---

## Specialist Findings

Record findings only from specialists that participated or from verified evidence assigned to the appropriate domain.

```yaml
specialist_findings:
  - agent: ""
    domain: ""
    highest_severity: ""
    findings: []
    gate: ""
    recommendation: ""
    evidence: []
    missing_information: []
```

Possible severity values:

```text
CRITICAL
HIGH
MEDIUM
LOW
NONE
NOT DETERMINED
NOT APPLICABLE
```

Gate values:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Recommendation values:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
NOT APPLICABLE
```

Do not invent a specialist finding or recommendation.

---

## Quality Gate Results

Record only gates that were evaluated, applicable, unavailable, or explicitly determined not applicable.

```yaml
quality_gates:
  architecture_gate:
    applicability: ""
    result: ""
    owner: "Solution Architect"
    evidence: []
    conditions: []
    missing_evidence: []

  backend_gate:
    applicability: ""
    result: ""
    owner: "Backend Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  frontend_gate:
    applicability: ""
    result: ""
    owner: "Frontend Systems Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  security_gate:
    applicability: ""
    result: ""
    owner: "Security Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  qa_gate:
    applicability: ""
    result: ""
    owner: "QA Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  code_review_gate:
    applicability: ""
    result: ""
    owner: "Code Reviewer"
    evidence: []
    conditions: []
    missing_evidence: []

  devops_gate:
    applicability: ""
    result: ""
    owner: "DevOps Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  performance_gate:
    applicability: ""
    result: ""
    owner: "Performance Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  documentation_gate:
    applicability: ""
    result: ""
    owner: "Documentation Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  llm_gate:
    applicability: ""
    result: ""
    owner: ""
    evidence: []
    conditions: []
    missing_evidence: []

  agentic_gate:
    applicability: ""
    result: ""
    owner: ""
    evidence: []
    conditions: []
    missing_evidence: []
```

Allowed applicability values:

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

Allowed gate-result values:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

For LLM Gate and Agentic Gate, record the actual responsible engineering workflow or specialist ownership.

Do not invent a standalone gate owner if governance does not define one.

---

## Blocking Findings

Record unresolved blockers.

```yaml
blocking_findings:
  - gate: ""
    domain: ""
    owner: ""
    severity: ""
    finding: ""
    evidence: []
    impact: ""
    required_remediation: ""
    validation_required: ""
```

Do not classify a finding as blocking without evidence and applicable governance.

---

## Conditions

Record non-blocking conditions associated with conditional progression.

```yaml
conditions:
  - condition: ""
    responsible_area: ""
    required_action: ""
    evidence_required: ""
    validation: ""
    status: ""
```

Allowed condition status:

```text
OPEN
COMPLETED
NOT VERIFIED
NOT APPLICABLE
```

Do not use conditions to hide mandatory blockers.

Do not use conditional approval as a substitute for formal risk acceptance.

---

## Missing Evidence

Missing evidence must be a first-class record.

```yaml
missing_evidence:
  - item: ""
    expected_source: ""
    impact: ""
    required_validation: ""
```

Allowed impact:

```text
BLOCKING
NON-BLOCKING
INFORMATIONAL
```

If blocking evidence is unavailable, the final decision normally requires:

```text
NEEDS MORE INFO
```

unless verified governance defines non-execution itself as a blocker.

---

## Conflicts

Record conflicts only when they actually exist.

```yaml
conflicts:
  detected: false
  items: []
```

When conflicts exist:

```yaml
conflicts:
  detected: true
  items:
    - domains: []
      agents: []
      disagreement: ""
      evidence: []
      domain_authority: ""
      resolution: ""
      status: ""
```

Allowed status:

```text
RESOLVED
UNRESOLVED
ESCALATED
```

Conflict resolution must follow:

`decision-authority.md`

Do not write:

```text
Security authority wins.
```

Use domain-specific reasoning instead.

Example:

```text
The unresolved blocker concerns authorization enforcement.
Security Engineer owns security severity and the Security Gate.
The blocker remains unresolved, so the final decision cannot be APPROVE.
```

---

## Human Approval

Record human approval only when it is relevant.

```yaml
human_approval:
  applicability: ""
  status: ""
  authority: ""
  evidence: ""
  limitations: ""
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

- Approver
- Role
- Approval
- Timestamp
- Approval scope

Human approval and formal risk acceptance are not automatically the same event.

---

## Formal Risk Treatment

```yaml
formal_risk_treatment:
  applicability: ""
  status: ""
  authority: ""
  evidence: ""
  residual_risk: ""
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
ACCEPTED
REMEDIATION REQUIRED
TRANSFERRED
AVOIDED
NOT PROVIDED
NOT VERIFIED
NOT APPLICABLE
```

Only use:

```text
ACCEPTED
```

when verified evidence shows that an authorized governance party formally accepted the risk.

No engineering agent or Orchestrator may invent formal risk acceptance.

---

## Risk Summary

Record only risk information supported by evidence.

```yaml
risk_summary:
  overall_risk: ""
  residual_risk: ""
  material_risks: []
  compensating_controls: []
  limitations: []
```

Allowed risk levels:

```text
LOW
MEDIUM
HIGH
CRITICAL
NOT DETERMINED
NOT APPLICABLE
```

Finding counts are optional.

Do not invent counts merely to complete the schema.

If counts are available:

```yaml
finding_counts:
  critical: 0
  high: 0
  medium: 0
  low: 0
```

Record counts only when they can be verified.

---

## Final Engineering Decision

Mandatory for a completed Decision Log.

```yaml
final_engineering_decision:
  decision: ""
  rationale: ""
  decision_owner: "Orchestrator"
  supporting_gates: []
  unresolved_blockers: []
  conditions: []
  missing_evidence: []
```

Allowed decisions:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

The decision must comply with:

- `decision-authority.md`
- `quality-gates.md`

The Orchestrator owns the final engineering decision.

The Orchestrator does not own formal risk acceptance.

---

# Decision Rules

## APPROVE

Use when:

- Applicable mandatory gates pass.
- No critical blocker remains.
- Required evidence is available.
- Required human approval is verified when applicable.
- No unresolved conflict prevents safe delivery.

## CONDITIONAL APPROVAL

Use when:

- No critical blocker remains.
- Mandatory controls are not bypassed.
- Remaining conditions are explicit.
- Responsible areas are identified.
- Required validation is identified.
- Required human approval is satisfied.

## BLOCK

Use when:

- An applicable mandatory gate fails.
- A critical blocker remains.
- Required mandatory control is absent.
- Required human approval is denied.
- Safe progression cannot continue.

## NEEDS MORE INFO

Use when:

- Answer-critical evidence is unavailable.
- Gate applicability cannot be determined.
- Required execution evidence is unavailable.
- Authority is unresolved.
- Specialist conflict cannot be resolved safely.
- Required human-approval status is unavailable.

---

# Decision Rationale

The rationale should explain:

- What was requested
- Which lifecycle applied
- Which evidence was reviewed
- Which agents participated
- Which gates applied
- Which gates failed or became conditional
- Which blockers remained
- Which conditions remained
- Which evidence was missing
- Whether human governance applied
- Why the final decision followed

Avoid vague rationale such as:

```text
No problems found.
```

Prefer evidence-based rationale such as:

```text
QA Gate PASSED based on executed unit, integration, and regression tests.
Security Gate was NOT APPLICABLE because the scoped documentation-only change did not affect authentication, authorization, sensitive data, executable configuration, or security controls.
Documentation Gate PASSED after the API description was validated against the current contract.
No unresolved blocker remains.
```

---

# Required Actions

Required actions may include:

- Blocking remediation
- Conditional follow-up
- Additional validation
- Required documentation
- Human governance
- Missing evidence collection

Use:

```yaml
required_actions:
  - action: ""
    category: ""
    responsible_area: ""
    blocking: false
    required_evidence: ""
    validation: ""
    status: ""
```

Allowed status:

```text
OPEN
COMPLETED
NOT VERIFIED
NOT APPLICABLE
```

Do not invent specific people or owners.

Use responsible areas such as:

- Backend
- Frontend
- Security
- QA
- DevOps
- Architecture
- Performance
- Documentation
- Governance

unless an individual owner is verified.

---

# Traceability Summary

```yaml
traceability:
  request_reference: ""
  workflow_reference: ""
  repository_evidence: []
  architecture_evidence: []
  test_evidence: []
  security_evidence: []
  deployment_evidence: []
  performance_evidence: []
  documentation_evidence: []
  governance_evidence: []
```

Use references actually available.

Do not fabricate file paths, URLs, identifiers, or external records.

---

# Minimal Decision Log Template

Use this form for a low-complexity material decision when a full record is unnecessary.

```yaml
record_version: "2.0"

context:
  objective: ""
  lifecycle: ""
  scope: []
  risk_level: ""

participating_agents: []

active_skills: []

evidence_sources: []

quality_gates: {}

blocking_findings: []

conditions: []

missing_evidence: []

human_approval:
  applicability: "NOT APPLICABLE"
  status: "NOT APPLICABLE"

formal_risk_treatment:
  applicability: "NOT APPLICABLE"
  status: "NOT APPLICABLE"

final_engineering_decision:
  decision: ""
  rationale: ""
  decision_owner: "Orchestrator"
```

Do not add fabricated metadata merely because the minimal template lacks an identifier.

---

# Extended Decision Log Template

Use this form for higher-risk, production, security-sensitive, regulated, complex, or multi-agent decisions.

```yaml
record_version: "2.0"

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
  workflow: ""
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

participating_agents: []

active_skills: []

workflow_execution:
  workflow: ""
  status: ""
  stages_completed: []
  stages_not_executed: []
  limitations: []

evidence_sources: []

tools_executed: []

test_evidence:
  unit_tests: "NOT APPLICABLE"
  integration_tests: "NOT APPLICABLE"
  contract_tests: "NOT APPLICABLE"
  end_to_end_tests: "NOT APPLICABLE"
  regression_tests: "NOT APPLICABLE"
  negative_tests: "NOT APPLICABLE"
  security_control_tests: "NOT APPLICABLE"
  llm_evaluation: "NOT APPLICABLE"
  agentic_evaluation: "NOT APPLICABLE"

specialist_findings: []

quality_gates:
  architecture_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Solution Architect"
    evidence: []
    conditions: []
    missing_evidence: []

  backend_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Backend Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  frontend_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Frontend Systems Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  security_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Security Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  qa_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "QA Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  code_review_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Code Reviewer"
    evidence: []
    conditions: []
    missing_evidence: []

  devops_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "DevOps Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  performance_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Performance Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  documentation_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "Documentation Engineer"
    evidence: []
    conditions: []
    missing_evidence: []

  llm_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "NOT DETERMINED"
    evidence: []
    conditions: []
    missing_evidence: []

  agentic_gate:
    applicability: "NOT DETERMINED"
    result: "NOT EXECUTED"
    owner: "NOT DETERMINED"
    evidence: []
    conditions: []
    missing_evidence: []

blocking_findings: []

conditions: []

missing_evidence: []

conflicts:
  detected: false
  items: []

human_approval:
  applicability: "NOT DETERMINED"
  status: "NOT VERIFIED"
  authority: "NOT AVAILABLE"
  evidence: "NOT AVAILABLE"
  limitations: ""

formal_risk_treatment:
  applicability: "NOT DETERMINED"
  status: "NOT VERIFIED"
  authority: "NOT AVAILABLE"
  evidence: "NOT AVAILABLE"
  residual_risk: "NOT DETERMINED"

risk_summary:
  overall_risk: "NOT DETERMINED"
  residual_risk: "NOT DETERMINED"
  material_risks: []
  compensating_controls: []
  limitations: []

required_actions: []

final_engineering_decision:
  decision: ""
  rationale: ""
  decision_owner: "Orchestrator"
  supporting_gates: []
  unresolved_blockers: []
  conditions: []
  missing_evidence: []

traceability:
  request_reference: ""
  workflow_reference: ""
  repository_evidence: []
  architecture_evidence: []
  test_evidence: []
  security_evidence: []
  deployment_evidence: []
  performance_evidence: []
  documentation_evidence: []
  governance_evidence: []
```

The default values in this template are placeholders.

They do not represent execution results.

---

# Correction Record

When a completed Decision Log requires correction, use an explicit correction record.

```yaml
correction:
  original_record_reference: ""
  reason: ""
  corrected_fields: []
  correction_authority: "NOT AVAILABLE"
  timestamp: "NOT AVAILABLE"
  evidence: []
```

Do not erase the historical record when applicable governance requires preservation.

Do not invent correction authority or timestamp.

---

# Retention and Access

Decision Log retention must follow verified:

- Corporate policy
- Project governance
- Security requirements
- Regulatory requirements
- Platform capabilities
- Data-classification requirements

Do not invent a retention period.

Do not assume indefinite retention.

Access should follow:

- Least Privilege
- Information sensitivity
- Operational need
- Audit requirements

Decision Logs containing sensitive security, operational, or business information may require restricted access.

---

# Decision Log Anti-Patterns

Avoid:

## Fabricated Trace Metadata

Inventing execution IDs, trace IDs, change IDs, timestamps, commits, or release identifiers.

## False Participation

Listing agents that were not invoked.

## False Skill Activation

Listing available skills as active when they were not applied.

## False Tool Execution

Listing configured tools as executed.

## False PASS

Treating NOT EXECUTED or NOT AVAILABLE as successful completion.

## Gate Omission

Excluding an applicable failed or conditional gate from the record.

## Gate Inflation

Recording every possible gate regardless of applicability.

## Universal Authority Hierarchy

Resolving conflict through a fixed specialist ranking.

## Human Approval Fabrication

Inventing an approver, approval, scope, or timestamp.

## Agent Risk Acceptance

Recording formal risk acceptance without authorized governance evidence.

## Finding-Count Fabrication

Creating severity counts that were not actually calculated.

## Sensitive Evidence Exposure

Embedding secrets, credentials, private data, or unnecessary exploit details.

## Planned Work as Completed Work

Recording proposed actions as executed results.

## Silent Historical Rewrite

Changing the original decision without preserving the correction or superseding record.

---

# Definition of a Complete Decision Log

A Decision Log is complete when:

- The decision objective is understood.
- Applicable lifecycle is recorded.
- Scope is explicit.
- Risk level is explicit or marked as not determined.
- Verified requirements are distinguished from assumptions.
- Missing requirements are explicit.
- Only actual participating agents are listed.
- Only applicable active skills are listed.
- Workflow execution status is explicit.
- Evidence sources are recorded.
- Evidence classifications are accurate.
- Only executed tools are recorded as executed.
- Tool side effects are documented when material.
- Test definitions are distinguished from test execution.
- NOT EXECUTED has not been treated as PASS.
- NOT AVAILABLE has not been treated as PASS.
- Specialist findings are not invented.
- Applicable Quality Gates are recorded.
- Irrelevant gates are not represented as PASSED.
- Gate states use the canonical vocabulary.
- Blocking findings are explicit.
- Conditions are explicit.
- Missing evidence is explicit.
- Conflicts are handled according to `decision-authority.md`.
- Gate evaluation is aligned with `quality-gates.md`.
- Human approval applicability is explicit when relevant.
- Human approval is not recorded as granted without evidence.
- Formal risk acceptance has not been invented.
- Residual risk is distinguished from formal risk acceptance.
- Required actions are explicit.
- Responsible areas are not replaced with invented individuals.
- Final decision uses the canonical vocabulary.
- Final rationale identifies the supporting evidence.
- Trace metadata has not been fabricated.
- Sensitive information has not been exposed unnecessarily.
- Retention requirements have not been invented.
- Corrections preserve appropriate historical traceability.
- A reviewer can understand why the final engineering decision was produced.

---

# Goal

Provide an accurate, secure, evidence-based, and reviewable record of each material engineering decision, showing what was evaluated, which agents and skills actually participated, which tools and validations actually executed, which Quality Gates applied, what blockers or conditions remained, whether human governance was required, and why the Orchestrator produced the final decision without fabricating trace metadata, approval, participation, execution, or formal risk acceptance.