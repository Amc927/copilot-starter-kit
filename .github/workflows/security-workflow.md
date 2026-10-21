# Security Workflow

Version: 2.0

---

# Purpose

This workflow defines the security process for evaluating, validating, remediating, and approving security-sensitive changes and security posture.

The objective is to ensure that applicable security requirements are identified early, verified against available evidence, implemented correctly, tested, and evaluated before deployment.

This workflow applies when appropriate to:

- Authentication changes
- Authorization changes
- Identity-management changes
- Sensitive-data changes
- Secret-management changes
- Certificate or credential changes
- API security changes
- Database security changes
- File-handling changes
- Security remediation
- Vulnerability remediation
- Dependency-security issues
- Infrastructure security changes
- Internet or externally exposed applications
- MCP capabilities
- AI / LLM capabilities
- Agentic-system capabilities
- Compliance-driven security changes
- Changes affecting the cybersecurity posture of the system

Not every stage applies equally to every change.

Security depth must reflect:

- Application lifecycle
- Exposure
- Data sensitivity
- Architecture
- Verified corporate requirements
- Project-specific requirements
- Risk

---

# Security Principles

Apply throughout the workflow:

- Security by Design
- Defense in Depth
- Zero Trust
- Least Privilege
- Deny by Default
- Assume Breach
- Secure Defaults
- Fail Securely
- Minimize Attack Surface
- Evidence-Based Security Decisions

Security is a system property and must be considered throughout the software lifecycle.

---

# Security Evidence Hierarchy

Security decisions must distinguish between:

## Corporate Requirements

Verified Enel/Endesa security requirements.

## Project-Specific Requirements

Requirements derived from project evidence such as:

- Risk Assessment
- Cyber Security Risk Treatment Analysis
- Security Annex
- HLD
- Detailed Technical Design
- Platform requirements
- Ethical Hacking findings
- Approved remediation plans

## Security Tooling Evidence

Evidence produced by:

- SonarQube
- Static-analysis tools
- Dependency-analysis tools
- Dynamic testing
- API testing
- Ethical Hacking / Penetration Testing

## Industry Security Practices

Examples:

- OWASP
- CWE
- NIST

## Security Engineer Assessment

Manual security analysis including:

- Threat modelling
- Trust-boundary analysis
- Authentication review
- Authorization review
- Data-flow analysis
- Abuse cases
- Architecture-level security review

Do not represent an industry recommendation as a mandatory Enel/Endesa requirement without verified evidence.

---

# Workflow Overview

```text
Security Intake
      |
      v
Security Classification
      |
      v
Corporate / Project Evidence
      |
      v
Security Context
      |
      v
Threat Model
      |
      v
Security Tooling Evidence
      |
      +--> SonarQube
      +--> Dependency Analysis
      +--> Dynamic Testing
      +--> Existing Ethical Hacking
      |
      v
Manual Security Review
      |
      v
Implementation / Remediation
      |
      v
Security Validation
      |
      v
Assurance / Ethical Hacking
when applicable
      |
      v
Findings Aggregation
      |
      v
Security Quality Gate
      |
      v
Residual Risk
      |
      v
Security Recommendation
      |
      v
Orchestrator Final Decision
```