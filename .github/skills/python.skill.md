---
name: "Python Engineering"
description: "Engineering standards and best practices for building production-grade software using Python."
---

# Python Engineering Skill

## Purpose

This skill provides standards, patterns, best practices, and engineering guidance for building production-grade software using Python.

It applies to:

- Backend services
- APIs
- Automation tools
- CLI applications
- AI/LLM systems
- Data processing applications
- Microservices

---

# Supported Python Version

Preferred:

- Python 3.12+

Minimum:

- Python 3.11

Avoid supporting legacy versions unless explicitly required.

---

# Core Engineering Principles

## Readability First

Code is read more often than it is written.

Prefer:

- explicit code
- clear naming
- small functions

Avoid:

- clever solutions
- implicit behavior
- unnecessary abstraction

---

## Simplicity

Apply:

- KISS
- YAGNI

Do not introduce complexity without measurable benefit.

---

## Strong Typing

Always use type hints.

Example:

```python
def calculate_total(items: list[Item]) -> Decimal:
    ...
```

Avoid:

```python
def calculate_total(items):
    ...
```

---

# Project Structure

Recommended layout:

```text
src/
│
├── api/
├── services/
├── repositories/
├── domain/
├── infrastructure/
├── schemas/
└── tests/
```

---

# Dependency Management

Preferred:

- uv
- poetry

Acceptable:

- pip

Avoid:

- unmanaged requirements
- global package installation

---

# Coding Standards

## Functions

Prefer:

- single responsibility
- less than 50 lines

Review if:

- more than 100 lines

---

## Classes

Create classes only when they represent:

- behavior
- state
- abstraction boundary

Avoid classes used only as namespaces.

---

## Naming

Use:

```python
snake_case
```

for:

- variables
- functions
- modules

Use:

```python
PascalCase
```

for:

- classes

Use:

```python
UPPER_CASE
```

for:

- constants

---

# Error Handling

Always:

- raise meaningful exceptions
- catch only expected failures
- provide actionable messages

Avoid:

```python
except Exception:
    pass
```

---

# Logging

Use structured logging.

Log:

- application startup
- external calls
- failures
- critical business events

Never log:

- passwords
- secrets
- tokens
- sensitive personal data

---

# API Development

Preferred framework:

- FastAPI

General principles:

- REST first
- explicit schemas
- validation at boundaries
- version APIs when necessary

Always use:

- request models
- response models
- OpenAPI generation

---

# Data Validation

Preferred:

```python
Pydantic
```

Validate:

- API inputs
- configuration
- external data

Never trust external input.

---

# Database Access

Preferred:

- SQLAlchemy

Always:

- parameterized queries
- explicit transactions
- connection pooling

Avoid:

- string concatenation SQL
- N+1 queries

---

# Testing Strategy

Framework:

```python
pytest
```

Required:

### Unit Tests

- business logic
- utility functions
- edge cases

### Integration Tests

- database interaction
- APIs
- external services

### Contract Tests

when APIs are involved

---

# Async Programming

Use async when:

- IO bound workloads
- APIs
- external services

Avoid async for:

- CPU intensive workloads

Preferred:

```python
asyncio
```

---

# Performance Guidelines

Optimize only after identifying bottlenecks.

Focus on:

- database queries
- network calls
- serialization cost
- memory consumption

Avoid premature optimization.

---

# Pandas Performance Engineering

Apply this section only when pandas is used for non-trivial data processing.

Performance recommendations must preserve:

- Functional correctness
- Business meaning
- Data integrity
- Readability
- Maintainability
- Memory safety

Prefer measurement over assumption.

Classify performance evidence as:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

Do not present an inferred optimization as a measured improvement.

## Vectorized Operations

Prefer native pandas operations over row-by-row Python processing when they:

- Preserve required behaviour
- Improve clarity
- Reduce repeated Python-level execution
- Provide a measurable or plausible performance benefit

Consider operations such as:

- `merge`
- `join`
- `map`
- `isin`
- `dropna`
- `fillna`
- `drop_duplicates`
- `str.strip`
- `str.lower`
- `str.upper`
- `groupby`
- `transform`
- `where`
- `loc`

Avoid Python-level loops over large DataFrames when a clear and equivalent vectorized operation exists.

Avoid `DataFrame.apply()` for large datasets when an equivalent native pandas operation:

- Preserves behaviour
- Is easier to understand
- Can be validated
- Avoids unnecessary Python-level execution

Do not replace readable, correct code with a difficult vectorized expression unless the benefit justifies the added complexity.

Do not assume vectorization is automatically faster for every workload.

## Business-Key Deduplication

Before expensive merge, join, validation, or filtering operations, evaluate whether repeated keys can be removed safely.

When duplicate records do not have independent business meaning:

- Identify the relevant business key.
- Define which record must be retained.
- Apply `drop_duplicates()` before expensive downstream operations where beneficial.
- Document the deduplication rule.
- Validate that the resulting dataset preserves required business information.

Do not deduplicate blindly.

Do not remove duplicates when:

- Duplicate rows represent legitimate business events.
- Row order has business meaning.
- Multiple records for the same key carry required information.
- The retention rule cannot be determined safely.

Deduplication rules must be based on business semantics, not only performance.

## Lookup Normalization

When lookup values are used repeatedly:

- Normalize values once where practical.
- Reuse the normalized representation.
- Avoid repeatedly applying the same string transformations.
- Define handling for null, blank, malformed, and unexpected values.
- Preserve the original value when required for output or auditability.

Typical normalization may include:

- Trimming whitespace with `str.strip()`
- Normalizing case when comparisons are case-insensitive
- Standardizing null or blank handling
- Converting values to the expected type
- Removing duplicates when business semantics allow it

Normalization must not alter meaningful business data.

## Lookup Reuse and Caching

For repeated validation, suggestion, mapping, or selection operations, consider reusable structures such as:

- Normalized `Series`
- Indexed DataFrames
- Dictionaries
- Sets
- Categoricals
- Precomputed mappings

Reuse normalized lookup values when:

- The underlying data has not changed.
- The normalization rule remains valid.
- Reuse reduces repeated scans or transformations.
- Memory impact remains acceptable.

Do not cache mutable or context-dependent data without considering:

- Invalidation
- Freshness
- Ownership
- Memory consumption
- Concurrency
- Lifecycle

A cache without a valid invalidation or refresh strategy can produce incorrect results.

## Merge and Join Strategy

Before merging DataFrames:

- Identify the business key.
- Validate expected key uniqueness.
- Determine expected relationship:
  - One-to-one
  - One-to-many
  - Many-to-one
  - Many-to-many
- Restrict input columns when unused columns materially increase cost.
- Evaluate duplicate keys.
- Evaluate null keys.
- Evaluate output-row growth.
- Validate output consistency.

When supported by the pandas version and appropriate to the repository, consider merge validation to detect unexpected cardinality.

Do not allow an unintended many-to-many merge to create uncontrolled row growth.

After material merges, validate:

- Row count
- Key coverage
- Unmatched records
- Duplicate generation
- Missing values
- Required output columns

## Filtering Strategy

For repeated filtering:

- Avoid repeated full-DataFrame scans when a reusable index, mapping, mask, or normalized lookup is appropriate.
- Reuse boolean masks when they remain valid and improve clarity.
- Use `isin()` for membership checks when appropriate.
- Avoid rebuilding identical lookup collections repeatedly.
- Apply selective filters before expensive operations when this preserves semantics.

Do not push filters earlier when doing so changes required business behaviour.

## Intermediate DataFrames and Memory

Consider memory impact when processing large datasets.

Avoid:

- Unnecessary full DataFrame copies
- Repeated materialization of identical intermediate results
- Retaining unused columns
- Retaining large temporary objects longer than necessary
- Repeated type conversion
- Repeated normalization

When appropriate:

- Select only required columns.
- Use appropriate data types.
- Release references to large temporary objects when no longer needed.
- Process data in chunks when the complete dataset cannot be handled safely in memory.
- Evaluate whether categoricals are appropriate for repeated low-cardinality values.

Do not optimize memory by reducing data precision or changing business meaning without an explicit requirement.

## Excel and File-Processing Workloads

When pandas processes Excel or similar files:

- Read only required sheets when possible.
- Read only required columns when supported and appropriate.
- Avoid reopening the same file repeatedly.
- Avoid repeating identical parsing and normalization.
- Validate required columns before expensive processing.
- Validate empty datasets early.
- Validate data types and unexpected values.
- Preserve required output ordering and formatting semantics.
- Separate file I/O from reusable business transformations where practical.

For large workbooks, distinguish whether the bottleneck is:

- File reading
- Parsing
- Data transformation
- Joining
- Validation
- Export
- Formatting

Do not assume pandas computation is the bottleneck without evidence.

## Measurement and Profiling

When execution is available, measure performance-sensitive changes.

Record when practical:

- Input size
- Dataset shape
- Execution environment
- Operation measured
- Baseline duration
- Optimized duration
- Memory impact
- Number of repetitions
- Functional-equivalence validation

Use representative data when available.

If synthetic test data is used, label it explicitly.

Do not claim an optimization is faster without execution evidence.

When measurement is unavailable, report:

`Performance recommendation is inferred and has not been validated through execution.`

## Correctness Validation After Optimization

Every material pandas optimization must preserve expected results.

Validate applicable:

- Row count
- Column count
- Key uniqueness
- Duplicate behaviour
- Null handling
- Data types
- Ordering when relevant
- Calculations
- Aggregations
- Mappings
- Unmatched records
- Exported output

Performance improvement does not justify incorrect output.

## Pandas Performance Anti-Patterns

Detect and report when materially relevant:

- Row-by-row processing over large DataFrames when an equivalent native operation exists
- Repeated `DataFrame.apply()` for operations supported natively by pandas
- Repeated normalization of unchanged lookup data
- Repeated full-DataFrame scans for identical conditions
- Uncontrolled many-to-many merges
- Expensive merges performed before safe business-key deduplication
- Reopening or reparsing the same source file unnecessarily
- Creating unnecessary intermediate DataFrame copies
- Loading unused sheets or columns in data-heavy workloads
- Caching without invalidation or freshness rules
- Optimization that changes business semantics
- Optimization claims without measurement evidence

Do not classify these as defects automatically.

Explain:

- Input scale
- Observed or inferred impact
- Correctness constraints
- Recommended validation
- Expected trade-off

## Pandas Performance Output

When pandas performance is relevant, report:

### Workload

- Input source
- Dataset size when known
- Main transformations
- Repeated operations

### Evidence

Use:

```text
MEASURED
OBSERVED
INFERRED
NOT VALIDATED
```

### Bottleneck

Identify the material operation or suspected operation.

### Recommendation

Describe:

- Proposed change
- Expected benefit
- Correctness constraints
- Memory implications
- Complexity trade-off

### Validation

Describe:

- Functional-equivalence checks
- Performance measurement
- Regression tests
- Data-integrity checks

### Result

Use:

```text
IMPROVED
NO MATERIAL IMPROVEMENT
REGRESSED
NOT EXECUTED
NOT AVAILABLE
```

Never report `IMPROVED` without execution evidence.

---

# Security Guidelines

Must follow:

- OWASP principles
- input validation
- least privilege
- secure secret management

Never:

- hardcode credentials
- expose stack traces
- trust user input

---

# AI / LLM Development

When building AI systems:

- validate prompts
- limit tool permissions
- sanitize retrieved content
- protect secrets
- log tool execution

Evaluate:

- hallucination risks
- prompt injection risks
- data leakage risks

---

# Documentation Requirements

Every production component must include:

- purpose
- inputs
- outputs
- dependencies
- limitations

---

# Definition of Done

A Python implementation is complete when:

- Code works.
- Tests pass.
- Types are defined.
- Logging exists.
- Validation exists.
- Security considerations are addressed.
- Documentation is updated.
- Technical debt is documented.