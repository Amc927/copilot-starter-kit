---
name: "Endesa Corporate Angular Engineering"
description: "Engineering standards for Angular applications using verified Endesa corporate frontend libraries, components, styles, and conventions."
---

# Endesa Corporate Angular Engineering Skill

## Purpose

This skill provides engineering standards and implementation guidance for frontend applications built with Angular and the corporate frontend libraries, components, styles, patterns, and design standards available within Endesa projects.

The primary objective of this skill is to ensure that Angular applications developed for Endesa reuse the approved corporate Angular ecosystem whenever it is available in the repository or in accessible project documentation.

It applies to:

- Angular applications
- Endesa corporate web applications
- Internal business applications
- Corporate user interfaces
- Forms
- Dashboards
- Data management interfaces
- REST API consumers
- Shared frontend components
- Existing Angular application maintenance
- New Angular frontend development

---

# Core Corporate Principle

When an Endesa Angular project provides corporate libraries, those libraries are the DEFAULT implementation option.

The agent must prefer:

1. Existing Endesa corporate Angular components.
2. Existing Endesa corporate libraries.
3. Existing Endesa design system components.
4. Existing Endesa styles and themes.
5. Existing corporate design tokens.
6. Existing shared utilities and services.
7. Existing corporate patterns already used by the repository.

before proposing generic alternatives.

Do NOT recreate functionality already available through an approved Endesa corporate library.

---

# Critical Anti-Hallucination Rule

Never invent:

- Endesa package names
- Corporate npm packages
- Corporate Angular components
- Corporate services
- Corporate directives
- Corporate pipes
- Corporate modules
- Corporate APIs
- Design tokens
- CSS classes
- Themes
- Internal npm registries
- Internal documentation
- Authentication libraries
- Internal URLs
- Corporate standards

A corporate library or component may only be referenced as an existing implementation when evidence can be found in:

- `package.json`
- Lock files
- Source imports
- Existing components
- Existing modules
- Existing configuration
- README files
- Documentation stored in the repository
- Corporate documentation explicitly provided to the agent

If evidence cannot be found, report:

`CORPORATE LIBRARY INFORMATION REQUIRED`

and do not fabricate an implementation.

---

# Activation Rules

Use this skill when:

- An Angular workspace exists.
- `angular.json` is present.
- Angular dependencies exist in `package.json`.
- The user explicitly requests Angular.
- The user explicitly requests the Endesa corporate Angular libraries.
- Endesa corporate frontend dependencies are detected.
- Corporate frontend components are already used by the application.
- The Solution Architect selects Angular for the frontend.

For Endesa projects, always investigate whether corporate Angular libraries are available before proposing generic UI libraries or custom components.

---

# Mandatory Repository Inspection

Before recommending, designing, modifying, or generating Angular code, inspect the repository.

At minimum inspect:

- `package.json`
- `package-lock.json`
- `yarn.lock`
- `pnpm-lock.yaml`
- `angular.json`
- `tsconfig.json`
- `tsconfig.app.json`
- Application source directories
- Shared component directories
- Existing Angular modules
- Existing standalone components
- Existing imports
- Global styles
- Theme configuration
- Assets
- Environment configuration
- Authentication configuration
- HTTP configuration
- Existing tests
- CI/CD configuration
- README files
- Available corporate documentation

The agent must determine from evidence:

- Angular version
- Node.js requirements
- Package manager
- TypeScript version
- Corporate packages
- Corporate components
- Corporate services
- Corporate styles
- Corporate theme
- Design tokens
- Existing application structure
- Testing framework
- State-management approach
- Authentication approach

Repository evidence always takes precedence over generic Angular recommendations.

---

# Endesa Corporate Library Discovery

Before implementing a user interface, explicitly search for evidence of Endesa corporate libraries.

Inspect:

```text
package.json
```

for existing corporate dependencies.

Inspect application imports for patterns that identify:

- Shared Endesa components
- Corporate UI libraries
- Shared utilities
- Corporate services
- Corporate authentication components
- Corporate layout components
- Corporate form components

Inspect directories likely to contain:

```text
shared/
core/
components/
ui/
layout/
theme/
styles/
design-system/
libs/
```

Also inspect:

- Existing screens
- Existing forms
- Existing navigation
- Existing tables
- Existing dialogs
- Existing dashboards

The objective is to learn how the project already consumes the Endesa corporate frontend ecosystem.

Do not infer library behaviour from package names alone when implementation or documentation is available.

---

# Corporate Component Priority

When implementing a UI requirement, use this selection order:

## Priority 1 - Existing Endesa corporate component

If an appropriate Endesa corporate component exists, reuse it.

## Priority 2 - Existing application shared component

If the application already provides an approved shared abstraction over corporate libraries, reuse it.

## Priority 3 - Existing Angular pattern in the repository

If no dedicated corporate component exists, follow the established application pattern.

## Priority 4 - Standard Angular implementation

Use standard Angular capabilities when the requirement does not require a corporate UI component.

## Priority 5 - External UI library

Only propose another UI library if:

- No Endesa corporate alternative exists.
- No existing project component solves the requirement.
- The dependency is technically justified.
- Compatibility has been assessed.
- Architecture explicitly approves it.

External libraries are NOT the default for an Endesa Angular application.

---

# Corporate Library Reuse Rules

When corporate components are available:

Always:

- Reuse them.
- Follow their documented API.
- Follow existing repository usage examples.
- Preserve their styling.
- Preserve accessibility behaviour.
- Preserve expected events and lifecycle.
- Respect their documented configuration.
- Use existing wrappers where applicable.

Do NOT:

- Copy corporate component source code.
- Reimplement the same component manually.
- Hardcode an approximation of the corporate component.
- Replace it with another design system for convenience.
- Modify its public API.
- Bypass required configuration.
- Override styles globally without impact analysis.
- Assume undocumented inputs or outputs.

---

# Angular Material and Other UI Libraries

Angular Material, Bootstrap, PrimeNG, Tailwind, or any other design/component framework must NOT automatically replace or bypass Endesa corporate libraries.

If the application already uses one of these technologies alongside the Endesa libraries, preserve the established architecture.

Do not introduce a new UI framework only because:

- It is familiar.
- It has a convenient component.
- It makes implementation faster.
- The agent knows it better.

Corporate consistency takes priority over developer convenience.

---

# Missing Corporate Component

If a required UI capability is not found in the available Endesa corporate libraries:

1. Search the existing repository for an equivalent implementation.
2. Search existing application shared components.
3. Review available corporate documentation.
4. Confirm that no documented corporate component has been found.

Then report:

```text
Corporate component required: [capability]

Corporate implementation found: NO

Repository alternative found: [YES/NO]

Proposed fallback: [description]

Corporate validation required: YES
```

Do not present the fallback as an approved Endesa corporate solution.

---

# Technology Compatibility

Always use the Angular, TypeScript, and Node.js versions defined by the repository.

Do not silently:

- Upgrade Angular.
- Upgrade Node.js.
- Upgrade TypeScript.
- Replace the package manager.
- Replace the build system.
- Introduce a new UI framework.
- Change state-management technology.
- Change corporate frontend libraries.

An Angular version upgrade requires assessment of:

- Endesa corporate library compatibility
- Third-party dependency compatibility
- TypeScript compatibility
- Node.js compatibility
- Build compatibility
- Test compatibility
- CI/CD compatibility

Corporate library compatibility must be verified before recommending an Angular upgrade.

---

# Package Management

Use the package manager already selected by the repository.

Possible examples:

- npm
- yarn
- pnpm

Do not change package manager without explicit approval.

Before introducing a dependency:

- Check whether an Endesa corporate library already provides the capability.
- Check existing project dependencies.
- Evaluate compatibility.
- Evaluate maintenance impact.
- Evaluate security impact.
- Explain why the dependency is necessary.

Never invent internal npm registries or corporate package coordinates.

---

# Architecture Principles

Follow the frontend architecture already established by the repository.

Apply:

- Separation of concerns
- Strong TypeScript typing
- Explicit data flow
- Reusable components
- Feature isolation
- Clear service boundaries
- Consistent error handling
- Consistent loading states
- Maintainable templates
- Testable components

Do NOT restructure an existing Endesa application simply to match a generic Angular architecture.

Corporate and repository patterns take precedence.

---

# TypeScript Standards

Always:

- Use explicit meaningful types.
- Avoid unnecessary `any`.
- Prefer `unknown` when the type is genuinely unknown.
- Apply strict null handling.
- Model API contracts explicitly.
- Preserve stable public interfaces.
- Keep code readable.
- Follow repository linting rules.

Avoid:

```typescript
any
```

unless technically unavoidable and documented.

Do not suppress:

- TypeScript errors
- Lint errors
- Build warnings

without a justified reason.

---

# Component Design

Components should:

- Have one clear responsibility.
- Keep templates readable.
- Avoid business logic in templates.
- Use typed inputs.
- Use typed outputs.
- Handle loading state.
- Handle empty state.
- Handle success state.
- Handle error state.
- Reuse Endesa corporate components.
- Follow existing change-detection conventions.

Before creating a new component, check whether an equivalent corporate or shared component exists.

---

# Forms

For forms, check first for Endesa corporate:

- Form controls
- Input components
- Select components
- Date components
- Validation components
- Error-message patterns
- Buttons
- Layout components

Reuse corporate implementations when available.

Always:

- Define validation explicitly.
- Display actionable validation feedback.
- Prevent invalid submission.
- Handle server-side validation.
- Preserve accessibility semantics.
- Keep business validation consistent.
- Handle API errors.

Never assume frontend validation provides a security boundary.

Backend validation remains mandatory.

---

# Navigation and Layout

Before creating navigation or layout elements, inspect the project for corporate:

- Headers
- Navigation
- Sidebars
- Menus
- Breadcrumbs
- Page containers
- Footers
- Layout grids

Reuse the established Endesa layout.

Do not build a visually separate application shell when a corporate application shell already exists.

---

# Tables and Data Presentation

Before implementing a table, grid, pagination control, filter panel, or data presentation component:

1. Search for Endesa corporate equivalents.
2. Search existing project implementations.
3. Follow established patterns.

For large datasets consider:

- Pagination
- Server-side filtering
- Sorting
- Loading states
- Empty states
- Error states
- Accessibility
- Performance

Do not load unbounded datasets into the browser.

---

# Dialogs, Notifications and Feedback

Check for corporate implementations of:

- Dialogs
- Modals
- Confirmation messages
- Toasts
- Notifications
- Alerts
- Progress indicators
- Loading indicators

Corporate interaction patterns should remain consistent across the application.

Do not introduce an unrelated notification system when an existing corporate approach is available.

---

# API Integration

Use the existing HTTP and API abstraction.

Always:

- Type request contracts.
- Type response contracts.
- Use configured API base URLs.
- Preserve authentication mechanisms.
- Handle network errors.
- Handle backend errors consistently.
- Avoid scattered HTTP calls inside visual components.
- Validate API assumptions.
- Avoid duplicated integration logic.

Do not expose:

- Tokens
- Secrets
- Credentials

in frontend source or logs.

API contract changes require coordination with:

- Backend Engineer
- QA Engineer
- Security Engineer

---

# Authentication and Authorization

Reuse the corporate authentication and authorization mechanisms already present in the repository.

Never invent:

- Authentication flows
- Corporate identity providers
- Authorization APIs
- Token storage mechanisms
- Internal SSO configuration

Frontend authorization controls are for UX only.

Backend authorization remains authoritative.

Never treat hidden or disabled frontend elements as a security control.

Authentication changes require mandatory Security Engineer review.

---

# State Management

Before introducing a state-management library:

1. Inspect the existing repository.
2. Identify the current state-management approach.
3. Determine whether the problem actually requires shared state.
4. Evaluate whether Angular-native mechanisms already solve it.
5. Evaluate whether corporate guidance exists.

Do not introduce:

- NgRx
- Another store library
- Additional state-management frameworks

solely because they are commonly used.

Preserve the existing project approach unless an architectural change is approved.

---

# Styling and Theming

The Endesa corporate visual identity available through approved project libraries and styles must take precedence.

Use existing:

- Corporate themes
- Design tokens
- Typography
- Colour definitions
- Spacing
- Responsive breakpoints
- Layout conventions
- Corporate CSS/SCSS utilities

Never invent brand values.

Do NOT:

- Hardcode corporate colours when tokens exist.
- Approximate corporate colours.
- Introduce a second design system.
- Recreate the corporate theme manually.
- Override corporate styles globally without analysis.
- Duplicate corporate components using custom CSS without justification.

If theme information cannot be found, report:

`CORPORATE THEME INFORMATION REQUIRED`

---

# Responsive Design

Follow the responsive behaviour established by the corporate libraries and existing application.

Validate critical screens for:

- Desktop layouts
- Reduced viewport width
- Overflow
- Table behaviour
- Form layout
- Navigation behaviour

Use existing corporate responsive utilities when available.

Do not invent corporate breakpoints.

---

# Accessibility

Accessibility is mandatory.

Frontend changes must consider:

- Keyboard navigation
- Focus management
- Accessible names
- Form labels
- Validation feedback
- Semantic HTML
- Screen-reader behaviour
- Content hierarchy
- Colour contrast

Preserve accessibility behaviour supplied by Endesa corporate components.

Do not replace accessible semantics with custom visual behaviour.

Accessibility regressions in critical user flows are blocking.

---

# Error Handling

Frontend errors must produce predictable user behaviour.

Handle:

- Network failures
- Validation errors
- Authorization failures
- Backend errors
- Empty results
- Timeout scenarios where applicable

Use existing corporate error components or notification patterns when available.

Do not expose internal backend details to users.

---

# Security Guidelines

Always consider:

- Cross-site scripting
- Unsafe HTML rendering
- URL validation
- Redirect validation
- Authentication state
- Authorization boundaries
- Browser storage
- Dependency vulnerabilities
- Sensitive console output

Never:

- Insert untrusted HTML without approved sanitization.
- Store application secrets in frontend code.
- Store credentials in source code.
- Treat UI visibility as authorization.
- Disable Angular security mechanisms for convenience.
- Log access tokens.
- Log sensitive personal information.
- Hardcode production credentials.

Security-sensitive changes require Security Engineer review.

---

# Testing Strategy

Use the test technologies already configured in the project.

Do not replace the existing testing framework without justification.

## Unit Tests

Cover:

- Components
- Services
- Validation
- Data transformations
- Error handling
- Business-facing presentation logic

## Integration Tests

Cover:

- Component interaction
- Routing
- API boundaries
- Authentication behaviour
- Corporate component integration

## End-to-End Tests

Use for critical business flows when the project supports them.

Critical corporate components should be tested through their documented behaviour rather than internal implementation.

---

# Performance Guidelines

Review:

- Initial bundle size
- Lazy-loaded routes
- Repeated API requests
- Large lists
- Large tables
- Change detection
- Subscription lifecycle
- Asset loading
- Third-party dependencies
- Duplicate corporate dependencies

Avoid premature optimization.

Performance recommendations must identify either:

- A measurable bottleneck
- A clear scalability risk
- An established repository pattern

Performance-sensitive changes should be reviewed by the Performance Engineer.

---

# Corporate Consistency Review

Before considering frontend implementation complete, verify:

- Endesa corporate components were searched.
- Available corporate components were reused.
- Existing application patterns were respected.
- No corporate library was duplicated unnecessarily.
- No corporate API was invented.
- Corporate styling was preserved.
- Corporate accessibility behaviour was preserved.
- No unrelated design system was introduced.
- Missing corporate information has been explicitly reported.

---

# Documentation Requirements

Frontend changes should document:

- Component purpose
- Inputs and outputs
- API dependencies
- Endesa corporate libraries used
- Corporate components reused
- Configuration
- Accessibility considerations
- Security considerations
- Known limitations
- Missing corporate information
- Required corporate validation

---

# Decision Rules

When recommending Angular implementation technology, use this decision sequence:

```text
Is Angular already used?
        |
       YES
        |
Are Endesa corporate libraries present?
        |
    +---+---+
    |       |
   YES      NO
    |       |
Reuse       Search repository and
Endesa      corporate documentation
libraries       |
               |
          Evidence found?
             /     \
           YES      NO
            |        |
          Reuse    Report missing
          them     corporate information
                     |
                 Do NOT invent
```

---

# Mandatory Corporate Evidence Report

Whenever this skill is activated, include a section containing:

```text
ENDESA CORPORATE ANGULAR CHECK

Angular version:
Node version:
Package manager:

Corporate libraries detected:
- [library or "None confirmed"]

Corporate components detected:
- [component or "None confirmed"]

Corporate styles/theme detected:
- [evidence or "None confirmed"]

Existing project patterns inspected:
- [evidence]

Corporate components selected for reuse:
- [components]

Generic third-party components proposed:
- [components or "None"]

Missing corporate information:
- [information or "None"]
```

This report prevents the agent from silently replacing the Endesa corporate frontend ecosystem with generic Angular solutions.

---

# Output Format

When this skill is used, provide:

## Technology Detection

Report:

- Angular version
- TypeScript version
- Node.js requirements
- Package manager
- Testing framework
- Repository evidence

## Endesa Corporate Library Detection

Report:

- Corporate dependencies found
- Corporate imports found
- Corporate components found
- Corporate services found
- Corporate styles found
- Corporate theme information found

## Corporate Reuse Decision

Explain:

- Which Endesa components will be reused
- Which existing application components will be reused
- Why a new component is required, if applicable

## Implementation Approach

Explain:

- Components affected
- Services affected
- Routes affected
- API interaction
- State management
- Forms
- Error handling

## Testing and Accessibility

Report:

- Unit tests
- Integration tests
- E2E impact
- Accessibility validation

## Security and Performance

Report:

- Security considerations
- Performance considerations

## Missing Corporate Information

Explicitly identify anything required but unavailable.

Never invent missing corporate standards.

---

# Definition of Done

An Endesa Angular implementation is complete when:

- Angular version is respected.
- Node.js compatibility is respected.
- Existing repository architecture is respected.
- Endesa corporate libraries have been explicitly investigated.
- Available Endesa corporate components are reused.
- Available corporate design patterns are followed.
- No Endesa package has been invented.
- No Endesa component has been invented.
- No corporate API has been invented.
- No corporate design token has been invented.
- Corporate styles and themes are preserved.
- TypeScript compiles.
- Configured linting passes.
- Tests pass.
- API contracts remain consistent.
- Loading states are handled.
- Error states are handled.
- Accessibility is validated.
- Security considerations are addressed.
- Performance impact is considered.
- Documentation is updated.
- Missing corporate information is explicitly documented.
- Any fallback outside Endesa corporate libraries is clearly identified as requiring validation.