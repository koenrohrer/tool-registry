Analyze `$ARGUMENTS` for refactoring opportunities.

1. Read the file and identify:
   - Functions longer than ~30 lines that could be decomposed
   - Duplicated logic that could be extracted
   - Deep nesting (3+ levels) that could be flattened with early returns
   - Complex conditionals that could be simplified or named
   - Mixed abstraction levels within a function
   - Dead code (unreachable branches, unused variables)
2. For each finding, explain:
   - What the problem is (1 sentence)
   - Why it matters (maintainability, readability, testability)
   - The specific refactoring to apply
3. Ask me which refactorings to apply (or "all")
4. Apply the selected refactorings one at a time
5. After each change, verify existing tests still pass (if tests exist)
6. Show a before/after summary of the changes

Do NOT change any public API signatures unless I explicitly approve it.
