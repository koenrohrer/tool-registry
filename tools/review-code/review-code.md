Review the code at `$ARGUMENTS`.

Analyze for the following categories and report findings:

**1. Bugs & Logic Errors**
- Off-by-one errors, null dereferences, race conditions
- Incorrect control flow, unreachable code, missing return statements
- Type mismatches or incorrect assumptions

**2. Security**
- Injection vulnerabilities (SQL, command, XSS)
- Improper input validation at system boundaries
- Hardcoded secrets or credentials
- Insecure defaults

**3. Error Handling**
- Swallowed exceptions, missing error propagation
- Missing validation at public API boundaries
- Inconsistent error return patterns

**4. Performance**
- Unnecessary allocations in hot paths
- N+1 queries, unbounded loops, missing pagination
- Blocking operations that should be async

**5. Maintainability**
- Functions doing too many things (SRP violations)
- Deeply nested conditionals
- Missing type annotations at module boundaries

Format as:
```
Code Review: $ARGUMENTS
========================
[BUG]  line X: description
[SEC]  line X: description
[PERF] line X: description
[WARN] line X: description
========================
Summary: X issues found (Y critical, Z warnings)
```

Only report issues you have high confidence in. Do not flag style preferences.
