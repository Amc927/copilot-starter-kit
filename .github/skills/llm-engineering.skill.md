---
name: LLM Engineering Skill
description: Reusable engineering knowledge for designing, grounding, evaluating, securing, integrating, and operating evidence-based LLM-powered applications, RAG systems, copilots, structured-generation workflows, and AI-assisted software capabilities.
---

# LLM Engineering Skill

## Purpose

This skill provides reusable engineering guidance for designing, implementing, evaluating, securing, and operating applications that contain material Large Language Model functionality.

It applies to:

- AI assistants
- Copilots
- RAG applications
- Classification
- Extraction
- Summarization
- Structured generation
- Natural-language interfaces
- LLM-powered workflows
- Tool-using LLM applications
- AI agents
- Multi-agent systems

This skill applies only when the target solution contains material LLM functionality.

Do not activate it merely because Copilot or another AI assistant was used during software development.

When the target system contains material agentic behaviour such as:

- Dynamic planning
- Delegation
- Autonomous tool selection
- Multi-agent routing
- Persistent agent memory
- Autonomous state-changing actions

also apply:

`Agentic Systems Engineering Skill`

LLM engineering and agentic-system engineering are related but separate concerns.

---

# Core Principle

Use an LLM only when its probabilistic language or reasoning capability provides justified value.

The goal is not to maximize model usage.

The goal is to satisfy the requirement with appropriate:

- Correctness
- Grounding
- Reliability
- Safety
- Security
- Maintainability
- Traceability
- Latency
- Cost
- User experience

Prefer deterministic software when deterministic software is sufficient.

Do not use an LLM for functionality that can be implemented more reliably and simply with:

- Explicit business rules
- Deterministic transformations
- Database queries
- Conventional search
- Validation logic
- Workflow engines
- Standard application code

---

# Evidence-First Rule

Material LLM-system conclusions must be supported by available evidence.

Evidence may include:

- Approved requirements
- Approved architecture
- Repository implementation
- Prompt templates
- Model configuration
- Retrieval configuration
- Knowledge sources
- Tool definitions
- Evaluation datasets
- Evaluation results
- Tests
- Execution evidence
- Security reviews
- Runtime metrics
- Platform documentation
- User feedback when verified

Do not invent:

- Model execution
- Retrieval results
- Citations
- Tool calls
- Evaluation results
- Model quality
- Latency measurements
- Token usage
- Cost
- Security controls
- Grounding evidence

Missing evidence must remain explicit.

---

# Evidence Classification

When useful, classify material conclusions as:

```text
VERIFIED
PARTIALLY VERIFIED
INFERRED
NOT VERIFIED
NOT APPLICABLE
```

## VERIFIED

Direct evidence supports the conclusion.

## PARTIALLY VERIFIED

Some evidence exists, but material details remain unavailable.

## INFERRED

Available evidence suggests the conclusion, but it has not been directly confirmed.

## NOT VERIFIED

Required evidence is unavailable or contradictory.

## NOT APPLICABLE

The concern does not apply to the system.

Never present:

`INFERRED`

or:

`NOT VERIFIED`

as:

`VERIFIED`

---

# Execution Status

For model calls, retrieval, evaluation, tools, and tests use:

```text
PASS
FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Never convert:

```text
NOT EXECUTED
```

or:

```text
NOT AVAILABLE
```

into:

```text
PASS
```

A prompt definition does not prove that the prompt was executed.

An evaluation definition does not prove that evaluation passed.

A configured retrieval system does not prove retrieval quality.

---

# Lifecycle Awareness

LLM engineering depth must reflect the approved lifecycle.

Supported lifecycle values:

- Experiment
- Prototype / PoC
- MVP
- Production

## Experiment

Prioritize:

- Technical feasibility
- Model-capability validation
- Basic grounding
- Representative examples
- Explicit limitations
- Safe data handling

Do not require production-scale evaluation without justification.

## Prototype / PoC

Prioritize:

- Use-case validation
- Prompt behaviour
- Retrieval feasibility
- Structured-output feasibility
- Representative evaluation cases
- Failure modes
- Security limitations
- Cost and latency awareness

A successful PoC does not prove production readiness.

## MVP

Evaluate:

- Repeatable evaluation
- Grounding
- Error handling
- Structured-output reliability
- Retrieval quality
- Security
- Cost
- Latency
- Regression protection
- User-facing limitations

## Production

Require appropriate evidence for:

- Model suitability
- Prompt quality
- Grounding
- Retrieval quality
- Evaluation coverage
- Security controls
- Sensitive-data handling
- Output validation
- Tool controls when applicable
- Failure handling
- Observability
- Regression evaluation
- Cost
- Latency
- Operational support

Do not apply experiment-level evidence as proof of production quality.

---

# LLM Applicability Decision

Before introducing an LLM, determine whether the requirement actually needs one.

Ask:

- Does the requirement involve natural-language understanding?
- Does it require generation?
- Does it require semantic interpretation?
- Does it require extraction from variable unstructured content?
- Does it require summarization?
- Does it require semantic retrieval?
- Does it require reasoning over variable context?
- Can deterministic software solve the requirement more safely?
- Can conventional search solve it?
- Can rules or templates solve it?
- Is model variability acceptable?
- Is the additional latency justified?
- Is the additional cost justified?
- Can the system handle model failure?

Use the simplest reliable solution.

Do not introduce an LLM because AI capability is available.

---

# LLM System Boundary

Clearly separate applicable system concerns.

A typical LLM system may contain:

```text
User / Application
        ↓
Trusted Instructions
        ↓
Application Logic
        ↓
Context Assembly
        ↓
Model
        ↓
Output Validation
        ↓
Application Behaviour
```

Optional capabilities may include:

```text
Retrieval
Tools
Memory
Agentic orchestration
Human approval
```

These capabilities are not mandatory for every LLM application.

Do not combine responsibilities merely because the model can perform them.

---

# Trusted and Untrusted Inputs

Distinguish trust levels explicitly.

Potentially trusted context may include:

- System instructions
- Approved application configuration
- Verified application state
- Approved policy

Potentially untrusted context may include:

- User input
- Retrieved documents
- Web content
- Uploaded files
- Emails
- External APIs
- Tool output
- Model-generated content
- Persistent memory derived from user or external content

Untrusted content must remain data.

It must not automatically become authoritative instructions.

---

# Instruction Hierarchy

Design prompts so trusted instructions remain clearly separated from untrusted content.

Material instructions should define:

- Objective
- Scope
- Constraints
- Available context
- Expected behaviour
- Output format
- Failure behaviour

Do not rely on natural-language prompt wording as the sole enforcement mechanism for:

- Authentication
- Authorization
- Tool permissions
- Data access
- Production changes
- Security policy

Enforce critical controls outside the model whenever practical.

---

# Prompt Engineering

Prompts should be:

- Explicit
- Structured
- Focused
- Maintainable
- Testable
- Versionable where material
- Clear about uncertainty
- Clear about expected output

Avoid:

- Contradictory instructions
- Hidden assumptions
- Excessive unrelated context
- Unnecessary repetition
- Sensitive values
- Security controls implemented only through wording

Do not describe an LLM prompt as deterministic merely because it is highly structured.

LLM output remains probabilistic unless deterministic external controls constrain the relevant behaviour.

---

# Prompt Structure

A useful prompt structure may contain:

```text
Objective

Context

Trusted Instructions

Task

Constraints

Output Requirements

Failure Behaviour
```

Use only sections that improve the task.

Do not make prompts unnecessarily long to satisfy a template.

---

# Prompt Versioning

Version material prompts when changes may affect:

- User-visible behaviour
- Structured outputs
- Retrieval
- Tools
- Security
- Evaluation
- Business decisions

Prompt changes should be evaluated like other behaviour changes.

When repository conventions exist, follow them.

Do not invent a mandatory versioning system.

---

# Few-Shot Examples

Use examples when they materially improve behaviour.

Examples should:

- Demonstrate required output
- Cover meaningful ambiguity
- Avoid secrets
- Avoid confidential production data unless explicitly approved
- Avoid examples that accidentally redefine general rules

Do not overfit the prompt to a small set of examples.

Include negative or boundary examples when useful.

---

# Context Engineering

Context quality depends on more than context volume.

Evaluate:

- Relevance
- Freshness
- Authority
- Provenance
- Completeness
- Duplication
- Ordering
- Sensitivity
- Token cost
- Trust level

Include only context that contributes materially to the task.

Do not remove required context merely to reduce token usage.

---

# Context Provenance

For material decisions, preserve the source of important context where possible.

Possible provenance includes:

- Repository
- Approved documentation
- Database
- Enterprise search
- User input
- External API
- Retrieval index
- Tool result
- Persistent memory

Do not treat all context sources as equally authoritative.

When sources conflict, identify the conflict.

---

# Context Freshness

Determine whether retrieved or injected context is current enough for the task.

Evaluate:

- Source date
- Update frequency
- Version
- Repository revision
- Document status
- Cache age
- Superseding information

Do not present stale knowledge as current when freshness materially affects the answer.

---

# Context Size

More context does not automatically improve quality.

Excess context may increase:

- Latency
- Cost
- Noise
- Conflicting instructions
- Prompt-injection surface
- Retrieval dilution

Prefer the minimum relevant context sufficient for the task.

When large context is required, consider structured filtering or staged retrieval.

---

# Context Deduplication

Avoid repeatedly injecting equivalent information.

Deduplicate context where this:

- Reduces noise
- Reduces cost
- Improves clarity
- Does not remove meaningful distinctions

Do not deduplicate sources that differ materially in authority, version, or meaning.

---

# Context Poisoning

Treat external and retrieved content as potentially hostile.

External content must not:

- Redefine trusted instructions
- Change tool permissions
- Grant itself authority
- Disable security controls
- Cause secret disclosure
- Trigger unauthorized actions

Context poisoning is primarily a security concern and must involve Security Engineer when material.

---

# Model Selection

Select model capabilities according to verified requirements.

Evaluate applicable:

- Task type
- Required reasoning
- Input modality
- Output modality
- Context requirements
- Structured-output capability
- Tool-calling requirements
- Quality
- Latency
- Cost
- Supported platform
- Data-handling requirements
- Security requirements
- Operational constraints

Do not select a model solely because it is newer, larger, or more capable.

Do not invent corporate model requirements.

Prefer the least costly and complex model that satisfies verified quality and capability requirements.

---

# Model Configuration

Configure model behaviour according to the task.

Possible configuration may include:

- Temperature
- Output length
- Structured-output schema
- Tool availability
- Response format
- Stop conditions
- Model-specific options

Do not copy configuration blindly between use cases.

Do not invent an optimal temperature or parameter without evaluation.

When deterministic validation is required, use external validation rather than relying solely on model configuration.

---

# Structured Outputs

Prefer structured output when downstream software must consume model results.

Possible formats include:

- JSON
- Typed schema
- Enumerated decision
- Structured record

A schema should define:

- Required fields
- Optional fields
- Types
- Enumerations
- Nullable behaviour
- Validation rules

Validate structured output before use.

Do not assume syntactically valid JSON is semantically correct.

For human-facing results, structured Markdown may be more appropriate than JSON.

Use the format that best fits the consumer.

---

# Output Validation

Treat model output as untrusted data.

Validate applicable:

- Schema
- Type
- Required fields
- Enumeration
- Business rules
- References
- Citations
- Identifiers
- URLs
- Commands
- Tool arguments
- Data sensitivity

Do not directly execute model-generated code, commands, URLs, queries, or state-changing actions without applicable validation and authorization.

---

# Grounding

Use grounding when model knowledge alone is insufficient for the task.

Potential grounding sources include:

- Enterprise knowledge
- Repository code
- Approved documentation
- Databases
- APIs
- Search
- User-provided content
- Verified tool output

Prefer authoritative and current sources.

Do not require retrieval when the necessary trusted context is already available.

Do not retrieve additional content solely because retrieval infrastructure exists.

---

# Retrieval-Augmented Generation

Use RAG when the task requires contextual knowledge not reliably contained in the model input or model knowledge.

A typical RAG flow is:

```text
User request
      ↓
Query understanding
      ↓
Retrieval
      ↓
Permission filtering
      ↓
Relevance filtering / ranking
      ↓
Context assembly
      ↓
Generation
      ↓
Evidence / citation validation
```

Not every implementation requires every stage.

---

# Retrieval Security

Retrieval must respect:

- Authentication
- Authorization
- Source permissions
- Tenant or project boundaries
- Sensitive-data controls
- Least Privilege

An LLM must not receive information that the requesting user or application is not authorized to access.

Retrieval filtering after unauthorized data has already been exposed to the model may be insufficient.

Enforce authorization before sensitive context reaches the model.

---

# Retrieval Quality

Evaluate:

- Relevant-document retrieval
- Irrelevant-document retrieval
- Missing-document behaviour
- Ranking
- Metadata filters
- Source freshness
- Permission filters
- Duplicate results
- Conflicting sources

Retrieval quality must be evaluated independently from generation quality when possible.

A poor answer may originate from:

- Retrieval failure
- Context-selection failure
- Model-generation failure
- Citation failure

Identify the actual layer before remediation.

---

# Chunking

Chunking strategy should reflect source structure and retrieval needs.

Evaluate:

- Document structure
- Semantic boundaries
- Chunk size
- Overlap
- Metadata
- Context preservation
- Retrieval granularity

Do not apply a universal chunk size without evaluation.

Preserve meaningful structures such as:

- Headings
- Sections
- Tables where relevant
- Code blocks
- Entity boundaries

when they materially affect retrieval quality.

---

# Retrieval Metadata

Use metadata when it improves:

- Filtering
- Ranking
- Freshness
- Access control
- Provenance
- Citation

Possible metadata may include:

- Source
- Document identifier
- Version
- Date
- Owner when verified
- Access scope
- Section
- Repository path

Do not invent metadata.

---

# No-Result Behaviour

When retrieval returns insufficient evidence:

- Do not fabricate missing knowledge.
- Explain that evidence is unavailable when appropriate.
- Request additional information when required.
- Use NEEDS MORE INFO for answer-critical missing evidence.

An empty retrieval result is not evidence that the requested information does not exist.

---

# Conflicting Sources

When sources conflict:

1. Identify the conflict.
2. Compare authority.
3. Compare freshness.
4. Compare scope.
5. Prefer the applicable authoritative source when determinable.
6. Report unresolved conflict when necessary.

Do not silently merge incompatible claims.

---

# Citations and Evidence

When applications expose source-backed answers, citations should map the material claim to actual evidence.

Evaluate:

- Citation exists
- Citation resolves to the claimed source
- Source supports the claim
- Citation is sufficiently specific
- Source permissions are preserved

Do not invent citations.

Do not cite a source that does not support the statement.

Citation correctness should be separately evaluated when citations are a product requirement.

---

# Tool Calling

Use tools when they provide required capabilities or evidence.

Examples:

- Search
- Data retrieval
- Calculation
- File access
- API actions
- Business-system actions

Tool use must be justified by the task.

Do not call a tool merely because it is available.

Do not rely on model memory when fresh authoritative evidence is required.

---

# Tool Governance

When an LLM selects or invokes tools, also apply applicable guidance from:

`Agentic Systems Engineering Skill`

Especially for:

- Tool permissions
- Side effects
- Authentication
- Authorization
- Idempotency
- Destructive actions
- Human approval
- Command execution
- Filesystem access
- Database access
- Network access

LLM Engineering Skill does not duplicate the complete agentic tool-governance model.

---

# Tool Selection

Evaluate:

- Was a tool necessary?
- Was the correct tool selected?
- Were arguments valid?
- Was the tool authorized?
- Were side effects appropriate?
- Was the result verified?
- Was sensitive information protected?

Tool-selection quality should be included in evaluation when material.

---

# Tool Output

Tool output is untrusted data unless explicitly verified.

Tool output may contain:

- Errors
- Partial data
- Stale data
- Prompt injection
- Malformed structures
- Sensitive information

Validate material outputs before using them for decisions or actions.

Do not allow tool output to override trusted instructions.

---

# LLM and Agentic Separation

An LLM application is not automatically an agentic system.

Examples that may remain non-agentic:

- Classification
- Extraction
- Summarization
- Translation
- Structured generation
- Single-step RAG
- Semantic search assistance

Agentic characteristics may include:

- Planning
- Iterative reasoning toward an objective
- Delegation
- Dynamic tool selection
- Autonomous retries
- Multi-agent coordination
- Persistent action-oriented state

When these characteristics are material, also apply:

`Agentic Systems Engineering Skill`

Do not duplicate agentic routing, delegation, memory, and authority rules here.

---

# AI and LLM Security

LLM security must involve Security Engineer when material.

Evaluate applicable:

- Direct prompt injection
- Indirect prompt injection
- Context poisoning
- Retrieval poisoning
- Sensitive-data leakage
- Excessive context exposure
- Tool abuse
- Model-output trust
- Data exfiltration
- Authorization bypass
- Excessive agency
- Insecure memory
- Cross-user data exposure

Treat all external content as untrusted.

Prompt wording alone is not an adequate security control for privileged operations.

---

# Sensitive Data

Evaluate whether sensitive information may enter:

- Prompts
- Context
- Retrieval
- Model input
- Model output
- Tool input
- Tool output
- Memory
- Logs
- Traces
- Evaluation datasets

Apply data minimization.

Do not include secrets unnecessarily.

Do not persist sensitive prompts or outputs merely for debugging convenience.

Use approved platform and project requirements for data handling.

Do not invent retention requirements.

---

# Hallucination Management

Hallucination cannot be eliminated solely through prompting.

Use applicable controls:

```text
Ground
↓
Constrain
↓
Validate
↓
Cite
↓
Abstain when evidence is insufficient
```

Controls may include:

- Retrieval
- Tool verification
- Structured outputs
- Schema validation
- Business-rule validation
- Citation validation
- Source restrictions
- Human review
- Explicit uncertainty
- Missing-information handling

Do not rely on model confidence as proof of correctness.

---

# Abstention

The system should be able to avoid unsupported claims.

Use abstention or NEEDS MORE INFO when:

- Required evidence is missing
- Sources conflict materially
- Retrieval fails
- Requested certainty exceeds available evidence
- Tool result is unavailable
- Required authorization prevents access

Abstention is preferable to confident fabrication.

---

# Evaluation Principles

LLM quality must be evaluated using representative tasks.

Evaluation should measure the behaviour material to the use case.

Possible dimensions include:

- Correctness
- Grounding
- Relevance
- Completeness
- Instruction following
- Structured-output validity
- Retrieval quality
- Citation correctness
- Safety
- Security
- Tool-selection accuracy
- Tool-argument accuracy
- Appropriate abstention
- Refusal behaviour
- Consistency
- Latency
- Cost

Do not require every metric for every use case.

---

# Evaluation Levels

Use applicable evaluation levels.

## Unit Evaluation

Evaluate deterministic components such as:

- Parsers
- Schema validation
- Retrieval filters
- Prompt assembly
- Post-processing
- Business validation

## Model Evaluation

Evaluate model behaviour on representative inputs.

Examples:

- Extraction quality
- Classification quality
- Grounded-answer quality
- Structured-output validity

## Retrieval Evaluation

Evaluate:

- Recall of relevant evidence
- Ranking
- Precision
- Permissions
- Freshness
- No-result behaviour

## Integration Evaluation

Evaluate:

- Model plus retrieval
- Model plus tools
- Model plus application validation
- Error handling

## Human Evaluation

Use when quality requires human judgement.

Examples:

- Usefulness
- Clarity
- Nuanced correctness
- Business acceptability

Define evaluation criteria to reduce reviewer inconsistency.

## Production Evaluation

When appropriate, evaluate verified runtime evidence such as:

- Failure rate
- Latency
- User feedback
- Retrieval failures
- Structured-output failures
- Tool failures
- Abstention frequency

Do not expose sensitive production data unnecessarily.

## Security Evaluation

Coordinate with Security Engineer.

Evaluate applicable:

- Prompt injection
- Indirect prompt injection
- Context poisoning
- Sensitive-data leakage
- Tool abuse
- Authorization bypass

---

# Evaluation Dataset

Build representative evaluation datasets.

Include applicable:

- Normal cases
- Ambiguous cases
- Edge cases
- Invalid input
- Missing context
- Conflicting context
- No retrieval result
- Stale sources
- Long context
- Structured-output edge cases
- Tool errors
- Security cases
- Multilingual input when supported
- Realistic domain terminology

Include examples of expected abstention when appropriate.

Synthetic evaluation data must be identified as synthetic.

Do not include production secrets or unnecessary sensitive data.

---

# Evaluation Ground Truth

When a task has objective ground truth, define it explicitly.

Examples:

- Expected classification
- Expected extracted fields
- Expected calculation
- Expected cited source
- Expected structured output

When ground truth is subjective:

- Define evaluation rubric.
- Define acceptable ranges or criteria.
- Consider multiple reviewers when justified.

Do not create false precision for subjective evaluation.

---

# Regression Evaluation

Prompt, model, retrieval, tooling, or context changes may create regressions.

When material changes occur:

1. Preserve an evaluation baseline when practical.
2. Re-run relevant evaluation scenarios.
3. Compare results.
4. Identify improvements and regressions.
5. Investigate changed failure modes.

Do not report improvement solely because selected examples improved.

Evaluate the representative dataset.

---

# Evaluation Evidence

Distinguish:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

An evaluation dataset existing does not prove the current system passed it.

Do not report production readiness from unexecuted evaluations.

---

# Consistency and Variability

LLM outputs are probabilistic.

Evaluate consistency where repeatability matters.

Possible techniques include:

- Repeated execution
- Structured outputs
- Lower-variance configuration when appropriate
- Post-validation
- Deterministic business rules outside the model

Do not promise identical output across executions unless deterministic external controls make that property true.

---

# Model Output Trust

Never treat model output as inherently authoritative.

Model output may contain:

- Incorrect facts
- Invalid identifiers
- Unsafe recommendations
- Invalid structured data
- Fabricated citations
- Malformed commands
- Unsupported assumptions

Validate according to downstream risk.

Higher-risk uses require stronger controls.

---

# Human-in-the-Loop

Human review should be applied according to:

- Impact
- Reversibility
- Uncertainty
- Authority
- Security
- Regulatory requirements
- Business risk

Consider human review for:

- High-impact decisions
- Irreversible actions
- Sensitive communications
- Formal approvals
- Critical ambiguity
- Material financial outcomes
- Production changes
- Legal or compliance-sensitive results

Do not require human review for every low-risk generation task without justification.

---

# Failure Handling

Define expected behaviour for:

- Model unavailable
- Model timeout
- Rate limit
- Invalid structured output
- Retrieval failure
- Empty retrieval
- Conflicting evidence
- Tool failure
- Context limit
- Unsafe output
- Evaluation failure

Fallback must not silently reduce required security or accuracy.

Possible safe outcomes include:

- Retry when appropriate
- Use deterministic fallback
- Request more information
- Return partial supported result
- Abstain
- Escalate to human review

Do not retry indefinitely.

---

# Retry Strategy

Retries should be:

- Bounded
- Appropriate to the error
- Cost-aware
- Latency-aware
- Safe

Do not retry:

- Invalid deterministic input without correction
- Authorization failure without changed authorization
- Human rejection
- A repeated security-policy violation

For probabilistic retry, evaluate whether a retry actually improves product quality or merely adds cost.

---

# Observability

LLM systems should expose enough evidence to diagnose material behaviour according to lifecycle and risk.

Consider recording when supported:

- Model invocation
- Model identifier or deployment
- Prompt/template version
- Retrieval execution
- Retrieval source references
- Tool invocation
- Structured-output validation
- Errors
- Latency
- Token usage when available
- Cost evidence when available
- Evaluation result
- Abstention
- Human approval where applicable

Do not fabricate unavailable telemetry.

Do not log sensitive prompt or response content unnecessarily.

---

# Privacy-Aware Observability

Before logging model inputs or outputs, evaluate:

- Sensitive data
- Personal data
- Secrets
- Confidential information
- Retention
- Access control
- Debugging value

Prefer metadata over full content when full content is unnecessary.

Redaction must preserve sufficient diagnostic value without exposing sensitive information.

---

# Performance

Coordinate material LLM performance analysis with Performance Engineer.

Evaluate applicable:

- End-to-end latency
- Model latency
- Retrieval latency
- Tool latency
- Number of model calls
- Context size
- Output size
- Streaming
- User-perceived latency
- Token usage
- Cost

Do not reduce grounding, validation, or security solely to reduce latency.

Do not invent performance or cost targets.

---

# Cost Awareness

LLM cost may depend on:

- Model
- Input size
- Output size
- Number of calls
- Retrieval
- Tool calls
- Retry behaviour
- Agentic steps

Evaluate cost only when relevant to the use case.

Do not claim exact cost without verified pricing and usage evidence.

Possible optimization areas include:

- Context reduction
- Model selection
- Call reduction
- Caching when safe and correct
- Output constraints
- Retrieval improvements

Cost optimization must not materially degrade required quality.

---

# Caching

Caching may apply to:

- Retrieval
- Embeddings
- Deterministic preprocessing
- Stable responses
- Tool results
- Context assembly

Before caching evaluate:

- Freshness
- User scope
- Authorization
- Sensitive data
- Invalidation
- Memory/storage cost
- Correctness

Do not cache user-specific or sensitive model results across unauthorized boundaries.

---

# Model and Prompt Changes

Treat material changes to:

- Model
- Model version
- Deployment
- Prompt
- RAG
- Chunking
- Embeddings
- Ranking
- Tool selection
- Structured-output schema

as potential behavioural changes.

Evaluate regression impact.

Do not assume a newer model automatically improves the application.

---

# Deployment and Operations

Coordinate with DevOps Engineer.

Document and evaluate applicable:

- Model endpoint
- Configuration
- Authentication
- Secrets
- Environment
- Rate limits
- Timeout
- Retry
- Observability
- Failover when required
- Quotas
- Deployment differences

Do not expose provider credentials in source code or documentation.

Do not invent production deployment procedures.

---

# Documentation

Coordinate with Documentation Engineer.

Document applicable:

- LLM use case
- Model role
- Context flow
- Retrieval
- Tools
- Structured outputs
- Evaluation
- Security
- Failure behaviour
- Limitations
- Cost considerations
- Operational requirements

Do not describe probabilistic output as guaranteed behaviour.

Do not document proposed controls as implemented controls without evidence.

---

# Common Anti-Patterns

Detect and avoid when materially relevant.

## LLM Everywhere

Using an LLM for deterministic functionality that conventional software handles better.

## Prompt-Only Security

Using natural-language instructions as the sole control for privileged behaviour.

## Context Dumping

Sending all available information to the model regardless of relevance.

## Blind RAG

Retrieving content without evaluating relevance, permissions, freshness, or quality.

## Trusting Model Output

Using generated values directly in high-risk operations without validation.

## Retrieval After Authorization Failure

Retrieving unauthorized sensitive data and attempting to filter it only after model exposure.

## Hallucinated Citations

Generating references that do not map to supporting evidence.

## Evaluation by Anecdote

Approving model behaviour after testing only a few convenient examples.

## Benchmark Overfitting

Optimizing for an evaluation dataset while degrading realistic behaviour.

## Unbounded Retry

Repeatedly calling the model until a desirable answer appears.

## Hidden Model Dependency

Critical business behaviour depends on model output without appropriate validation or documented limitations.

## Stale Context

Using outdated or superseded evidence as current truth.

## Sensitive Prompt Logging

Persisting complete prompts or outputs containing sensitive information without justification.

## Model Upgrade Without Regression Evaluation

Changing model or deployment and assuming backward-compatible behaviour.

---

# Finding Classification

Use:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

## CRITICAL

Use for a demonstrated or strongly evidenced condition capable of causing severe unauthorized action, critical data exposure, critical business failure, or unsafe high-impact output.

Typical recommendation:

`BLOCK`

## HIGH

Use for a material weakness with realistic potential for significant incorrect behaviour, security exposure, or business impact.

Possible recommendation:

- BLOCK
- CONDITIONAL APPROVAL

## MEDIUM

Use for a meaningful weakness that does not create a critical blocker but requires remediation or explicit treatment.

Typical recommendation:

`CONDITIONAL APPROVAL`

## LOW

Use for lower-impact improvements.

Typical recommendation:

`APPROVE`

with follow-up where appropriate.

Severity must reflect evidence, use-case impact, and lifecycle.

---

# LLM Blocking Rules

Recommend BLOCK when an applicable unresolved condition exists, such as:

- Critical sensitive-data leakage
- Critical authorization bypass through LLM behaviour
- Critical prompt injection enables privileged action
- Model output directly controls a critical operation without required validation
- Retrieval exposes data outside authorized scope
- Critical fabricated output can cause severe business or operational harm
- Required production evaluation fails critically
- Required human approval can be bypassed
- Mandatory security control is absent
- Critical unsafe tool use exists

Do not block solely because model output can vary.

Variability must be assessed according to actual product requirements and risk.

---

# Conditional Approval

Use CONDITIONAL APPROVAL when:

- No critical blocker remains
- Remaining findings are non-critical
- Conditions are explicit
- Required evaluation is clear
- Required remediation is clear
- Residual LLM risk is understood

For each condition identify:

- Required action
- Responsible specialist
- Evaluation or validation required

---

# Needs More Info

Use NEEDS MORE INFO when answer-critical evidence is unavailable.

Examples:

- Required model capability unknown
- Data sensitivity unknown
- Grounding source unknown
- Retrieval permissions unknown
- Evaluation results unavailable
- Performance requirement unknown
- Cost requirement unknown
- Tool authority unknown
- Human-review requirement unknown

Do not invent missing information.

---

# LLM Engineering Process

Follow this sequence.

## 1. Establish Objective

Determine:

- User need
- Business objective
- Lifecycle
- Expected output
- Risk

## 2. Validate LLM Need

Determine whether an LLM is justified or deterministic software is sufficient.

## 3. Define System Boundary

Identify:

- Application
- LLM
- Context
- Retrieval
- Tools
- Human interaction
- Downstream systems

## 4. Identify Trust Boundaries

Classify:

- Trusted instructions
- User input
- Retrieved content
- Tool output
- Memory

## 5. Select Model Capabilities

Evaluate:

- Quality
- Modality
- Context
- Structured output
- Tools
- Latency
- Cost
- Data handling

## 6. Design Context and Prompt

Define:

- Trusted instructions
- Task
- Relevant context
- Output requirements
- Failure behaviour

## 7. Design Grounding

When required define:

- Sources
- Retrieval
- Permissions
- Ranking
- Freshness
- Citations
- No-result behaviour

## 8. Define Output Validation

Define schemas and business validation appropriate to downstream risk.

## 9. Define Security Controls

Coordinate with Security Engineer.

## 10. Define Evaluation

Create representative evaluation scenarios and required quality criteria.

## 11. Define Observability

Identify necessary execution, retrieval, tool, error, latency, and evaluation evidence.

## 12. Validate

Execute relevant evaluations when possible.

## 13. Produce Recommendation

Use exactly one:

- APPROVE
- CONDITIONAL APPROVAL
- BLOCK
- NEEDS MORE INFO

---

# LLM Gate

Use:

```text
PASSED
CONDITIONAL
FAILED
```

## PASSED

Use when:

- Applicable requirements are satisfied.
- Required evaluation evidence is available.
- No critical LLM blocker remains.
- Required grounding and validation are adequate.
- Residual risk is appropriate to the lifecycle.

## CONDITIONAL

Use when:

- No critical blocker remains.
- Remaining issues are non-critical.
- Conditions are explicit.
- Required evaluation or remediation is clear.

## FAILED

Use when:

- Critical unsafe behaviour remains.
- Mandatory evaluation fails critically.
- Critical grounding or authorization failure exists.
- Required validation for a critical workflow is absent.

---

# Output Format

## Executive Summary

Provide the overall LLM-system assessment.

## LLM Applicability

Report:

- LLM required: YES / NO / NOT DETERMINED
- Lifecycle
- Justification
- Deterministic alternatives considered

## Use Case

Describe:

- User objective
- Business objective
- Expected model role
- Failure impact

## System Boundary

Describe:

- Application
- Model
- Context
- Retrieval
- Tools
- Human controls
- External systems

## Model Requirements

Report:

- Required capabilities
- Context needs
- Structured-output needs
- Tool needs
- Performance needs
- Cost constraints
- Data constraints

Do not invent a mandatory model.

## Prompt and Context

Report:

- Trusted instructions
- Context sources
- Trust boundaries
- Freshness requirements
- Sensitive-data considerations

## Grounding and RAG

When applicable report:

- Sources
- Retrieval strategy
- Permissions
- Ranking
- Metadata
- Citation behaviour
- No-result behaviour
- Conflicting-source behaviour

## Structured Output

Report:

- Format
- Schema
- Validation
- Failure behaviour

## Tool Use

When applicable report:

- Tools
- Purpose
- Validation
- Agentic Systems Engineering Skill applicability

## Security

Report LLM-specific concerns requiring Security Engineer review.

## Evaluation

Report:

- Dataset
- Evaluation levels
- Metrics
- Security cases
- Regression strategy

## Evaluation Evidence

Use applicable:

```text
DEFINED
EXECUTED - PASS
EXECUTED - FAIL
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

## Observability

Report applicable:

- Model invocation
- Retrieval
- Tools
- Errors
- Latency
- Usage
- Evaluation evidence

## Performance and Cost

Report verified:

- Latency
- Context size
- Model calls
- Tool calls
- Usage
- Cost

Do not invent metrics.

## Findings

For each material finding report:

- Severity
- Component
- Evidence
- Issue
- Impact
- Required remediation
- Responsible specialist
- Validation method

## Conditions

List outstanding non-blocking remediation.

## Missing Information

List unavailable evidence.

## LLM Gate

Exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## LLM Recommendation

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

- Validate whether an LLM is actually required.
- Prefer deterministic software when sufficient.
- Consider lifecycle and risk.
- Distinguish trusted instructions from untrusted content.
- Treat external and retrieved content as untrusted.
- Ground material factual output when required.
- Respect retrieval authorization.
- Validate model output according to downstream risk.
- Use structured outputs when appropriate.
- Define no-result and insufficient-evidence behaviour.
- Evaluate representative scenarios.
- Include failure cases in evaluation.
- Distinguish defined evaluations from executed evaluations.
- Distinguish NOT EXECUTED from PASS.
- Coordinate security with Security Engineer.
- Apply Agentic Systems Engineering Skill when material agentic behaviour exists.
- Consider latency and cost.
- Protect sensitive data.
- Make model limitations explicit.
- Make missing evidence explicit.

You MUST NOT:

- Use an LLM merely because it is available.
- Claim deterministic LLM output without deterministic external controls.
- Invent model execution.
- Invent retrieval results.
- Invent citations.
- Invent tool execution.
- Invent evaluation results.
- Invent latency or cost evidence.
- Treat NOT EXECUTED as PASS.
- Treat NOT AVAILABLE as PASS.
- Trust model output without appropriate validation.
- Use prompt wording as the sole security boundary.
- Expose unauthorized data to the model.
- Treat retrieved content as trusted instructions.
- Fabricate evidence when retrieval fails.
- Retry indefinitely until a desired answer appears.
- Require RAG for every LLM use case.
- Require tools for every LLM use case.
- Treat every LLM system as agentic.
- Sacrifice grounding, security, or correctness solely to reduce cost or latency.
- Present a prototype as production-ready without evidence.

---

# Collaboration Model

This skill may be applied by:

- Solution Architect → LLM architecture and applicability
- Backend Engineer → LLM integration and application logic
- Frontend Systems Engineer → user interaction and LLM UX
- Security Engineer → LLM threats, data and tool security
- QA Engineer → behavioural and regression validation
- Code Reviewer → implementation-quality review
- DevOps Engineer → deployment, secrets and runtime operations
- Performance Engineer → latency, throughput, context and cost analysis
- Documentation Engineer → LLM documentation
- Orchestrator → routing and final engineering decision

When agentic behaviour exists, also apply:

`Agentic Systems Engineering Skill`

This skill provides reusable LLM engineering guidance.

It does not replace specialist authority.

---

# Definition of Done

An LLM-system design or review is complete when:

- Application lifecycle has been considered.
- The LLM use case is understood.
- LLM usage has been justified.
- Deterministic alternatives have been considered.
- The LLM system boundary is explicit.
- Trusted instructions are distinguished from untrusted content.
- Context sources are identified.
- Context provenance is considered.
- Context freshness is considered where relevant.
- Sensitive-data exposure is considered.
- Model requirements are explicit.
- Model selection is based on requirements rather than novelty.
- Material model configuration is understood.
- Prompt purpose and output requirements are explicit.
- Prompt changes are treated as behavioural changes when material.
- Structured outputs are validated when applicable.
- Grounding requirements are identified.
- Retrieval authorization is evaluated when RAG is involved.
- Retrieval quality is evaluated when RAG is involved.
- No-result behaviour is defined when retrieval is involved.
- Conflicting-source behaviour is considered.
- Citations are not fabricated.
- Tool use is justified when applicable.
- Agentic Systems Engineering Skill is applied when material agentic behaviour exists.
- Model output is treated as untrusted data.
- Hallucination controls are appropriate to risk.
- Abstention or NEEDS MORE INFO behaviour exists when evidence is insufficient.
- Prompt injection and indirect prompt injection are considered.
- Required Security Engineer review is identified.
- Evaluation scenarios are representative.
- Evaluation includes relevant failure and edge cases.
- Evaluation definitions are distinguished from executed evaluations.
- NOT EXECUTED has not been treated as PASS.
- Regression evaluation is considered for material changes.
- LLM variability has been considered.
- Human review is applied according to impact and risk.
- Failure handling is defined.
- Retry behaviour is bounded.
- Observability is appropriate to lifecycle and risk.
- Sensitive prompt and output logging is controlled.
- Performance and cost are considered where material.
- Claims about latency, quality, or cost are evidence-based.
- Critical LLM blockers are explicit.
- Missing evidence is explicit.
- LLM Gate has been produced.
- LLM Recommendation is traceable to evidence.

---

# Goal

Build LLM-powered systems only where probabilistic language or reasoning capabilities provide justified value, and ensure those systems are grounded, validated, secure, evaluable, observable, cost-aware, lifecycle-appropriate, and capable of abstaining rather than fabricating when reliable evidence is unavailable.