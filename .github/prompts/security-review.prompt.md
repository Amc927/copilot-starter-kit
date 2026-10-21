---
name: Security Review Prompt
description: Standardized evidence-based security review framework aligned with verified Enel/Endesa security requirements, SSDLC principles, SonarQube evidence, OWASP practices, Assurance processes, API security, MCP security, and AI/LLM security.
model: Auto (copilot)
---

# Security Review Prompt

## Objective

Perform an evidence-based security assessment of the provided change, application, architecture, implementation, API, integration, infrastructure component, MCP capability, AI/LLM capability, or agentic system.

Identify:

- Exploitable vulnerabilities
- Security weaknesses
- Broken trust boundaries
- Authentication risks
- Authorization risks
- Data-protection concerns
- Secret-management risks
- Dependency and supply-chain risks
- Infrastructure risks
- API risks
- MCP risks
- AI/LLM risks
- Missing verified security controls
- Missing security evidence

Focus on real-world security risk and verified requirements.

Do not invent security requirements, corporate controls, tool execution, findings, or assessment evidence.

---

# Evidence-First Rule

Every material security conclusion must be supported by available evidence.

Evidence may include:

- Repository code
- Repository configuration
- Architecture documentation
- Enel/Endesa security documentation
- Risk Assessment
- Cyber Security Risk Treatment Analysis
- Security Annex
- HLD
- Detailed Technical Design
- Platform documentation
- SonarQube results
- Dependency-analysis results
- Dynamic-security-testing results
- API-security-testing results
- Ethical Hacking findings
- Penetration-testing findings
- Existing vulnerability reports
- Security-remediation evidence

Never convert missing evidence into PASS.

When information required for a safe security decision cannot be verified, use:

`NEEDS MORE INFO`

---

# Security Evidence Classification

Always distinguish between the following sources.

## Corporate Requirement

A verified Enel/Endesa security requirement.

## Project-Specific Requirement

A verified requirement explicitly applicable to the application or project.

Possible sources include:

- Risk Assessment
- Cyber Security Risk Treatment Analysis
- Security Annex
- HLD
- Detailed Technical Design
- Platform configuration
- Ethical Hacking findings
- Approved remediation plans

## Security Tooling Evidence

Verified results from:

- SonarQube
- Static analysis
- Dependency analysis
- Dynamic security testing
- API security testing
- Ethical Hacking
- Penetration testing

## Industry Security Practice

Examples include:

- OWASP
- CWE
- NIST
- Established secure-development practices

## Security Recommendation

Professional security judgement produced by the Security Engineer.

Never represent an industry recommendation as a mandatory Enel/Endesa requirement unless supporting corporate evidence exists.

---

# Corporate Evidence Rule

For an Enel/Endesa corporate application, investigate available evidence for applicable security requirements.

Search for:

- Security Guidelines
- Security Annex
- Risk Assessment
- Cyber Security Risk Treatment Analysis
- HLD
- Detailed Technical Design
- Platform security documentation
- Authentication documentation
- Authorization documentation
- Secret-management documentation
- Ethical Hacking reports
- Vulnerability reports
- Remediation plans

If a claimed corporate requirement cannot be verified, report:

`Corporate security requirement not verified - validation required.`

Do not invent:

- Corporate security controls
- SecurePlat configuration
- Authentication flows
- Authorization models
- Secret-management requirements
- Cryptographic requirements
- Ethical Hacking requirements
- Security gates
- SonarQube policies

---

# Security Review Principles

Apply:

- Security by Design
- Zero Trust
- Least Privilege
- Deny by Default
- Defense in Depth
- Assume Breach
- Secure Defaults
- Fail Securely
- Minimize Attack Surface
- Evidence-Based Security Decisions

Recommendations must be:

- Actionable
- Risk-based
- Technically justified
- Traceable to evidence

---

# Review Context

Before performing the review, establish the available context.

## Application Lifecycle

Identify when available:

- Experiment
- Prototype / PoC
- MVP
- Production

Security depth must reflect lifecycle, exposure, data sensitivity, and risk.

Prototype status does not justify:

- Exposed credentials
- Broken authentication
- Broken authorization
- Uncontrolled access to protected systems
- Unprotected sensitive data

## System Type

Classify the system as one or more of:

- Web Application
- Backend Service
- API
- Microservice
- Database
- Mobile Application
- Desktop Application
- Infrastructure Component
- Cloud Service
- Streamlit Application
- Angular Application
- MCP Server
- MCP Client
- AI/LLM Application
- RAG System
- AI Agent
- Multi-Agent System
- Other

Do not activate AI, MCP, or agentic security review merely because Copilot was used during development.

## Data Context

Identify the information processed when evidence is available.

Examples include:

- Public information
- Internal information
- Personal data
- Sensitive data
- Confidential business information
- Credentials
- Tokens
- Certificates
- Internal documents
- Financial information
- Intellectual property

Do not invent a corporate data classification.

If the review depends on a data classification that cannot be verified, report it as missing information.

---

# Trust Boundaries

Identify relevant boundaries between:

- Users
- Browsers
- Frontend
- Backend
- APIs
- Databases
- Internal services
- External services
- Third parties
- Cloud services
- Administrative interfaces
- MCP servers
- MCP clients
- AI agents
- Agent tools

For each relevant boundary evaluate:

- Authentication
- Authorization
- Data exchanged
- Secrets
- Privilege
- Input trust
- Failure behaviour

---

# Secure Software Development Lifecycle Review

Evaluate security evidence throughout the applicable software lifecycle.

## Planning

Review:

- Security requirements
- Data sensitivity
- Exposure
- Trust boundaries
- Corporate requirements
- Project-specific requirements

## Design

Review:

- Authentication
- Authorization
- Data flows
- Integration boundaries
- Secret architecture
- Cryptography
- Attack surface
- Failure behaviour

## Development

Review:

- Secure Coding
- Input validation
- Output handling
- Error handling
- Secret handling
- Dependencies
- Security-sensitive implementation

## Testing

Review available:

- SonarQube
- Static analysis
- Dependency analysis
- Dynamic security testing
- API security testing
- Security regression testing
- Ethical Hacking
- Assurance

## Deployment

Review:

- Secure configuration
- Secret injection
- Network exposure
- Permissions
- TLS
- Runtime security
- Mandatory security gates

## Maintenance

Review when relevant:

- Vulnerability remediation
- Dependency lifecycle
- Certificate lifecycle
- Credential rotation
- Security incidents
- Security-relevant changes

---

# Enel/Endesa Secure Coding Review

When supported by applicable corporate evidence, evaluate:

- Input validation
- Output encoding
- Output sanitization
- Authentication
- Password management
- Session management
- Access control
- Deny by Default
- Least Privilege
- Cryptographic practices
- Error handling
- Logging
- Data protection
- Communication security
- System configuration
- Database security
- File management
- Memory management where relevant
- Modularity
- Backdoor prevention
- Protection considerations for source code and executables
- Documentation
- Component inventory where required

Not every control applies to every application.

Record applicability and supporting evidence.

---

# Authentication Review

Review:

- Identity verification
- Authentication mechanism
- Session management
- Token handling
- Credential handling
- Expired credentials
- Default accounts
- Machine identities
- Service accounts
- Robot users
- Certificate authentication where applicable
- MFA where applicable

Determine:

- Can authentication be bypassed?
- Are credentials protected?
- Are tokens handled securely?
- Are expired credentials rejected?
- Are default accounts protected?
- Are authentication errors safe?
- Is centralized authentication required by verified evidence?

Do not invent corporate authentication mechanisms.

---

# Authorization Review

Apply:

- Least Privilege
- Deny by Default
- Explicit permission evaluation

Review:

- Role enforcement
- Permission validation
- Object-level authorization
- Function-level authorization
- Resource-level authorization
- Administrative operations
- Service-to-service authorization
- Data authorization

Determine:

- Can users access resources belonging to others?
- Can privileges be escalated?
- Are checks applied at the authoritative boundary?
- Are privileged operations explicitly protected?
- Can frontend restrictions be bypassed?

Frontend controls are not authoritative authorization boundaries.

When verified Enel Digital Platform documentation indicates that SecurePlat is applicable, inspect the available integration evidence.

Never invent SecurePlat integration details.

---

# Input Validation Review

Treat external input as untrusted.

Review:

- Types
- Schemas
- Formats
- Length
- Ranges
- Enumerations
- Identifiers
- URLs
- Paths
- Files
- API payloads
- External-service responses
- Business constraints

Determine:

- Can malicious input bypass validation?
- Can an injection attack occur?
- Is validation performed at the authoritative boundary?
- Are external responses trusted without validation?
- Are file uploads sufficiently constrained?

Client-side validation does not replace backend validation.

---

# Output Encoding and Sanitization Review

Review applicable contexts:

- HTML
- JavaScript
- URLs
- HTTP headers
- Generated files
- Logs
- Generated content

Determine:

- Can untrusted content reach an active context?
- Are framework protections preserved?
- Is unsafe rendering present?
- Is sanitization appropriate to the output context?

Do not recommend bypassing framework security controls without justified evidence.

---

# Secrets and Credential Review

Search for exposure of:

- Passwords
- API keys
- Consumer secrets
- Access tokens
- Refresh tokens
- Database credentials
- Private keys
- Keystore passwords
- Robot credentials
- Certificate private material

Review whether secrets are:

- Hardcoded in code
- Committed to repositories
- Stored in plaintext documentation
- Included in frontend assets
- Exposed in logs
- Exposed through exceptions
- Returned through APIs
- Embedded in prompts
- Included in test fixtures

Identify the verified secret-management mechanism.

For Enel Digital Platform, investigate approved project or platform evidence for mechanisms such as:

- AWS Secrets Manager
- Azure Key Vault
- Kubernetes-integrated secret management

Do not assume that the same secret-management technology applies to every project.

---

# Credential and Certificate Lifecycle

Review when applicable:

- Storage
- Rotation
- Expiration
- Revocation
- Ownership
- Automation
- Service continuity during rotation

Report plaintext or uncontrolled credential distribution as a security concern.

Do not invent mandatory rotation intervals.

---

# Data Protection Review

Review:

- Collection
- Access
- Storage
- Transmission
- Logging
- Export
- Retention
- Disposal
- Backup when relevant

Determine:

- Is sensitive information exposed?
- Is access properly restricted?
- Is protection aligned with verified requirements?
- Is unnecessary sensitive data returned or logged?

Do not invent corporate classifications, retention periods, or encryption requirements.

---

# Cryptography and Communication Security

Review:

- Data in transit
- Data at rest when required
- TLS
- Certificate validation
- Key storage
- Key rotation
- Password storage
- Cryptographic dependency lifecycle

Never recommend:

- Custom cryptography
- Disabled certificate validation
- Deprecated cryptography knowingly

When exact corporate algorithms, versions, or key sizes are required, verify them in applicable documentation.

---

# Error Handling and Information Disclosure

Review whether error behaviour exposes:

- Stack traces
- Internal paths
- Database details
- Credentials
- Tokens
- Sensitive configuration
- Internal hostnames unnecessarily
- Framework internals unnecessarily
- Confidential business information

Systems should fail in a controlled state.

Operational diagnostics must not become an information-disclosure channel.

---

# API Security Review

Apply when APIs exist.

Review:

- Authentication
- Authorization
- Object-level authorization
- Function-level authorization
- Input validation
- Output exposure
- State-changing operations
- Error handling
- TLS
- Rate limiting where relevant
- Resource-consumption controls
- CORS where relevant
- API inventory
- Sensitive operations

Determine:

- Can the API be invoked without appropriate authorization?
- Can identifiers expose another user's data?
- Does the API expose excessive information?
- Can privileged operations be triggered unexpectedly?
- Can resource consumption be abused?

---

# Database Security Review

Apply when databases are involved.

Review:

- Parameterized queries
- Injection risk
- Database permissions
- Least Privilege
- Credentials
- Sensitive fields
- Database error exposure
- Data integrity
- Audit requirements when applicable
- Arbitrary-query functionality

Generic arbitrary-SQL capabilities require explicit security scrutiny.

---

# File Security Review

Apply when file handling or filesystem access is involved.

Review:

- File type validation
- File size
- File naming
- Storage location
- Path traversal
- Malicious content
- Access permissions
- Download authorization
- Data exposure

Unrestricted filesystem access is a high-risk capability.

---

# Dependency and Supply Chain Review

Review:

- Dependency versions
- Known vulnerabilities
- Unsupported components
- Package origins
- Dependency integrity
- Build dependencies
- Container base images when applicable
- Third-party integrations

Use dependency-analysis or SCA evidence when available.

Do not ignore known vulnerabilities solely because exploitation has not yet been demonstrated.

Assess the risk in context.

---

# SonarQube Review

Always investigate whether SonarQube is available for the project.

Determine:

- Is SonarQube configured?
- Is it integrated into CI/CD?
- Was analysis executed?
- Are current results available?
- Does the analysis correspond to the relevant revision when identifiable?
- Is the Quality Gate available?
- Are vulnerabilities available?
- Are Security Hotspots available?
- Are unresolved security findings present?

Report:

```text
SonarQube detected:
YES / NO / NOT DETERMINED

Configured in CI/CD:
YES / NO / NOT DETERMINED

Analysis evidence:
AVAILABLE / NOT AVAILABLE / NOT EXECUTED / NOT DETERMINED

Quality Gate:
PASS / FAIL / NOT AVAILABLE / NOT APPLICABLE
```

Never invent SonarQube execution or findings.

---

# SonarQube Interpretation

When SonarQube evidence exists:

1. Review the Quality Gate.
2. Review security vulnerabilities.
3. Review relevant Security Hotspots.
4. Identify unresolved material findings.
5. Evaluate findings in the application context.
6. Review available remediation evidence.

A SonarQube Quality Gate PASS does not prove that the complete application is secure.

SonarQube does not replace manual review of:

- Authentication design
- Authorization design
- Business-logic security
- Trust boundaries
- Data flows
- Secret-management architecture
- Abuse cases
- MCP permissions
- Agent authority
- AI/LLM threats

Do not duplicate every SonarQube issue mechanically.

Include material issues and add the relevant security context.

---

# SonarQube Mandatory Gate

Determine whether SonarQube is a verified mandatory project, pipeline, or release gate.

If mandatory:

- Verify execution.
- Verify the Quality Gate.
- Review blocking findings.
- Report missing evidence.
- Do not treat missing analysis as PASS.

If SonarQube is not verified as mandatory:

- Use available results as security evidence.
- Do not invent a corporate blocking policy.

Always apply:

`SonarQube PASS does not equal complete security approval.`

---

# Other Security Tooling

Review available evidence from:

## Static Analysis

Other repository-configured static-analysis tools.

## Dependency Analysis

Dependency or software-composition-analysis results.

## Dynamic Security Testing

DAST or equivalent verified testing evidence.

## API Security Testing

Available API-security-testing evidence.

## Ethical Hacking or Penetration Testing

Available Assurance or penetration-testing findings.

For each tool:

- Verify execution evidence.
- Review material findings.
- Do not invent results.
- Do not treat missing evidence as PASS.

---

# Ethical Hacking and Assurance Applicability

When production exposure or verified corporate or project requirements make it relevant, determine whether any of the following are required:

- Assurance Check
- Ethical Hacking
- Web Application Penetration Testing
- API security testing
- Security Annex review
- Re-check after remediation

Pay particular attention to applications exposed to public or otherwise insecure networks.

Allowed result:

```text
REQUIRED
NOT REQUIRED
NOT DETERMINED
NOT APPLICABLE
```

Do not claim Ethical Hacking is mandatory for every application without verified evidence.

---

# Ethical Hacking and Assurance Findings

When evidence exists, review:

- Scope
- Finding identifier
- Severity
- Affected component
- Finding status
- Remediation plan
- Compensating controls
- Required re-check
- Re-check evidence
- Residual risk

Do not consider a finding closed merely because remediation was proposed.

Use available validation or re-check evidence.

---

# OWASP Review

Use OWASP as applicable industry security guidance.

## Broken Access Control

Review authorization boundaries and privilege escalation.

## Cryptographic Failures

Review protection of sensitive information and cryptographic usage.

## Injection

Review applicable:

- SQL Injection
- Command Injection
- Template Injection
- Other interpreter injection

Prompt injection belongs primarily to AI/LLM security analysis.

## Insecure Design

Review security assumptions and trust boundaries.

## Security Misconfiguration

Review:

- Runtime configuration
- Services
- Environments
- Network exposure
- Default settings

## Vulnerable Components

Review:

- Dependencies
- Unsupported versions
- Third-party integrations

## Authentication Failures

Review identity and session controls.

## Software and Data Integrity Failures

Review:

- Build integrity
- Dependency integrity
- Deployment integrity
- Supply chain

## Logging and Monitoring Failures

Review:

- Security events
- Auditability
- Incident visibility

Do not describe an OWASP recommendation as an Enel/Endesa corporate requirement unless verified.

---

# AI and LLM Security Review

Apply only when the target solution contains material AI or LLM functionality.

Review:

## Prompt Injection

Can direct user input manipulate model behaviour?

## Indirect Prompt Injection

Can retrieved or external content manipulate behaviour?

## Context Poisoning

Can untrusted knowledge influence future decisions?

## Tool Abuse

Can the model invoke tools outside its required authority?

## Data Leakage

Can sensitive information be exposed through:

- Prompts
- Context
- Retrieval
- Tool calls
- Model outputs

## Excessive Autonomy

Can AI actions occur without appropriate controls or human approval?

## Model Output Trust

Is model output treated as trusted data without validation?

Do not apply AI/LLM review merely because Copilot was used during development.

---

# MCP Security Review

Apply only when MCP exists or is explicitly proposed.

Review:

## Tool Permissions

Are tools restricted through Least Privilege?

## Tool Boundaries

Does each tool expose only the required capability?

## State-Changing Tools

Are side effects explicit and protected?

## Resource Access

Can resources expose sensitive information?

## Authentication

How is the client or caller authenticated?

## Authorization

What capabilities may the caller invoke?

## Transport

Is the transport appropriate to the exposure and architecture?

## External Content

Is retrieved content treated as untrusted data?

## Command Execution

Is unrestricted command execution exposed?

## Filesystem Access

Can tools access files outside approved boundaries?

## Database Access

Are generic arbitrary database queries exposed?

## Secret Exposure

Can responses, prompts, tools, or resources expose secrets?

Avoid generic unrestricted MCP capabilities.

---

# Agentic System Security Review

Apply only when the target solution contains agentic behaviour.

Review:

- Agent authority
- Agent permissions
- Tool permissions
- Delegation
- Human approval
- Production access
- External data
- Secret access
- Memory
- Traceability
- Autonomous actions

Agents must not bypass application authorization or applicable governance.

---

# Risk Classification

Use:

```text
CRITICAL
HIGH
MEDIUM
LOW
```

Severity must reflect:

- Evidence
- Exploitability
- Impact
- Existing controls
- Exposure
- Data sensitivity
- Application context

Do not inflate severity to gain prioritization.

Do not silently modify a severity reported by a security tool.

If contextual security severity differs from tool-reported severity, report both and explain the difference.

---

# Security Blocking Rules

Recommend BLOCK when an applicable unresolved condition exists, including:

- Critical authentication bypass
- Critical authorization bypass
- Critical privilege escalation
- Unresolved critical vulnerability
- Exposed sensitive credentials
- Critical secret-management failure
- Critical sensitive-data exposure
- Critical injection vulnerability
- Unsafe critical production exposure
- Missing verified mandatory corporate security control
- Failed mandatory security assurance
- Unresolved critical Ethical Hacking finding without formal treatment
- Failed verified mandatory security gate with blocking findings

The Security Engineer cannot create or assume formal risk acceptance.

---

# Missing Information Rule

Use:

`NEEDS MORE INFO`

when security-critical information cannot be verified.

Examples:

- Authentication unknown
- Authorization unknown
- Data sensitivity unknown
- Exposure unknown
- Required corporate evidence unavailable
- Mandatory SonarQube result unavailable
- Ethical Hacking applicability unresolved
- Critical integration behaviour unknown

Do not guess the missing security posture.

---

# Final Output Format

## Executive Summary

Provide the overall security assessment.

## Security Context

Report:

- Application type
- Lifecycle
- Technology
- Exposure
- Data context
- Authentication
- Authorization
- Platform

## Evidence

### Corporate Requirements

List only verified corporate requirements.

### Project-Specific Requirements

List verified project-specific requirements.

### Industry Security Practices

List applicable external security practices.

### Missing Evidence

List unavailable evidence.

## Threat Model

Document:

- Assets
- Trust boundaries
- Entry points
- Privileged operations
- Attack surfaces
- Material abuse scenarios

## Secure Coding Review

Summarize applicable Secure Coding concerns.

## SonarQube Evidence

Report:

- Detected
- CI/CD integration
- Analysis evidence
- Quality Gate
- Vulnerabilities
- Security Hotspots
- Unresolved material findings

## Additional Security Tooling

Report applicable:

- Static analysis
- Dependency analysis
- Dynamic security testing
- API security testing

## Ethical Hacking and Assurance

Report:

- Applicability
- Evidence
- Findings
- Re-check status
- Residual risk

## Findings

For every material finding report:

- Identifier when available
- Source
- Severity
- Tool severity when applicable
- Issue
- Evidence
- Exploitability
- Impact
- Required remediation
- Validation method
- Status
- Residual risk

## Secrets and Credentials

Report relevant secret-management and credential-lifecycle concerns.

## API Security

Report when applicable.

## MCP Security

Report when applicable.

## AI and LLM Security

Report when applicable.

## Agentic Security

Report when applicable.

## Security Gate Result

Exactly one:

```text
PASSED
CONDITIONAL
FAILED
```

## Risk Summary

Report:

- Highest severity
- Overall residual risk
- Main risk drivers

Do not fabricate finding counts.

## Conditions

List required remediation and follow-up actions.

## Missing Information

List all security-critical unresolved information.

## Final Recommendation

Exactly one:

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

Provide concise evidence-based justification.

---

# Success Criteria

A security review is complete when:

- Security context has been established.
- Application lifecycle has been considered.
- Relevant corporate security evidence has been investigated.
- Project-specific requirements have been identified.
- Corporate requirements have been distinguished from industry recommendations.
- Trust boundaries have been identified.
- Attack surfaces have been evaluated.
- Authentication has been reviewed.
- Authorization has been reviewed.
- Least Privilege and Deny by Default have been considered.
- Applicable Secure Coding controls have been reviewed.
- Secret management has been evaluated.
- Sensitive data has been evaluated.
- Dependency and supply-chain security has been considered.
- SonarQube availability has been investigated.
- Available SonarQube evidence has been reviewed.
- SonarQube PASS has not been treated as proof of complete security.
- Mandatory SonarQube requirements have not been invented.
- Additional security-tooling evidence has been reviewed when available.
- Ethical Hacking or Assurance applicability has been evaluated when relevant.
- Existing Ethical Hacking findings have been considered when relevant.
- MCP security has been reviewed when MCP exists.
- AI/LLM security has been reviewed when AI/LLM functionality exists.
- Agentic security has been reviewed when agentic functionality exists.
- Findings are evidence-based.
- Risks are classified.
- Remediation is explicit.
- Residual risk is documented.
- Missing information is explicit.
- Security Gate has been produced.
- Final recommendation is traceable to evidence.

The review must focus on real security risk rather than purely theoretical concerns.