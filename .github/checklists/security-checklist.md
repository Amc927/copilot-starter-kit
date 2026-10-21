# Security Review Checklist

Version: 2.0

---

# Purpose

Used by the Security Engineer to evaluate whether a change or solution satisfies the applicable security requirements required for approval.

The checklist combines:

- Verified Enel/Endesa security requirements
- Project-specific security requirements
- Secure Software Development Lifecycle controls
- Security-tooling evidence
- OWASP and established industry security practices
- Manual threat and security analysis

Not every section applies to every application.

For each section use:

PASS
FAIL
NOT APPLICABLE
NOT EXECUTED

Do not convert missing evidence into PASS.

A FAIL in a critical security control must be reported to the Orchestrator.

---

# Security Context

- [ ] Application type identified
- [ ] Application lifecycle identified
- [ ] Architecture understood
- [ ] Technologies identified
- [ ] Data handled by the application identified
- [ ] Sensitive or confidential information identified when applicable
- [ ] External exposure identified
- [ ] Trust boundaries identified
- [ ] External integrations identified
- [ ] Authentication mechanism identified
- [ ] Authorization mechanism identified
- [ ] Relevant security documentation identified
- [ ] Missing security-critical information documented

Result:

PASS / FAIL / N/A

---

# Corporate Security Evidence

Determine which security requirements have verified corporate or project evidence.

Review available:

- [ ] Enel/Endesa Security Guidelines
- [ ] Security Annex
- [ ] Risk Assessment
- [ ] Cyber Security Risk Treatment Analysis
- [ ] HLD security requirements
- [ ] Detailed Technical Design security requirements
- [ ] Enel Digital Platform security documentation
- [ ] Ethical Hacking reports
- [ ] Security remediation plans
- [ ] Platform authentication documentation
- [ ] Platform authorization documentation
- [ ] Secret-management documentation
- [ ] Other approved project security documentation

Requirements have been classified as:

- [ ] Corporate Requirement
- [ ] Project-Specific Requirement
- [ ] Industry Security Practice
- [ ] Security Recommendation

No industry recommendation has been incorrectly presented as a mandatory Enel/Endesa requirement.

If relevant corporate requirements cannot be verified, record:

`Corporate security requirement not verified - validation required.`

Result:

PASS / FAIL / N/A

---

# Secure Software Development Lifecycle

Evaluate security throughout the applicable lifecycle.

## Planning

- [ ] Security requirements identified
- [ ] Data sensitivity considered
- [ ] Trust boundaries considered
- [ ] Exposure considered

## Design

- [ ] Authentication architecture reviewed
- [ ] Authorization architecture reviewed
- [ ] Data-flow security reviewed
- [ ] Integration security reviewed
- [ ] Secret-management architecture reviewed
- [ ] Attack surface considered

## Development

- [ ] Secure coding controls evaluated
- [ ] Static-analysis requirements evaluated
- [ ] Dependency security evaluated
- [ ] Security-sensitive implementation reviewed

## Testing

- [ ] Security testing requirements identified
- [ ] SonarQube evaluated when available
- [ ] Dependency analysis evaluated when available
- [ ] Dynamic security testing evaluated when applicable
- [ ] Ethical Hacking applicability evaluated

## Deployment

- [ ] Secure configuration considered
- [ ] Secret handling considered
- [ ] Production exposure considered
- [ ] Production security evidence reviewed

## Maintenance

- [ ] Vulnerability-management requirements considered
- [ ] Credential rotation considered where applicable
- [ ] Certificate lifecycle considered where applicable
- [ ] Security-relevant maintenance responsibilities identified

Result:

PASS / FAIL / N/A

---

# Secure Coding Baseline

Review applicable secure coding controls.

- [ ] Input validation
- [ ] Output encoding
- [ ] Output sanitization
- [ ] Authentication
- [ ] Password management where applicable
- [ ] Session management where applicable
- [ ] Access control
- [ ] Deny by Default
- [ ] Least Privilege
- [ ] Cryptographic practices
- [ ] Error handling
- [ ] Logging
- [ ] Data protection
- [ ] Communication security
- [ ] System configuration
- [ ] Database security
- [ ] File management where applicable
- [ ] Memory-management concerns where applicable
- [ ] Modularity
- [ ] No backdoors
- [ ] Source-code protection considerations
- [ ] Executable protection considerations
- [ ] Security documentation
- [ ] Component inventory where required

Result:

PASS / FAIL / N/A

---

# Authentication

- [ ] Authentication required where appropriate
- [ ] Authentication mechanism identified
- [ ] Authentication cannot be bypassed
- [ ] User identity handled securely
- [ ] Session management reviewed
- [ ] Token handling reviewed
- [ ] Expired credentials rejected
- [ ] Logout behaviour reviewed where applicable
- [ ] Default accounts reviewed where applicable
- [ ] Service accounts reviewed where applicable
- [ ] Robot users reviewed where applicable
- [ ] Certificate authentication reviewed where applicable
- [ ] MFA impact evaluated where applicable
- [ ] Centralized authentication requirement verified where applicable
- [ ] Corporate authentication integration not invented

Result:

PASS / FAIL / N/A

---

# Authorization

- [ ] Authorization mechanism identified
- [ ] Least Privilege applied
- [ ] Deny by Default applied
- [ ] Permission checks exist
- [ ] Role-based controls reviewed where applicable
- [ ] Object-level authorization enforced where required
- [ ] Function-level authorization enforced where required
- [ ] Resource-level authorization reviewed
- [ ] Administrative functions restricted
- [ ] Privilege escalation risk evaluated
- [ ] Service-to-service authorization reviewed where applicable
- [ ] Data authorization reviewed
- [ ] Frontend restrictions are not treated as authoritative authorization
- [ ] Backend enforcement exists for security-sensitive controls
- [ ] SecurePlat applicability investigated where relevant
- [ ] SecurePlat configuration not invented

Result:

PASS / FAIL / N/A

---

# Input Validation

- [ ] External input treated as untrusted
- [ ] Required fields validated
- [ ] Types validated
- [ ] Formats validated
- [ ] Length limits evaluated
- [ ] Numeric or logical ranges evaluated
- [ ] Enumerated values validated
- [ ] Identifiers validated
- [ ] Paths validated where applicable
- [ ] URLs validated where applicable
- [ ] API payloads validated
- [ ] External service responses considered untrusted
- [ ] File uploads validated where applicable
- [ ] Request-size limits evaluated where relevant
- [ ] Business constraints validated
- [ ] Client-side validation not treated as the security boundary

Result:

PASS / FAIL / N/A

---

# Output Encoding and Sanitization

- [ ] Untrusted output contexts identified
- [ ] HTML handling reviewed
- [ ] JavaScript-related output reviewed where applicable
- [ ] URL handling reviewed where applicable
- [ ] Header generation reviewed where applicable
- [ ] Output encoding appropriate
- [ ] Output sanitization appropriate
- [ ] Unsafe rendering avoided
- [ ] Framework security protections remain enabled
- [ ] User-controlled active content handled safely

Result:

PASS / FAIL / N/A

---

# API Security

Apply when APIs are involved.

- [ ] API authentication enforced
- [ ] API authorization enforced
- [ ] Object-level authorization reviewed
- [ ] Function-level authorization reviewed
- [ ] Input validation exists
- [ ] Output exposure reviewed
- [ ] Privileged endpoints identified
- [ ] State-changing operations identified
- [ ] Error responses do not leak sensitive details
- [ ] Rate limiting evaluated where relevant
- [ ] Resource-consumption risk evaluated
- [ ] Excessive data exposure reviewed
- [ ] API contracts reviewed
- [ ] TLS requirements considered
- [ ] CORS reviewed where relevant
- [ ] API inventory considered
- [ ] Frontend restrictions not used as API security controls

Result:

PASS / FAIL / N/A

---

# Sensitive Data Protection

- [ ] Sensitive data identified
- [ ] Personal data identified where applicable
- [ ] Confidential business data identified where applicable
- [ ] Authentication data identified
- [ ] Data collection reviewed
- [ ] Data access reviewed
- [ ] Data storage reviewed
- [ ] Data transmission reviewed
- [ ] Data exposure reviewed
- [ ] Data retention considered where applicable
- [ ] Data disposal considered where applicable
- [ ] Export behaviour reviewed where applicable
- [ ] Sensitive data not unnecessarily logged
- [ ] Applicable encryption requirements evaluated

Result:

PASS / FAIL / N/A

---

# Secrets and Credentials

- [ ] Secrets not hardcoded
- [ ] Secrets not committed to repositories
- [ ] Secrets not stored in plaintext documentation
- [ ] Secrets not returned by APIs
- [ ] Secrets not included in frontend assets
- [ ] Secrets not written to logs
- [ ] Secrets not exposed through exceptions
- [ ] Real credentials not used in test fixtures
- [ ] Secret-management mechanism identified
- [ ] Secret-management mechanism appropriate to target platform
- [ ] AWS Secrets Manager applicability reviewed when relevant
- [ ] Azure Key Vault applicability reviewed when relevant
- [ ] Kubernetes-integrated secret management applicability reviewed when relevant
- [ ] Corporate secret-management mechanism not invented
- [ ] Least-privilege access to secrets considered

Result:

PASS / FAIL / N/A

---

# Credential and Certificate Lifecycle

Apply when credentials, robot users, technical users, certificates, or keys exist.

- [ ] Credential ownership identified
- [ ] Secure storage identified
- [ ] Rotation requirements considered
- [ ] Expiration considered
- [ ] Revocation considered
- [ ] Certificate lifecycle considered
- [ ] Automation considered where appropriate
- [ ] Service continuity during rotation considered
- [ ] Manual plaintext credential distribution avoided
- [ ] Obsolete or expired credentials rejected

Result:

PASS / FAIL / N/A

---

# Cryptography and Communication Security

- [ ] Data-in-transit protection evaluated
- [ ] Data-at-rest requirements evaluated
- [ ] TLS requirements evaluated
- [ ] Certificate validation preserved
- [ ] Key storage reviewed
- [ ] Key rotation considered
- [ ] Password storage reviewed where applicable
- [ ] Deprecated cryptographic mechanisms avoided
- [ ] Custom cryptography avoided
- [ ] Exact corporate algorithm/key requirements verified before claiming compliance

Result:

PASS / FAIL / N/A

---

# Database Security

Apply when persistence is involved.

- [ ] Parameterized queries used
- [ ] Injection risk reviewed
- [ ] Database permissions reviewed
- [ ] Least Privilege applied
- [ ] Database credentials protected
- [ ] Sensitive fields identified
- [ ] Sensitive data protection reviewed
- [ ] Database error leakage reviewed
- [ ] Data integrity impact evaluated
- [ ] Backup security considered where applicable
- [ ] Audit requirements considered where applicable
- [ ] Arbitrary SQL capabilities explicitly reviewed if present

Result:

PASS / FAIL / N/A

---

# File Security

Apply when file upload, download, or filesystem access exists.

- [ ] File types validated
- [ ] File size limits considered
- [ ] File names handled safely
- [ ] Path traversal considered
- [ ] Storage location reviewed
- [ ] Access permissions reviewed
- [ ] Download authorization reviewed
- [ ] Malicious content risk considered
- [ ] Sensitive data exposure considered
- [ ] Unrestricted filesystem access avoided

Result:

PASS / FAIL / N/A

---

# Error Handling and Information Disclosure

- [ ] Errors fail in a controlled state
- [ ] Stack traces not exposed
- [ ] Internal paths not exposed
- [ ] Database details not exposed
- [ ] Credentials not exposed
- [ ] Tokens not exposed
- [ ] Sensitive configuration not exposed
- [ ] Internal hostnames not unnecessarily exposed
- [ ] Framework details not unnecessarily exposed
- [ ] Confidential business information protected
- [ ] User-facing errors appropriately generic
- [ ] Diagnostic information available securely where necessary

Result:

PASS / FAIL / N/A

---

# Logging and Monitoring

- [ ] Security-relevant events logged where appropriate
- [ ] Authentication failures logged where appropriate
- [ ] Authorization failures logged where appropriate
- [ ] Privileged operations observable where appropriate
- [ ] Unexpected security-relevant failures logged
- [ ] Passwords not logged
- [ ] Secrets not logged
- [ ] Tokens not logged
- [ ] Private keys not logged
- [ ] Sensitive personal information not unnecessarily logged
- [ ] Authentication headers not logged
- [ ] Auditability requirements considered
- [ ] Monitoring implications evaluated
- [ ] Logging does not create additional sensitive-data exposure

Result:

PASS / FAIL / N/A

---

# Dependency and Supply Chain Security

- [ ] Third-party dependencies identified
- [ ] Dependency versions reviewed
- [ ] Known vulnerable components evaluated
- [ ] Unsupported components identified
- [ ] Package origin considered
- [ ] Dependency integrity considered
- [ ] Build dependencies considered
- [ ] Container base images reviewed where applicable
- [ ] Transitive-security impact considered
- [ ] Vulnerable components have remediation or treatment when required
- [ ] Vulnerability not dismissed without contextual analysis

Result:

PASS / FAIL / N/A

---

# SonarQube Detection

Determine whether SonarQube applies.

- [ ] SonarQube configuration searched
- [ ] CI/CD integration searched
- [ ] Analysis execution evidence searched
- [ ] Current analysis result searched

SonarQube:

`DETECTED / NOT DETECTED / NOT DETERMINED`

Configured in CI/CD:

`YES / NO / NOT DETERMINED`

Current analysis evidence:

`AVAILABLE / NOT AVAILABLE / NOT EXECUTED / NOT DETERMINED`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# SonarQube Review

Apply when SonarQube evidence is available.

- [ ] Quality Gate reviewed
- [ ] Security vulnerabilities reviewed
- [ ] Security Hotspots reviewed
- [ ] Relevant security findings reviewed
- [ ] Unresolved findings identified
- [ ] Resolved findings evaluated where necessary
- [ ] Accepted findings and justification reviewed when relevant
- [ ] Affected components identified
- [ ] SonarQube findings assessed in application context
- [ ] Current analysis scope or revision identified when available
- [ ] SonarQube PASS not treated as proof of overall security
- [ ] Findings not mechanically duplicated without security context
- [ ] Material findings incorporated into Security Findings
- [ ] Missing current results explicitly reported

SonarQube Quality Gate:

`PASS / FAIL / NOT AVAILABLE / NOT APPLICABLE`

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# SonarQube Mandatory Gate

Apply when SonarQube is a verified mandatory project, pipeline, or release gate.

- [ ] Mandatory-gate requirement verified
- [ ] Analysis execution verified
- [ ] Quality Gate result available
- [ ] Failed mandatory gate escalated
- [ ] Material unresolved findings assessed
- [ ] Remediation status reviewed
- [ ] Missing evidence not treated as PASS

If SonarQube is unavailable but mandatory:

`NEEDS MORE INFO`

or:

`FAIL`

according to the verified project requirement and available evidence.

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Other Static Analysis

Apply when additional static-analysis tooling exists.

- [ ] Tool identified
- [ ] Execution evidence available
- [ ] Relevant security findings reviewed
- [ ] Material findings assessed
- [ ] Missing evidence reported
- [ ] Automated findings not treated as complete security assessment

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Dependency Analysis / SCA

Apply when dependency-analysis tooling exists.

- [ ] Tool identified
- [ ] Current execution evidence available
- [ ] Known vulnerabilities reviewed
- [ ] Severity reviewed
- [ ] Affected version identified
- [ ] Fix or upgrade path considered
- [ ] Accepted findings supported by evidence
- [ ] Unresolved material findings reported

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Dynamic Security Testing

Apply when dynamic security testing is required or available.

- [ ] Test scope identified
- [ ] Execution evidence available
- [ ] Findings reviewed
- [ ] Severity reviewed
- [ ] Remediation status reviewed
- [ ] Required re-test identified
- [ ] Missing result not treated as PASS

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Ethical Hacking / Assurance Applicability

Determine applicability before production when relevant.

- [ ] Application exposure identified
- [ ] Public/insecure-network exposure evaluated
- [ ] Corporate Assurance requirements searched
- [ ] Security Annex requirement evaluated
- [ ] Ethical Hacking requirement evaluated
- [ ] Application-specific Risk Assessment considered
- [ ] Assurance requirement not invented
- [ ] Applicability supported by evidence

Applicability:

`REQUIRED / NOT REQUIRED / NOT DETERMINED / NOT APPLICABLE`

Result:

PASS / FAIL / N/A

---

# Ethical Hacking / Assurance Results

Apply when Assurance or Ethical Hacking is required or evidence exists.

- [ ] Assessment evidence available
- [ ] Assessment scope understood
- [ ] Critical findings reviewed
- [ ] High findings reviewed
- [ ] Remediation plans reviewed
- [ ] Compensating controls reviewed where applicable
- [ ] Re-check requirements identified
- [ ] Re-check evidence reviewed where available
- [ ] Residual risk evaluated
- [ ] Finding not considered closed solely because remediation was proposed
- [ ] Formal risk acceptance verified where relevant

Result:

PASS / FAIL / N/A / NOT EXECUTED

---

# Infrastructure and Platform Security

Infrastructure implementation remains primarily owned by DevOps Engineer.

Security review includes:

- [ ] Access controls reviewed
- [ ] Identity reviewed
- [ ] Secret management reviewed
- [ ] Environment configuration reviewed
- [ ] External exposure evaluated
- [ ] Least privilege considered
- [ ] TLS reviewed where relevant
- [ ] Container security considered where relevant
- [ ] Network boundaries considered
- [ ] Ingress/egress implications considered
- [ ] Runtime isolation considered where relevant
- [ ] Security concerns coordinated with DevOps Engineer

Result:

PASS / FAIL / N/A

---

# Frontend Security

Apply when frontend code is affected.

- [ ] Client-side validation not treated as security enforcement
- [ ] Authorization not enforced solely in frontend
- [ ] XSS risk reviewed
- [ ] Unsafe HTML reviewed
- [ ] DOM injection reviewed
- [ ] Redirect handling reviewed where relevant
- [ ] Browser storage reviewed
- [ ] Token handling reviewed
- [ ] Sensitive client-side information reviewed
- [ ] Frontend dependency security reviewed
- [ ] Backend enforcement exists for security-sensitive rules

Result:

PASS / FAIL / N/A

---

# Backend Security

Apply when backend code is affected.

- [ ] Input validation reviewed
- [ ] Authentication reviewed
- [ ] Authorization reviewed
- [ ] Business-operation authorization reviewed
- [ ] Secret handling reviewed
- [ ] Database access reviewed
- [ ] External integrations reviewed
- [ ] Error handling reviewed
- [ ] Logging reviewed
- [ ] Cryptography reviewed where applicable
- [ ] Sensitive-data exposure reviewed
- [ ] Dependency security reviewed

Result:

PASS / FAIL / N/A

---

# AI / LLM Security

Apply only when the target application contains material AI or LLM capabilities.

Do NOT apply merely because Copilot was used to develop the application.

- [ ] Prompt injection reviewed
- [ ] Indirect prompt injection reviewed
- [ ] Context poisoning reviewed
- [ ] Sensitive data leakage reviewed
- [ ] Excessive context exposure reviewed
- [ ] Model output trust reviewed
- [ ] Tool permissions reviewed
- [ ] Authorization bypass through model/tool actions reviewed
- [ ] Data exfiltration risk considered
- [ ] Untrusted retrieved content handled as untrusted
- [ ] Excessive model autonomy reviewed

Result:

PASS / FAIL / N/A

---

# Agentic System Security

Apply only when the target application contains agentic capabilities.

- [ ] Agent responsibilities understood
- [ ] Agent authority reviewed
- [ ] Agent permissions reviewed
- [ ] Tool permissions reviewed
- [ ] Delegation boundaries reviewed
- [ ] Human approval controls evaluated
- [ ] Execution boundaries reviewed
- [ ] Secret access reviewed
- [ ] Agent memory reviewed where applicable
- [ ] External data access reviewed
- [ ] Autonomous production-change risk reviewed
- [ ] Traceability reviewed
- [ ] Agent actions cannot bypass application authorization

Result:

PASS / FAIL / N/A

---

# MCP Security

Apply only when MCP exists or is explicitly proposed.

- [ ] MCP requirement identified
- [ ] Tool boundaries defined
- [ ] Tool permissions reviewed
- [ ] Resource exposure reviewed
- [ ] Prompt exposure reviewed where applicable
- [ ] Transport reviewed
- [ ] Authentication reviewed
- [ ] Authorization reviewed
- [ ] Least Privilege applied
- [ ] Trust boundaries reviewed
- [ ] State-changing tools identified
- [ ] Side effects reviewed
- [ ] External MCP content treated as untrusted
- [ ] Secret exposure reviewed
- [ ] Command execution reviewed if present
- [ ] Filesystem access reviewed if present
- [ ] Database access reviewed if present
- [ ] Network access reviewed if present
- [ ] Generic unrestricted MCP tools avoided
- [ ] Unintended tool-execution risk reviewed

Result:

PASS / FAIL / N/A

---

# OWASP Review

Apply relevant OWASP threat categories.

- [ ] Broken Access Control evaluated
- [ ] Cryptographic Failures evaluated
- [ ] Injection risks evaluated
- [ ] Insecure Design reviewed
- [ ] Security Misconfiguration reviewed
- [ ] Vulnerable Components reviewed
- [ ] Identification and Authentication Failures reviewed
- [ ] Software and Data Integrity Failures reviewed
- [ ] Logging and Monitoring Failures reviewed

Additional applicable OWASP guidance considered where relevant.

OWASP findings are not automatically classified as corporate requirements.

Result:

PASS / FAIL / N/A

---

# Vulnerability Management

For material findings verify:

- [ ] Finding source identified
- [ ] Identifier recorded when available
- [ ] Affected component identified
- [ ] Severity recorded
- [ ] Tool-reported severity preserved when applicable
- [ ] Contextual security severity recorded when necessary
- [ ] Exploitability considered
- [ ] Business/security impact considered
- [ ] Remediation defined
- [ ] Compensating control documented where applicable
- [ ] Validation method defined
- [ ] Remediation status supported by evidence
- [ ] Residual risk evaluated
- [ ] Formal risk acceptance verified when necessary

Result:

PASS / FAIL / N/A

---

# Security Evidence Summary

Corporate Requirements Reviewed:

`_____________________`

Project-Specific Requirements Reviewed:

`_____________________`

Risk Assessment:

`AVAILABLE / NOT AVAILABLE / NOT APPLICABLE / NOT DETERMINED`

Security Annex:

`AVAILABLE / NOT AVAILABLE / NOT APPLICABLE / NOT DETERMINED`

SonarQube:

`DETECTED / NOT DETECTED / NOT DETERMINED`

SonarQube Quality Gate:

`PASS / FAIL / NOT AVAILABLE / NOT APPLICABLE`

Dependency Analysis:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Dynamic Security Testing:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Ethical Hacking / Assurance:

`REQUIRED / NOT REQUIRED / NOT DETERMINED / NOT APPLICABLE`

Ethical Hacking Result:

`PASS / FAIL / NOT EXECUTED / NOT AVAILABLE / NOT APPLICABLE`

Missing Security Evidence:

`_____________________`

---

# Critical Security Gates

The Security Engineer must recommend BLOCK when an applicable unresolved critical condition exists.

- [ ] No unresolved critical vulnerability
- [ ] No critical authentication bypass
- [ ] No critical authorization bypass
- [ ] No critical privilege escalation
- [ ] No exposed sensitive credentials
- [ ] No critical secret-management failure
- [ ] No critical sensitive-data exposure
- [ ] No critical injection vulnerability
- [ ] No unsafe critical production exposure
- [ ] No verified mandatory security control missing
- [ ] No failed mandatory security assurance without approved treatment
- [ ] No unresolved critical Ethical Hacking finding without formal risk acceptance
- [ ] No unresolved mandatory security gate failure
- [ ] No mandatory SonarQube gate falsely represented as PASS

If any applicable item fails:

Security Gate = FAILED

Final Recommendation = BLOCK

unless formal treatment or risk acceptance exists through the applicable governance process.

The Security Engineer cannot create that risk acceptance.

Result:

PASS / FAIL / N/A

---

# Security Findings Summary

Critical Findings:

`_____________________`

High Findings:

`_____________________`

Medium Findings:

`_____________________`

Low Findings:

`_____________________`

Do not fabricate counts.

Use only findings actually identified through available evidence or review.

---

# Security Risk Assessment

Highest Risk:

LOW

MEDIUM

HIGH

CRITICAL

Risk:

`_____________________`

Main Risk Drivers:

`_____________________`

Residual Risk:

`_____________________`

---

# Final Security Recommendation

Allowed values:

APPROVE

CONDITIONAL APPROVAL

BLOCK

NEEDS MORE INFO

Recommendation:

`_____________________`

---

# Security Gate Result

Allowed values:

PASSED

CONDITIONAL

FAILED

Result:

`_____________________`

---

# Security Engineer Sign-Off

Reviewer:

`_____________________`

Date:

`_____________________`

Decision:

`PASSED / CONDITIONAL / FAILED`

Recommendation:

`APPROVE / CONDITIONAL APPROVAL / BLOCK / NEEDS MORE INFO`

Conditions:

`________________________________________________`

`________________________________________________`

Missing Evidence:

`________________________________________________`

Comments:

`________________________________________________`

`________________________________________________`

---

# Definition of Security Readiness

A solution is considered security-ready for its intended lifecycle when:

- Security context is understood.
- Applicable corporate security requirements have been investigated.
- Project-specific security requirements are identified.
- Corporate requirements are distinguished from industry practices.
- Relevant SSDLC controls have been considered.
- Trust boundaries are understood.
- Authentication is reviewed.
- Authorization is reviewed.
- Least Privilege and Deny by Default are considered.
- Inputs are appropriately validated.
- Client-side controls are not treated as authoritative security controls.
- Secrets are protected.
- Credential and certificate lifecycle is considered where applicable.
- Sensitive data is protected.
- Cryptographic requirements are evaluated.
- Error handling does not create unacceptable information disclosure.
- Logging does not expose sensitive information.
- Dependency security is evaluated.
- SonarQube availability has been investigated.
- Available SonarQube evidence has been reviewed.
- SonarQube PASS has not been treated as proof of overall security.
- Required security tooling has been executed or missing evidence is explicit.
- Ethical Hacking / Assurance applicability has been determined where relevant.
- Existing Ethical Hacking findings have been considered where applicable.
- MCP security has been reviewed when MCP is involved.
- AI/LLM security has been reviewed when AI/LLM capability exists.
- Agentic security has been reviewed when the target system is agentic.
- No unresolved critical security blocker remains without formally approved treatment.
- Security residual risk is understood.
- Missing security evidence is explicit.
- Security recommendation is traceable to verified evidence.