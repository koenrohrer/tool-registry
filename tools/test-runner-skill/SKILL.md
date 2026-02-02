# Test Runner Skill

Run test suites and diagnose failures with intelligent analysis.

## Instructions

When asked to run or analyze tests:
1. Detect the test framework (Jest, Vitest, pytest, etc.)
2. Run the appropriate test command
3. Parse test output for failures
4. For each failure, analyze root cause
5. Suggest fixes with code examples

## Output Format

- **Total**: X passed, Y failed, Z skipped
- **Failures**: Each with root cause analysis and suggested fix
- **Performance**: Slow tests flagged if > 5s
