# Backend Technical Review Checklist

## Purpose

Used by the Backend Engineer to validate implementation quality, maintainability, correctness, performance awareness, and production readiness.

Result:

```text
PASS
FAIL
NOT APPLICABLE
```

---

# Requirements Understanding

- [ ] Business requirements understood
- [ ] Acceptance criteria identified
- [ ] Scope clearly defined
- [ ] Assumptions documented
- [ ] Open questions resolved

Result:

PASS / FAIL / N/A

---

# Architecture Compliance

- [ ] Existing architecture respected
- [ ] Service boundaries respected
- [ ] No unnecessary coupling introduced
- [ ] Separation of concerns maintained
- [ ] No architectural anti-patterns introduced

Result:

PASS / FAIL / N/A

---

# API Design

Apply when APIs are involved.

- [ ] Endpoint naming is consistent
- [ ] HTTP methods correctly used
- [ ] Request validation exists
- [ ] Response contracts defined
- [ ] Error handling standardized
- [ ] Backward compatibility evaluated
- [ ] API documentation updated

Result:

PASS / FAIL / N/A

---

# Business Logic

- [ ] Business rules correctly implemented
- [ ] Edge cases handled
- [ ] Null or empty values handled
- [ ] Error scenarios handled
- [ ] Unexpected states handled

Result:

PASS / FAIL / N/A

---

# Code Quality

- [ ] Code is readable
- [ ] Naming is meaningful
- [ ] No duplicated business logic
- [ ] Functions have a single responsibility
- [ ] Classes have a clear responsibility
- [ ] Complexity level acceptable

Result:

PASS / FAIL / N/A

---

# Error Handling

- [ ] Exceptions handled appropriately
- [ ] Errors provide useful information
- [ ] Internal implementation details not exposed
- [ ] Retry behavior evaluated
- [ ] Failure scenarios documented

Result:

PASS / FAIL / N/A

---

# Data Access Layer

Apply when persistence is involved.

- [ ] Queries reviewed
- [ ] Transactions handled correctly
- [ ] Data consistency verified
- [ ] Database permissions considered
- [ ] Data integrity maintained

Result:

PASS / FAIL / N/A

---

# Security Awareness

Backend review does not replace Security Engineer review.

- [ ] Input validation exists
- [ ] Secret handling reviewed
- [ ] Sensitive data exposure reviewed
- [ ] Authorization requirements identified
- [ ] Security concerns escalated when needed

Result:

PASS / FAIL / N/A

---

# Performance Awareness

Backend review does not replace Performance Engineer review.

- [ ] Expensive operations identified
- [ ] Database impact reviewed
- [ ] External calls reviewed
- [ ] Large dataset impact reviewed
- [ ] Potential bottlenecks documented

Result:

PASS / FAIL / N/A

---

# Logging And Observability

- [ ] Significant events logged
- [ ] Error conditions logged
- [ ] Sensitive information not logged
- [ ] Auditability requirements considered
- [ ] Monitoring impact evaluated

Result:

PASS / FAIL / N/A

---

# Testing Review

- [ ] Unit tests exist
- [ ] Integration tests exist
- [ ] Edge cases tested
- [ ] Failure cases tested
- [ ] Test coverage gaps documented

Result:

PASS / FAIL / N/A

---

# Technical Debt Review

- [ ] Existing technical debt identified
- [ ] New technical debt documented
- [ ] Debt justification recorded
- [ ] Remediation recommendations provided

Result:

PASS / FAIL / N/A

---

# Deployment Impact

- [ ] Configuration changes identified
- [ ] Environment variables documented
- [ ] Backward compatibility assessed
- [ ] Migration requirements identified
- [ ] Rollback implications documented

Result:

PASS / FAIL / N/A

---

# Final Backend Recommendation

Allowed values:

```text
APPROVE

APPROVE WITH CONDITIONS

BLOCK

NEEDS MORE INFO
```

---

# Technical Risk Assessment

Allowed values:

```text
LOW

MEDIUM

HIGH

CRITICAL
```

---

# Backend Review Result

Allowed values:

```text
PASSED

CONDITIONAL

FAILED
```

---

# Backend Engineer Sign-Off

Reviewer:

```text
_____________________
```

Date:

```text
_____________________
```

Result:

```text
PASSED / CONDITIONAL / FAILED
```

Comments:

```text
________________________________________________

________________________________________________

________________________________________________
```