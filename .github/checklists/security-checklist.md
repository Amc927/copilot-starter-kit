# Security Review Checklist

Version: 1.0

---

# Purpose

This checklist is used by the Security Engineer to evaluate whether a change satisfies the minimum security requirements required for approval.

Result:

```text
PASS
FAIL
NOT APPLICABLE
```

---

# Authentication

- [ ] Authentication is required where appropriate
- [ ] Authentication cannot be bypassed
- [ ] Session management reviewed
- [ ] Token handling reviewed
- [ ] Expired credentials are rejected
- [ ] Logout behavior validated
- [ ] MFA impact evaluated (if applicable)

Result:

```text
PASS / FAIL / N/A
```

---

# Authorization

- [ ] Role-based access controls reviewed
- [ ] Permission checks exist
- [ ] Object-level authorization enforced
- [ ] Privilege escalation risk evaluated
- [ ] Administrative functions restricted
- [ ] Default access is denied

Result:

```text
PASS / FAIL / N/A
```

---

# Input Validation

- [ ] All user input validated
- [ ] Schemas enforced
- [ ] Invalid input rejected
- [ ] File uploads validated
- [ ] Request size limits evaluated
- [ ] Untrusted input treated as hostile

Result:

```text
PASS / FAIL / N/A
```

---

# API Security

- [ ] API authentication enforced
- [ ] API authorization enforced
- [ ] Error responses do not leak sensitive details
- [ ] Rate limiting evaluated
- [ ] Excessive data exposure reviewed
- [ ] API contracts reviewed

Result:

```text
PASS / FAIL / N/A
```

---

# Sensitive Data Protection

- [ ] Sensitive data identified
- [ ] Sensitive data exposure reviewed
- [ ] Encryption requirements evaluated
- [ ] Sensitive data not exposed in logs
- [ ] Secrets not hardcoded
- [ ] Credentials managed securely

Result:

```text
PASS / FAIL / N/A
```

---

# Database Security

- [ ] Parameterized queries used
- [ ] No SQL injection risk identified
- [ ] Database permissions reviewed
- [ ] Sensitive fields protected
- [ ] Data integrity impact evaluated

Result:

```text
PASS / FAIL / N/A
```

---

# Infrastructure Security

- [ ] Access controls reviewed
- [ ] Secret management reviewed
- [ ] Environment configuration reviewed
- [ ] External exposure evaluated
- [ ] Least-privilege principle applied
- [ ] Deployment security validated

Result:

```text
PASS / FAIL / N/A
```

---

# Logging And Monitoring

- [ ] Security-relevant events logged
- [ ] Authentication failures logged
- [ ] Authorization failures logged
- [ ] Logs do not contain sensitive data
- [ ] Auditability requirements satisfied
- [ ] Monitoring implications evaluated

Result:

```text
PASS / FAIL / N/A
```

---

# Dependency Security

- [ ] Third-party dependencies reviewed
- [ ] Vulnerable libraries identified
- [ ] Supply chain risks evaluated
- [ ] Dependency updates assessed

Result:

```text
PASS / FAIL / N/A
```

---

# AI / LLM Security

Apply only when AI capabilities exist.

- [ ] Prompt injection risk reviewed
- [ ] Indirect prompt injection reviewed
- [ ] Tool permissions reviewed
- [ ] Context poisoning risk reviewed
- [ ] Sensitive data leakage reviewed
- [ ] Agent authority boundaries reviewed

Result:

```text
PASS / FAIL / N/A
```

---

# MCP Security

Apply only when MCP servers exist.

- [ ] Tool permissions reviewed
- [ ] Resource exposure reviewed
- [ ] MCP transport reviewed
- [ ] Authentication requirements reviewed
- [ ] Trust boundaries reviewed
- [ ] Unintended tool execution risks reviewed

Result:

```text
PASS / FAIL / N/A
```

---

# OWASP Review

- [ ] Broken Access Control evaluated
- [ ] Cryptographic Failures evaluated
- [ ] Injection risks evaluated
- [ ] Insecure Design reviewed
- [ ] Security Misconfiguration reviewed
- [ ] Vulnerable Components reviewed
- [ ] Authentication Failures reviewed
- [ ] Integrity Failures reviewed
- [ ] Logging and Monitoring Failures reviewed

Result:

```text
PASS / FAIL / N/A
```

---

# Final Security Gate

## Critical Findings

Count:

```text
0
```

Required for PASS.

---

## High Findings

Count:

```text
0
```

Preferred.

---

## Final Recommendation

Allowed values:

```text
APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO
```

---

## Security Gate Result

Allowed values:

```text
PASSED

CONDITIONAL

FAILED
```

---

# Security Engineer Sign-Off

Reviewer:

```text
_____________________
```

Date:

```text
_____________________
```

Decision:

```text
PASSED / CONDITIONAL / FAILED
```