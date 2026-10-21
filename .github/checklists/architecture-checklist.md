# Architecture Review Checklist

## Purpose

Used by the Solution Architect to evaluate architectural quality, lifecycle suitability, technology selection, scalability, maintainability, reliability, security alignment, deployment readiness, and long-term sustainability.

This checklist supports:

- Architecture Gate
- Technical Design Reviews
- System Evolution Reviews
- Technology Selection
- Prototype / PoC Reviews
- MVP Reviews
- Production Architecture Reviews
- Solution Approval Processes

For each section use:

PASS
FAIL
NOT APPLICABLE

A FAIL in a critical architectural section must be reported to the Orchestrator.

### Applicability Rule

Use this checklist only when architectural evaluation is materially applicable.

A Prototype / PoC does not by itself require Solution Architect participation or make the Architecture Gate applicable.

Architecture Gate applicability depends on whether the request materially affects areas such as:

- Technology selection or migration
- System or service boundaries
- Data ownership
- Datastore selection
- Major integration patterns
- Deployment architecture
- Prototype-to-production architecture
- MCP adoption
- Material LLM architecture
- Material agentic architecture

When a change remains within established repository technology and existing architectural boundaries, the Architecture Gate may be:

`NOT APPLICABLE`

Do not execute this checklist merely because the lifecycle is Prototype / PoC.

Checklist availability does not prove Architecture Gate applicability.

---

# Business Alignment

- [ ] Business objective clearly defined
- [ ] Proposed solution addresses the business need
- [ ] Scope is understood
- [ ] Functional requirements identified
- [ ] Relevant non-functional requirements identified
- [ ] Constraints identified
- [ ] Success criteria identified
- [ ] Assumptions documented
- [ ] Missing information explicitly identified
- [ ] Architecture does not depend on invented requirements

Result:

PASS / FAIL / NOT APPLICABLE

---

# Lifecycle Classification

The intended lifecycle must be identified when it materially affects architectural decisions.

Allowed classifications:

- Experiment
- Prototype / PoC
- MVP
- Production
- Not determined

Review:

- [ ] Lifecycle classified
- [ ] Lifecycle classification supported by requirements or approved context
- [ ] Architecture complexity appropriate to lifecycle
- [ ] Prototype technology not presented as production architecture without justification
- [ ] Production requirements not unnecessarily imposed on disposable experiments
- [ ] MVP architecture supports expected near-term evolution
- [ ] Production architecture addresses operational requirements
- [ ] Lifecycle uncertainty explicitly documented

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Result:

PASS / FAIL / NOT APPLICABLE

---

# Repository and Existing Architecture Evidence

Apply when an existing repository or application exists.

- [ ] Existing programming languages identified
- [ ] Existing backend technology identified
- [ ] Existing frontend technology identified
- [ ] Frameworks identified
- [ ] Relevant technology versions identified where available
- [ ] Package or dependency management identified
- [ ] APIs identified
- [ ] Databases identified
- [ ] External integrations identified
- [ ] Authentication architecture identified
- [ ] Authorization architecture identified
- [ ] Deployment model identified
- [ ] Existing tests considered
- [ ] Existing architecture documentation reviewed when available
- [ ] Corporate dependencies investigated
- [ ] Repository evidence used before proposing technology changes

Result:

PASS / FAIL / NOT APPLICABLE

---

# Technology Selection

Apply when a technology decision is required.

- [ ] Technology decision required and explicitly identified
- [ ] Existing technology evaluated before proposing replacement
- [ ] Business requirements considered
- [ ] Lifecycle considered
- [ ] Security requirements considered
- [ ] Integration requirements considered
- [ ] Operational requirements considered
- [ ] Maintainability considered
- [ ] Performance considered
- [ ] Deployment constraints considered
- [ ] Migration cost considered
- [ ] Verified corporate standards considered
- [ ] Technology not selected merely because a corresponding skill exists
- [ ] Decision rationale documented
- [ ] Relevant alternatives considered
- [ ] Rejected alternatives have documented reasoning

Result:

PASS / FAIL / NOT APPLICABLE

---

# Backend Technology Decision

Apply when backend technology is relevant.

Evaluate applicable options:

- Existing backend technology
- Python
- Java
- Other technology required by the repository or architecture

Review:

- [ ] Existing backend technology identified
- [ ] Python evaluated when relevant
- [ ] Java evaluated when relevant
- [ ] Existing non-Python/Java technology preserved unless migration is justified
- [ ] Backend choice appropriate to lifecycle
- [ ] Backend choice appropriate to integrations
- [ ] Backend choice appropriate to deployment environment
- [ ] Backend choice appropriate to maintenance requirements
- [ ] Backend choice appropriate to performance requirements
- [ ] Organizational or platform constraints verified rather than assumed
- [ ] No unnecessary language migration introduced

Selected Backend:

`Python / Java / Existing technology / Other / None / Not determined`

Rationale:

`_____________________`

Result:

PASS / FAIL / NOT APPLICABLE

---

# Python vs Java Assessment

Apply only when Python and Java are genuine alternatives.

Evaluate:

- [ ] Existing ecosystem
- [ ] Existing repository
- [ ] Functional requirements
- [ ] Data processing requirements
- [ ] AI/LLM requirements
- [ ] Integration requirements
- [ ] Runtime constraints
- [ ] Deployment environment
- [ ] Maintainability
- [ ] Operational support
- [ ] Performance requirements
- [ ] Verified corporate requirements
- [ ] Migration implications

Decision:

`Python / Java / Existing technology / Needs more information`

No universal superiority has been assumed.

Result:

PASS / FAIL / NOT APPLICABLE

---

# Frontend Technology Decision

Apply when a dedicated frontend is relevant.

Evaluate applicable options:

- Existing frontend technology
- Angular
- Streamlit
- React
- Vue
- Svelte
- Vanilla TypeScript
- Other justified technology
- No dedicated frontend

Review:

- [ ] Existing frontend technology identified
- [ ] Lifecycle considered
- [ ] UX complexity considered
- [ ] Accessibility requirements considered
- [ ] Corporate frontend requirements considered
- [ ] Maintainability considered
- [ ] Security considered
- [ ] Integration requirements considered
- [ ] Deployment model considered
- [ ] No framework selected solely because a specialist skill exists
- [ ] No unnecessary frontend migration introduced

Selected Frontend:

`Angular / Streamlit / Existing technology / Other / None / Not determined`

Rationale:

`_____________________`

Result:

PASS / FAIL / NOT APPLICABLE

---

# Endesa Corporate Angular Assessment

Apply when Angular is selected or already present.

- [ ] Angular use supported by repository evidence or approved architecture
- [ ] Angular version identified when available
- [ ] Node.js requirements identified when available
- [ ] Endesa corporate frontend libraries investigated
- [ ] Corporate components investigated
- [ ] Corporate themes and styles investigated
- [ ] Corporate documentation reviewed when available
- [ ] Corporate components reused where appropriate
- [ ] Corporate package names verified
- [ ] Corporate component APIs verified
- [ ] No corporate package invented
- [ ] No corporate component invented
- [ ] No corporate API invented
- [ ] No corporate design token invented
- [ ] Missing corporate information explicitly documented

If required corporate information cannot be verified:

`Corporate information not available - validation required.`

Result:

PASS / FAIL / NOT APPLICABLE

---

# Streamlit / Prototype Assessment

Apply when Streamlit is established by repository evidence, explicitly proposed, or selected through an applicable architecture decision.

Streamlit does not by itself imply a Prototype / PoC lifecycle.

Evaluate Streamlit according to the verified lifecycle and requirements of the application.

- [ ] Lifecycle and intended use identified
- [ ] Streamlit selection justified
- [ ] Streamlit not selected solely because Python is used
- [ ] UX complexity appropriate for Streamlit
- [ ] Business workflow can be validated with the proposed UI
- [ ] Lifecycle-specific limitations documented when applicable
- [ ] Reusable business logic appropriately separated from UI concerns where practical
- [ ] Production target identified when known
- [ ] Prototype-to-production migration impact evaluated
- [ ] Authentication differences evaluated when relevant
- [ ] Authorization differences evaluated when relevant
- [ ] Deployment differences evaluated when relevant
- [ ] Corporate UI adoption implications evaluated when relevant

Result:

PASS / FAIL / NOT APPLICABLE

---

# Prototype vs Production Architecture

Apply only when a Prototype / PoC has a verified or explicitly proposed production target that materially differs from the prototype architecture or technology.

Do not invent a production target merely because the current lifecycle is Prototype / PoC.

When no production target is known or required, this section is:

`NOT APPLICABLE`

- [ ] Prototype stack explicitly identified
- [ ] Production target explicitly identified when known
- [ ] Reusable business logic identified
- [ ] Reusable and disposable components identified according to the verified production-transition strategy
- [ ] Reusable API boundaries identified
- [ ] Data model continuity evaluated
- [ ] Authentication migration evaluated
- [ ] Authorization migration evaluated
- [ ] Corporate component adoption evaluated
- [ ] Accessibility impact evaluated
- [ ] Deployment migration evaluated
- [ ] Testing migration evaluated
- [ ] Migration risks documented
- [ ] Prototype convenience not silently converted into production architecture

Prototype Stack:

`_____________________`

Production Target:

`_____________________`

Result:

PASS / FAIL / NOT APPLICABLE

---

# Architectural Boundaries

- [ ] Responsibilities clearly separated
- [ ] System boundaries well defined
- [ ] Component ownership identifiable
- [ ] Backend/frontend boundaries clear
- [ ] Data ownership clear
- [ ] Security boundaries clear
- [ ] Components do not unnecessarily overlap responsibilities
- [ ] Architecture avoids unnecessary coupling
- [ ] Technology boundaries understandable

Result:

PASS / FAIL / NOT APPLICABLE

---

# Separation Of Concerns

- [ ] Business logic separated appropriately from infrastructure
- [ ] Data access separated appropriately from business logic
- [ ] Presentation concerns isolated
- [ ] Cross-cutting concerns properly managed
- [ ] Component responsibilities clear
- [ ] Prototype UI does not unnecessarily own reusable business logic
- [ ] Integration concerns have clear boundaries

Result:

PASS / FAIL / NOT APPLICABLE

---

# Modularity

- [ ] Components are appropriately modular
- [ ] Components can evolve independently where required
- [ ] Dependencies are explicit
- [ ] Reuse opportunities identified
- [ ] Complexity remains manageable
- [ ] Module boundaries reflect responsibilities
- [ ] Technology-specific concerns do not unnecessarily leak across boundaries

Result:

PASS / FAIL / NOT APPLICABLE

---

# Integration Design

- [ ] Internal integrations reviewed
- [ ] External integrations reviewed
- [ ] API contracts defined
- [ ] Contract ownership identified
- [ ] Authentication considered
- [ ] Authorization considered
- [ ] Failure scenarios considered
- [ ] Timeout requirements considered
- [ ] Retry implications considered
- [ ] Coupling acceptable
- [ ] Sensitive data exchange identified

Result:

PASS / FAIL / NOT APPLICABLE

---

# MCP Architecture Review

Apply only when MCP is proposed or already exists.

MCP is an integration capability, not a replacement for Python, Java, or frontend technology.

- [ ] MCP requirement explicitly identified
- [ ] MCP provides a justified capability
- [ ] Alternative integration approaches considered where relevant
- [ ] Tools identified
- [ ] Tool boundaries defined
- [ ] Resources identified where applicable
- [ ] Prompts identified where applicable
- [ ] Tool side effects understood
- [ ] Permission boundaries defined
- [ ] Authentication requirements identified
- [ ] Authorization requirements identified
- [ ] Least privilege considered
- [ ] Transport strategy identified
- [ ] Security implications reviewed
- [ ] Prompt injection / untrusted content risks considered
- [ ] Operational complexity considered
- [ ] Scalability implications considered
- [ ] MCP not introduced merely because AI is involved

When Python implements MCP:

- [ ] Python Engineering Skill expected
- [ ] Python MCP Engineering Skill expected

Result:

PASS / FAIL / NOT APPLICABLE

---

# Data Architecture

- [ ] Data ownership defined
- [ ] Source of truth identified
- [ ] Data flow documented or understood
- [ ] Data consistency considered
- [ ] Persistence strategy validated
- [ ] Transaction requirements considered
- [ ] Data lifecycle considered
- [ ] Sensitive data identified
- [ ] Data migration requirements identified
- [ ] Expected volume considered when relevant
- [ ] Additional storage technology justified

Result:

PASS / FAIL / NOT APPLICABLE

---

# Scalability

Scalability must be appropriate to the lifecycle and expected demand.

- [ ] Expected demand considered where known
- [ ] Growth assumptions documented where relevant
- [ ] Horizontal scaling evaluated when relevant
- [ ] Vertical scaling evaluated when relevant
- [ ] Bottlenecks identified
- [ ] Resource utilization considered
- [ ] External dependency limits considered
- [ ] Scalability complexity justified
- [ ] Prototype not over-engineered for hypothetical production scale
- [ ] Production architecture not based on unsupported scalability assumptions

Result:

PASS / FAIL / NOT APPLICABLE

---

# Reliability

- [ ] Failure modes identified
- [ ] Relevant single points of failure identified
- [ ] Recovery strategy considered
- [ ] Resilience mechanisms considered where required
- [ ] Availability requirements evaluated
- [ ] External dependency failure considered
- [ ] Partial failure considered
- [ ] Data consistency under failure considered

Result:

PASS / FAIL / NOT APPLICABLE

---

# Performance Impact

- [ ] Expected workload considered
- [ ] High-volume scenarios evaluated when relevant
- [ ] Database impact evaluated
- [ ] Network impact evaluated
- [ ] External integration latency reviewed
- [ ] Frontend performance considered where relevant
- [ ] Potential bottlenecks documented
- [ ] Performance complexity justified by requirements
- [ ] Prototype performance not presented as production evidence without validation

Result:

PASS / FAIL / NOT APPLICABLE

---

# Security Alignment

Architecture review complements but does not replace Security Engineer review.

- [ ] Trust boundaries identified
- [ ] Authentication model reviewed
- [ ] Authorization model reviewed
- [ ] Least privilege considered
- [ ] Sensitive data identified
- [ ] Data protection requirements identified
- [ ] Secret management requirements identified
- [ ] External security boundaries identified
- [ ] Frontend/backend security responsibilities separated
- [ ] MCP permissions reviewed when applicable
- [ ] Security responsibilities assigned
- [ ] Critical security concerns escalated to Security Engineer

Result:

PASS / FAIL / NOT APPLICABLE

---

# Observability

Observability depth should match the lifecycle and operational requirements.

- [ ] Logging requirements identified
- [ ] Monitoring requirements identified
- [ ] Metrics requirements identified where relevant
- [ ] Traceability requirements identified
- [ ] Correlation requirements considered
- [ ] Important operational events identifiable
- [ ] External dependency visibility considered
- [ ] Production troubleshooting needs considered
- [ ] Sensitive information excluded from observability design

Result:

PASS / FAIL / NOT APPLICABLE

---

# Deployment Architecture

- [ ] Deployment model defined
- [ ] Runtime identified
- [ ] Environment strategy defined where required
- [ ] Infrastructure dependencies identified
- [ ] Configuration strategy identified
- [ ] Secret management considered
- [ ] CI/CD implications considered
- [ ] Rollback considerations documented
- [ ] Availability requirements considered
- [ ] Scalability requirements considered
- [ ] Operational ownership identified when known
- [ ] Deployment complexity appropriate to lifecycle

Result:

PASS / FAIL / NOT APPLICABLE

---

# Testability

- [ ] Components are testable
- [ ] Interfaces are testable
- [ ] Integration points are testable
- [ ] Failure scenarios are testable
- [ ] Acceptance criteria are testable
- [ ] Technology selection supports required testing
- [ ] Security-critical behaviour can be validated
- [ ] Migration behaviour can be validated where applicable
- [ ] MCP contracts testable when applicable
- [ ] Prototype limitations do not prevent validation of the intended concept

Result:

PASS / FAIL / NOT APPLICABLE

---

# Technical Debt Review

- [ ] Existing relevant technical debt identified
- [ ] New technical debt documented
- [ ] Technology-selection debt identified
- [ ] Prototype-specific debt identified
- [ ] Trade-offs explained
- [ ] Debt impact evaluated
- [ ] Debt risk evaluated
- [ ] Remediation strategy proposed where appropriate
- [ ] Blocking versus non-blocking debt distinguished
- [ ] Long-term impact considered

Result:

PASS / FAIL / NOT APPLICABLE

---

# LLM Architecture Review

Apply only when the solution itself includes material LLM functionality and architectural evaluation is applicable.

LLM functionality does not by itself make the system agentic or require a material architecture decision.

Use:

`LLM Engineering Skill`

for detailed LLM engineering guidance.

Review architectural concerns when applicable:

- [ ] LLM functionality is justified by verified requirements
- [ ] Deterministic alternatives considered where relevant
- [ ] LLM system boundary is clear
- [ ] Model responsibilities are clear
- [ ] Trusted and untrusted context boundaries are understood
- [ ] Grounding or retrieval architecture considered when applicable
- [ ] Data and permission boundaries identified
- [ ] External model-provider boundary considered when applicable
- [ ] Structured-output or downstream validation responsibilities identified
- [ ] Tool usage identified when applicable
- [ ] Security implications identified
- [ ] Evaluation requirements identified
- [ ] Operational implications considered where relevant
- [ ] LLM architecture complexity is justified

Result:

PASS / FAIL / NOT APPLICABLE

---

# Agentic Systems Architecture Review

Apply only when the solution itself includes material agentic behaviour and architectural evaluation is applicable.

The existence of LLM functionality does not by itself make the solution agentic.

The fact that the Starter Kit uses agents does not make every target application an agentic system.

Use:

`Agentic Systems Engineering Skill`

for detailed agentic-system engineering guidance.

Review architectural concerns when applicable:

- [ ] Agentic behaviour is justified by verified requirements
- [ ] Simpler deterministic or non-agentic alternatives considered
- [ ] Agent responsibilities clearly defined
- [ ] Agent boundaries established
- [ ] Authority model defined
- [ ] Routing model defined where applicable
- [ ] Delegation model defined where applicable
- [ ] Tool boundaries and permissions considered
- [ ] State and memory architecture considered where relevant
- [ ] Human oversight considered according to risk
- [ ] Stopping conditions considered
- [ ] Failure handling considered
- [ ] Traceability requirements considered
- [ ] Security implications identified
- [ ] Agentic complexity justified
- [ ] Multiple agents are not introduced without a material need

Result:

PASS / FAIL / NOT APPLICABLE

---

# Future Maintainability

- [ ] Future enhancements considered at an appropriate level
- [ ] Complexity remains manageable
- [ ] Technology choices are supportable
- [ ] Documentation requirements identified
- [ ] Knowledge transfer possible
- [ ] Architecture remains understandable
- [ ] Upgrade path considered where relevant
- [ ] Corporate dependency evolution considered where relevant
- [ ] Prototype migration path understood where relevant

Result:

PASS / FAIL / NOT APPLICABLE

---

# Specialist Routing

When Architecture Gate is applicable, identify specialist capabilities and engineering skills that may be required by the approved architecture.

Final agent routing remains the responsibility of the Orchestrator and must follow actual scope, lifecycle, risk, evidence, domain impact, and Quality Gate applicability.

Architecture review must not make specialist participation mandatory merely because a capability may be relevant during later implementation.

Backend Python:

`Backend Engineer + Python Engineering Skill`

Backend Java:

`Backend Engineer + Java Engineering Skill`

Python MCP:

`Backend Engineer + Python Engineering Skill + Python MCP Engineering Skill`

Angular:

`Frontend Systems Engineer + Endesa Corporate Angular Engineering Skill`

Streamlit:

`Frontend Systems Engineer + Python Engineering Skill where Python implementation guidance is required`

Additional reviews when applicable:

- [ ] Security Engineer
- [ ] QA Engineer
- [ ] Code Reviewer
- [ ] DevOps Engineer
- [ ] Performance Engineer
- [ ] Documentation Engineer

Result:

PASS / FAIL / NOT APPLICABLE

---

# Critical Architecture Gates

The Solution Architect must not recommend approval when an applicable critical condition exists.

- [ ] No unresolved critical architectural inconsistency
- [ ] No undefined critical system boundary
- [ ] No unresolved critical data-integrity risk
- [ ] No unresolved critical security architecture risk
- [ ] No technology migration without justification and approval
- [ ] No production architecture based solely on prototype convenience
- [ ] No mandatory corporate technology invented
- [ ] No critical integration contract left undefined
- [ ] No unjustified MCP exposure of sensitive capabilities
- [ ] No unresolved deployment blocker for the intended lifecycle

If any applicable item fails, report it explicitly to the Orchestrator.

Result:

PASS / FAIL / NOT APPLICABLE

---

# Architecture Evidence Summary

Business Objective:

`_____________________`

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Existing Backend:

`_____________________`

Recommended Backend:

`_____________________`

Existing Frontend:

`_____________________`

Recommended Frontend:

`_____________________`

MCP Required:

`YES / NO / NOT DETERMINED`

Prototype Stack:

`_____________________`

Production Target:

`_____________________`

Active Engineering Skills:

`_____________________`

Corporate Standards Verified:

`_____________________`

Missing Corporate Information:

`_____________________`

Main Architectural Constraints:

`_____________________`

Main Trade-offs:

`_____________________`

---

# Architecture Risk Assessment

Highest Risk Level:

LOW

MEDIUM

HIGH

CRITICAL

Risk:

`_____________________`

Main Risk Drivers:

`_____________________`

---

# Architecture Gate Result

Use exactly one:

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
NOT APPLICABLE != PASSED
```

Use `NOT APPLICABLE` when architectural evaluation is not materially applicable to the scoped change.

Use `NOT EXECUTED` when Architecture Gate is applicable but the required architectural evaluation has not been performed.

Use `NOT AVAILABLE` when Architecture Gate is applicable but required architecture evidence or capability is unavailable.

Result:

`_____________________`

---

# Architecture Recommendation

Produce an Architecture Recommendation only when Architecture Gate is applicable.

Use exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
NOT APPLICABLE
```

Use:

`NOT APPLICABLE`

only when Architecture Gate is `NOT APPLICABLE` and no architectural recommendation is required.

Apply:

```text
ARCHITECTURE GATE NOT APPLICABLE
!=
ARCHITECTURE APPROVED
```

When Architecture Gate is applicable but required architectural evaluation has not been executed or required evidence is unavailable, use:

`NEEDS MORE INFO`

Do not fabricate architectural approval merely because no architectural blocker has been reported.

Recommendation:

`_____________________`

---

# Solution Architect Sign-Off

Complete this section only when the Solution Architect actually participated.

Do not invent reviewer identity, review date, participation, approval, or recommendation.

Participation:

```text
EXECUTED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Reviewer:

`_____________________`

Date:

`_____________________`

Architecture Gate:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Architecture Recommendation:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
NOT APPLICABLE
```

Use `NOT APPLICABLE` for the recommendation only when the Architecture Gate is `NOT APPLICABLE` and no Solution Architect recommendation is required.

Comments:

`________________________________________________`

`________________________________________________`

`________________________________________________`

Apply:

```text
SOLUTION ARCHITECT DEFINED != SOLUTION ARCHITECT PARTICIPATED
SIGN-OFF TEMPLATE AVAILABLE != SIGN-OFF EXECUTED
NOT EXECUTED != APPROVED
NOT AVAILABLE != APPROVED
NOT APPLICABLE != APPROVED
```

When the Architecture Gate is `NOT APPLICABLE`, do not fabricate a Solution Architect sign-off.

When the Architecture Gate is applicable but the Solution Architect review has not been executed, use:

```text
Participation: NOT EXECUTED
Architecture Gate: NOT EXECUTED
Architecture Recommendation: NEEDS MORE INFO
```

When the required Solution Architect capability or architectural evidence is unavailable, use:

```text
Participation: NOT AVAILABLE
Architecture Gate: NOT AVAILABLE
Architecture Recommendation: NEEDS MORE INFO
```

---

# Definition Of Architectural Readiness

A solution is considered architecturally ready when:

- Business objective is understood.
- Lifecycle is classified when relevant.
- Existing architecture is understood when applicable.
- Existing technologies are identified.
- Technology selection is justified.
- Backend technology is identified when relevant.
- Frontend technology is identified when relevant.
- Prototype and production architectures are distinguished when necessary.
- System responsibilities are clearly separated.
- Boundaries are defined.
- Data ownership is understood.
- Integration contracts are sufficiently defined.
- Scalability has been evaluated at the appropriate level.
- Reliability concerns are addressed.
- Security requirements are understood.
- Observability requirements are appropriate to the lifecycle.
- Deployment implications are understood.
- MCP usage is justified when applicable.
- Corporate standards have not been invented.
- Technical debt is documented.
- Migration impact is understood where applicable.
- Specialist routing is identified.
- Long-term maintainability is acceptable.
- Trade-offs are documented.
- Missing information is explicit.