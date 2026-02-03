Scaffold a new ACK service called `$ARGUMENTS`.

1. Read existing services in `src/services/` to understand conventions:
   - Constructor injection pattern with typed dependencies
   - Result types: `{ success: true, data } | { success: false, error: string }` (never throw)
   - Method naming patterns
   - Import patterns with `.js` extensions

2. Create `src/services/$ARGUMENTS.service.ts` with:
   - A class named `{PascalCase}Service`
   - Constructor accepting dependencies as `private readonly` parameters
   - At least one placeholder method returning a Result type
   - Standard imports

3. Create `src/test/unit/$ARGUMENTS.service.test.ts` with:
   - Vitest imports
   - Mock dependencies
   - Test for constructor initialization
   - Test template for the placeholder method

4. Register the service in `src/extension.ts`:
   - Add to the services initialization section (after its dependencies are created)
   - Add to the `services` object passed to `storeServices()`
   - Add to `getServices()` return type

5. Show a summary of files created and modifications made
