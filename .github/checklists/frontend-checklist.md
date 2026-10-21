# Frontend Technical Review Checklist

## Purpose

Used by the Frontend Systems Engineer to validate frontend implementation quality, technology alignment, architecture compliance, UX correctness, accessibility, security awareness, performance, testing, and production readiness.

This checklist is technology-neutral.

Technology-specific validation must additionally follow the active engineering skill when applicable:

- Endesa Corporate Angular Engineering Skill
- Python Engineering Skill when Streamlit is involved

For each section use:

PASS
FAIL
NOT APPLICABLE

A FAIL in a critical section must be reported to the Orchestrator.

---

# Frontend Technology Detection

- [ ] Frontend technology identified from repository evidence
- [ ] Framework identified
- [ ] Framework version identified when available
- [ ] Runtime version identified when relevant
- [ ] Package or dependency management identified
- [ ] Existing frontend technology preserved unless an approved change exists
- [ ] Active engineering skill identified
- [ ] Technology selection supported by repository evidence or approved architecture
- [ ] No corporate technology or standard assumed without evidence

Frontend technology:

`Angular / React / Vue / Svelte / Streamlit / Vanilla TypeScript / Other / Not determined`

Active skills:

`Endesa Corporate Angular Engineering / Python Engineering / Other / None`

Result:

PASS / FAIL / N/A

---

# Lifecycle Context

Determine when relevant whether the implementation targets:

- [ ] Experiment
- [ ] Prototype / PoC
- [ ] MVP
- [ ] Production

Validate:

- [ ] Lifecycle is supported by available evidence or approved architecture
- [ ] Technology is appropriate for the selected lifecycle
- [ ] Prototype technology is not presented as production architecture without justification
- [ ] Production requirements are not unnecessarily imposed on disposable prototype UI
- [ ] Prototype limitations are explicitly documented
- [ ] Migration impact is documented when prototype and production technologies differ

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Result:

PASS / FAIL / N/A

---

# Streamlit Review

Apply only when Streamlit is involved.

- [ ] Streamlit usage is supported by the approved architecture
- [ ] Streamlit was not selected solely because the backend uses Python
- [ ] Application lifecycle has been identified
- [ ] Business logic is separated from Streamlit-specific UI where practical
- [ ] Reusable backend or domain logic is not unnecessarily coupled to Streamlit
- [ ] Authentication requirements evaluated
- [ ] Authorization requirements evaluated
- [ ] Sensitive information protected
- [ ] Input validation implemented where applicable
- [ ] Error states handled
- [ ] Prototype limitations documented
- [ ] Production target documented when known
- [ ] Migration impact documented when relevant

Result:

PASS / FAIL / N/A

---

# Angular Review

Apply only when Angular is involved.

- [ ] Angular version identified
- [ ] TypeScript version identified
- [ ] Node.js requirements identified
- [ ] Angular repository conventions respected
- [ ] Angular-specific engineering skill applied
- [ ] Existing Angular architecture respected
- [ ] No unnecessary framework migration introduced
- [ ] Angular upgrade not performed implicitly
- [ ] Dependency compatibility evaluated
- [ ] Build compatibility evaluated

Result:

PASS / FAIL / N/A

---

# Corporate Angular Review

Apply only when corporate Angular capabilities are relevant.

- [ ] Corporate frontend evidence searched
- [ ] Corporate libraries verified before use
- [ ] Corporate components verified before use
- [ ] Corporate styles or themes verified before use
- [ ] Corporate documentation checked when available
- [ ] Existing corporate components reused where appropriate
- [ ] Existing component APIs respected
- [ ] Accessibility behaviour of corporate components preserved
- [ ] No corporate package name invented
- [ ] No corporate component invented
- [ ] No corporate API invented
- [ ] No corporate design token invented
- [ ] No corporate registry invented
- [ ] Missing corporate information explicitly reported

If required information cannot be verified, record:

`Corporate information not available - validation required.`

Result:

PASS / FAIL / N/A

---

# Requirements Understanding

- [ ] Business requirements understood
- [ ] Acceptance criteria identified
- [ ] Scope clearly defined
- [ ] User flows identified
- [ ] Assumptions documented
- [ ] Missing requirements identified
- [ ] Open questions resolved or explicitly reported
- [ ] Implementation does not depend on invented requirements

Result:

PASS / FAIL / N/A

---

# Architecture Compliance

- [ ] Approved frontend technology respected
- [ ] Existing architecture respected
- [ ] Frontend/backend boundaries respected
- [ ] API boundaries respected
- [ ] Security boundaries respected
- [ ] Component responsibilities are clear
- [ ] No unnecessary coupling introduced
- [ ] No unauthorized architecture change introduced
- [ ] No unauthorized framework migration introduced
- [ ] Architectural conflicts escalated to the Solution Architect

Result:

PASS / FAIL / N/A

---

# Component Design

- [ ] Components have clear responsibilities
- [ ] Components are appropriately sized
- [ ] Business logic is not unnecessarily embedded in presentation components
- [ ] Existing components reused where appropriate
- [ ] Corporate components reused where applicable
- [ ] Inputs and outputs are clear
- [ ] Component contracts are predictable
- [ ] Hidden side effects avoided
- [ ] Duplicate component functionality avoided
- [ ] Reusable logic separated appropriately

Result:

PASS / FAIL / N/A

---

# UI State Coverage

For relevant user flows evaluate:

- [ ] Initial state
- [ ] Loading state
- [ ] Success state
- [ ] Empty state
- [ ] Validation error state
- [ ] API error state
- [ ] Authentication failure state
- [ ] Authorization failure state
- [ ] Partial failure state
- [ ] Retry state
- [ ] Disabled or unavailable state

Additionally:

- [ ] State transitions are predictable
- [ ] Stale or contradictory information is avoided
- [ ] User actions produce visible feedback where appropriate

Result:

PASS / FAIL / N/A

---

# State Management

- [ ] State ownership is clear
- [ ] Local state used where appropriate
- [ ] Shared state justified
- [ ] Server state distinguished appropriately
- [ ] Existing state-management approach respected
- [ ] No unnecessary global state introduced
- [ ] No duplicate sources of truth introduced
- [ ] New state-management dependency justified
- [ ] State synchronization behaviour understood
- [ ] Failure states represented

Result:

PASS / FAIL / N/A

---

# API Integration

Apply when backend APIs are involved.

- [ ] Request contract understood
- [ ] Response contract understood
- [ ] Contracts typed where supported
- [ ] API abstraction follows repository conventions
- [ ] Raw API access not unnecessarily scattered across UI components
- [ ] API failures handled
- [ ] Authentication failures handled
- [ ] Authorization failures handled
- [ ] Timeouts considered where relevant
- [ ] Unexpected responses considered
- [ ] Sensitive information protected
- [ ] Backend contract changes coordinated with Backend Engineer
- [ ] Frontend not unnecessarily coupled to persistence models

Result:

PASS / FAIL / N/A

---

# Forms and Validation

Apply when forms or user input are involved.

- [ ] Required fields validated
- [ ] Data formats validated
- [ ] Business-relevant constraints represented
- [ ] Validation feedback actionable
- [ ] Backend validation errors handled
- [ ] Invalid submission prevented where appropriate
- [ ] Duplicate submission risk considered
- [ ] Submission state represented
- [ ] Form accessibility considered
- [ ] Client-side validation not treated as a security boundary

Result:

PASS / FAIL / N/A

---

# Error Handling

- [ ] Validation errors handled
- [ ] API errors handled
- [ ] Authentication failures handled
- [ ] Authorization failures handled
- [ ] Network failures handled where relevant
- [ ] Timeouts handled where relevant
- [ ] Missing data handled
- [ ] Partial failures considered
- [ ] Unexpected responses considered
- [ ] Internal implementation details not exposed
- [ ] Raw stack traces not exposed
- [ ] Sensitive configuration not exposed
- [ ] User-facing messages understandable where appropriate

Result:

PASS / FAIL / N/A

---

# Accessibility

- [ ] Semantic HTML used where applicable
- [ ] Keyboard navigation evaluated
- [ ] Focus management evaluated
- [ ] Interactive controls have accessible names
- [ ] Forms have appropriate labels
- [ ] Validation feedback is accessible
- [ ] Error feedback is accessible
- [ ] Colour contrast considered
- [ ] Screen reader behaviour considered
- [ ] Corporate component accessibility behaviour preserved
- [ ] Critical accessibility regressions identified

For prototypes:

- [ ] Temporary accessibility limitations explicitly documented

Result:

PASS / FAIL / N/A

---

# Frontend Security

Frontend review does not replace Security Engineer review.

- [ ] Untrusted input considered
- [ ] XSS risk evaluated
- [ ] Unsafe HTML rendering reviewed
- [ ] DOM injection risk evaluated
- [ ] URL manipulation considered
- [ ] Redirect handling reviewed where applicable
- [ ] Authentication state reviewed
- [ ] Authorization assumptions reviewed
- [ ] Browser storage reviewed
- [ ] Sensitive data exposure reviewed
- [ ] Secrets are not stored in frontend code
- [ ] Tokens are not unnecessarily exposed
- [ ] Security mechanisms have not been disabled for convenience
- [ ] Client-side UI restrictions are not treated as authorization
- [ ] Security-sensitive changes escalated to Security Engineer

Result:

PASS / FAIL / N/A

---

# Dependency Review

- [ ] New dependencies justified
- [ ] Existing capabilities checked first
- [ ] Existing corporate components checked where applicable
- [ ] Framework-native capability checked
- [ ] Existing dependencies checked
- [ ] Compatibility evaluated
- [ ] Security implications considered
- [ ] Maintenance impact considered
- [ ] Performance or bundle impact considered
- [ ] Duplicate dependency functionality avoided
- [ ] Second design system not introduced without approval
- [ ] Dependency choice appropriate to application lifecycle

Result:

PASS / FAIL / N/A

---

# Performance Awareness

Frontend review does not replace Performance Engineer review.

Evaluate when relevant:

- [ ] Initial loading behaviour
- [ ] Bundle size
- [ ] Lazy loading
- [ ] Code splitting
- [ ] Repeated API requests
- [ ] Large collections
- [ ] Expensive rendering
- [ ] State update frequency
- [ ] Subscription lifecycle
- [ ] Asset loading
- [ ] Memory leaks
- [ ] Third-party dependencies
- [ ] Client-side caching
- [ ] Potential bottlenecks documented
- [ ] Significant concerns escalated to Performance Engineer

For prototypes:

- [ ] Prototype performance is not presented as representative of production without evidence

Result:

PASS / FAIL / N/A

---

# Testing Review

- [ ] Unit tests exist where appropriate
- [ ] Component behaviour tested
- [ ] Services tested where appropriate
- [ ] Validation tested
- [ ] State transitions tested
- [ ] Error handling tested
- [ ] Integration tests exist where appropriate
- [ ] API integration boundaries tested
- [ ] Routing tested where relevant
- [ ] Authentication behaviour tested where relevant
- [ ] Corporate component integration tested where relevant
- [ ] End-to-end tests cover critical flows when required
- [ ] Regression tests added for defects where practical
- [ ] Tests are deterministic
- [ ] Tests validate observable behaviour
- [ ] Production credentials are not required by tests
- [ ] Active technology skill testing requirements satisfied
- [ ] Test coverage gaps documented

Result:

PASS / FAIL / N/A

---

# Technical Debt Review

- [ ] Relevant existing technical debt identified
- [ ] Oversized components identified
- [ ] Duplicated logic identified
- [ ] Missing tests identified
- [ ] Inconsistent state management identified
- [ ] Unsafe rendering identified
- [ ] Obsolete dependencies identified
- [ ] Accessibility debt identified
- [ ] Excessive coupling identified
- [ ] Missing UX states identified
- [ ] Styling or design-system debt identified
- [ ] Prototype logic leaking into production architecture identified
- [ ] New technical debt documented
- [ ] Impact and risk documented
- [ ] Remediation recommendation provided
- [ ] Blocking versus non-blocking debt distinguished

Result:

PASS / FAIL / N/A

---

# Documentation Review

- [ ] Frontend documentation updated where necessary
- [ ] Component usage documented where necessary
- [ ] API integration documentation updated
- [ ] Configuration documented
- [ ] New dependencies documented
- [ ] Corporate components documented when applicable
- [ ] Accessibility considerations documented when relevant
- [ ] Known limitations documented
- [ ] Prototype limitations documented when applicable
- [ ] Prototype-to-production migration considerations documented when applicable
- [ ] Missing corporate information documented

Result:

PASS / FAIL / N/A

---

# Build and Deployment Impact

- [ ] Build changes identified
- [ ] Runtime changes identified
- [ ] Environment configuration changes identified
- [ ] Dependency changes identified
- [ ] Corporate dependency requirements identified where applicable
- [ ] Authentication configuration impact identified
- [ ] Deployment impact evaluated
- [ ] Backward compatibility assessed where relevant
- [ ] Rollback implications considered
- [ ] DevOps review requested when deployment risk requires it

Result:

PASS / FAIL / N/A

---

# Critical Frontend Gates

The Frontend Systems Engineer must not recommend approval when any applicable critical condition exists.

- [ ] No broken critical user flow
- [ ] No incompatible API contract
- [ ] No unresolved critical frontend security finding
- [ ] No critical authentication failure
- [ ] No critical authorization design failure
- [ ] No unacceptable exposure of sensitive information
- [ ] No unauthorized framework migration
- [ ] No invented mandatory corporate dependency or component
- [ ] No critical accessibility regression affecting required user flows
- [ ] No production architecture based on an unvalidated prototype assumption
- [ ] No knowingly broken mandatory test flow

If any applicable item fails, report it explicitly to the Orchestrator.

Result:

PASS / FAIL / N/A

---

# Evidence Summary

Frontend Technology:

`_____________________`

Framework:

`_____________________`

Framework Version:

`_____________________`

Lifecycle:

`Experiment / Prototype / PoC / MVP / Production / Not determined`

Active Engineering Skills:

`_____________________`

Corporate Components Detected:

`_____________________`

Repository Evidence:

`_____________________`

Tests Executed:

`_____________________`

Tests Not Executed:

`_____________________`

Known Limitations:

`_____________________`

Missing Information:

`_____________________`

---

# Final Frontend Recommendation

Use the same decision vocabulary as the Orchestrator:

APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO

Recommendation:

`_____________________`

---

# Frontend Risk Assessment

Allowed values:

LOW

MEDIUM

HIGH

CRITICAL

Risk:

`_____________________`

Main Risk Drivers:

`_____________________`

---

# Frontend Review Result

Allowed values:

PASSED

CONDITIONAL

FAILED

Result:

`_____________________`

---

# Frontend Engineer Sign-Off

Reviewer:

`_____________________`

Date:

`_____________________`

Result:

`PASSED / CONDITIONAL / FAILED`

Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO`

Conditions:

`________________________________________________`

Missing Evidence:

`________________________________________________`

Comments:

`________________________________________________`

`________________________________________________`

`________________________________________________`

---

# Definition of Frontend Readiness

A frontend implementation is considered ready for its intended lifecycle when:

- Frontend technology has been identified from repository evidence or approved architecture.
- Application lifecycle has been identified when relevant.
- Approved architecture and frontend/backend boundaries have been respected.
- Existing frontend technology has been preserved unless a change was explicitly approved.
- The appropriate engineering skill has been applied.
- Angular-specific requirements have been followed when Angular is involved.
- Corporate Angular capabilities have only been applied when supported by evidence.
- Corporate components have been reused when verified and appropriate.
- No corporate package, component, API, theme, design token, registry, or standard has been invented.
- Streamlit has not been selected solely because the backend uses Python.
- Prototype technology has not been represented as production architecture without justification.
- Prototype limitations and migration implications have been documented when applicable.
- Critical user flows are functional.
- Required UI states are handled.
- State transitions are predictable.
- API contracts are understood and compatible.
- API failures are handled.
- Authentication failures are handled where applicable.
- Authorization failures are handled where applicable.
- Client-side controls are not treated as authoritative authorization.
- Forms and validation behave correctly where applicable.
- Accessibility has been considered at the appropriate lifecycle depth.
- No critical accessibility regression remains in required user flows.
- Frontend security concerns have been addressed or escalated.
- Performance implications have been considered.
- Dependency changes are justified.
- Build and deployment impacts are understood.
- Required tests exist.
- Required tests pass where execution evidence is available.
- Tests that were not executed are explicitly reported as NOT EXECUTED.
- Missing test evidence has not been treated as PASS.
- Type checking has not been reported as successful without execution evidence.
- Linting has not been reported as successful without execution evidence.
- Technical debt is documented.
- Documentation is updated.
- Known limitations are explicit.
- Missing corporate information is explicit.
- Material risks and missing evidence are explicit.
- Frontend Review Result has been produced.
- Final Frontend Recommendation is traceable to verified evidence.