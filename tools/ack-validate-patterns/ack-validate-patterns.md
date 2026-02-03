Audit the ACK codebase for pattern violations.

Scan all `.ts` files in `src/` (excluding tests and `*.d.ts`) and check:

**1. Import Extensions**
- All relative imports (`from './...'` or `from '../...'`) must end with `.js`
- Flag every violation with file:line

**2. Path Hardcoding**
- Files in `src/adapters/` and `src/services/` must not use `path.join` or `path.resolve` with literal `.claude`, `settings.json`, `.mcp.json`, or `skills/` strings
- All such paths must go through `ClaudeCodePaths`

**3. Parser Error Handling**
- Files in `src/adapters/*/parsers/` must not contain `throw new Error` or `throw Error`
- Parsers must return error-status NormalizedTool objects

**4. Raw File Writes**
- Files in `src/` (except `fileio.service.ts`) must not call `fs.writeFile` or `fs.writeFileSync` directly
- Must use `FileIOService` methods

**5. Switch Exhaustiveness**
- Any `switch` over `type`, `scope`, `toolType`, or `configScope` must have a `default:` case that throws

**6. Schema Registration**
- Every schema key used in `schemaService.validate()` calls must be registered in `schemas.ts`

Print a structured report:
```
ACK Pattern Audit
=================
[FAIL] src/services/foo.ts:42 - Missing .js import extension
[FAIL] src/adapters/claude-code/parsers/bar.ts:15 - throw in parser
[WARN] src/services/baz.ts:88 - switch on type without default throw
...
=================
Summary: X violations (Y blocking, Z warnings)
```
