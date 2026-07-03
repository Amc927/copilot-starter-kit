---
name: Release Decision Prompt
description: Standardized release approval and deployment decision framework used by the Orchestrator to determine production readiness.
model: Auto (copilot)
---

# Release Decision Prompt

## Objective

Evaluate whether a software change, feature, bug fix, security remediation, infrastructure modification, or release candidate is safe and ready for deployment.

This review does not focus on implementation details.

The objective is to determine production readiness based on:

- Agent findings
- Quality Gate outcomes
- Risk assessment
- Operational readiness
- Governance compliance

---

# Inputs

Review the following information:

- Change summary
- Scope of release
- Agent reports
- Quality Gate results
- Risk assessment
- Deployment plan
- Rollback plan
- Test evidence
- Known limitations

---

# Decision Principles

Always prioritize:

1. Security
2. Functional correctness
3. Production stability
4. Performance
5. Maintainability

Feature delivery must never override critical risk.

---

# Quality Gate Review

Evaluate:

## Security Gate

Status:

```text
PASSED
CONDITIONAL
FAILED
```

Determine:

- Critical vulnerabilities
- Authorization risks