# QA Validation Checklist

## Purpose

Used by the QA Engineer to validate functional correctness, regression safety, and release readiness.

Result:

```text
PASS
FAIL
NOT APPLICABLE
```

---

# Requirements Validation

- [ ] Business requirements understood
- [ ] Acceptance criteria identified
- [ ] Edge cases identified
- [ ] Expected behavior defined

Result:

PASS / FAIL / N/A

---

# Functional Testing

- [ ] Feature behaves as expected
- [ ] Inputs validated
- [ ] Outputs validated
- [ ] Error handling validated
- [ ] Boundary conditions tested

Result:

PASS / FAIL / N/A

---

# Negative Testing

- [ ] Invalid data tested
- [ ] Empty values tested
- [ ] Unexpected input tested
- [ ] Failure scenarios tested

Result:

PASS / FAIL / N/A

---

# API Validation

- [ ] Request schema validated
- [ ] Response schema validated
- [ ] Error responses validated
- [ ] Backward compatibility reviewed

Result:

PASS / FAIL / N/A

---

# Regression Validation

- [ ] Existing functionality verified
- [ ] Core workflows tested
- [ ] No unintended side effects detected
- [ ] Automated tests reviewed

Result:

PASS / FAIL / N/A

---

# Test Coverage

- [ ] Unit tests exist
- [ ] Integration tests exist
- [ ] Critical paths covered
- [ ] Missing coverage documented

Result:

PASS / FAIL / N/A

---

# Release Recommendation

Allowed Values:

```text
PASS

CONDITIONAL PASS

BLOCK

NEEDS MORE INFO
```

---

# QA Gate Result

```text
PASSED

CONDITIONAL

FAILED
```