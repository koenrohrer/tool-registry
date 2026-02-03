Write thorough unit tests for `$ARGUMENTS`.

1. Read the target file and understand every exported function/class/component
2. Detect the project's testing framework (Jest, Vitest, Mocha, pytest, etc.) by checking config files and existing tests
3. Find an existing test file in the project to match style conventions (import patterns, describe/it nesting, assertion style, mock patterns)
4. For each exported function/class:
   - Test the happy path with typical inputs
   - Test edge cases (empty inputs, nulls, boundary values)
   - Test error conditions (invalid inputs, thrown exceptions)
   - Test any side effects (file I/O, API calls) with appropriate mocks
5. Place the test file following the project's test location convention
6. Run the tests to verify they pass
7. Report coverage: which functions are tested, which edge cases are covered
