Scaffold a new ACK parser for `$ARGUMENTS` in the Claude Code adapter.

1. Read existing parsers in `src/adapters/claude-code/parsers/` to understand the conventions:
   - Import patterns (FileIOService, SchemaService, NormalizedTool types)
   - Function signature pattern: `async parse*(fileIO, schemaService, path, scope): Promise<NormalizedTool[]>`
   - Error handling: return empty array for missing files, error-status NormalizedTool for validation failures, NEVER throw
   - Schema validation via `schemaService.validate(schemaKey, data)`
   - Status determination (enabled/disabled based on naming or config flags)

2. Create `src/adapters/claude-code/parsers/$ARGUMENTS.parser.ts` with:
   - The standard imports (FileIOService, SchemaService, NormalizedTool, ToolType, ConfigScope, ToolStatus, ToolSource)
   - A main parse function following the naming pattern
   - Proper error handling (try/catch returning error-status tools)
   - Zod schema validation
   - All imports using `.js` extensions

3. Create a corresponding test file at `src/test/unit/$ARGUMENTS.parser.test.ts` with:
   - Vitest imports (describe, it, expect, beforeEach, afterEach)
   - tmpdir setup/teardown pattern
   - Tests for: valid input, missing file, invalid JSON, schema validation failure, disabled state

4. Register the schema key in `src/adapters/claude-code/schemas.ts` if needed

5. Wire up the parser call in `src/adapters/claude-code/claude-code.adapter.ts` readTools method

6. Show a summary of files created and modifications made
