Add a new tool type called `$ARGUMENTS` to the ACK extension.

This is a multi-step operation touching many files. Walk through each step:

1. **Add enum value** in `src/types/enums.ts`:
   - Add `{PascalCase} = '{snake_case}'` to `ToolType` enum

2. **Create parser** in `src/adapters/claude-code/parsers/{name}.parser.ts`:
   - Follow existing parser patterns (skill.parser.ts or command.parser.ts)
   - Return `NormalizedTool[]`, never throw
   - Validate with Zod schema

3. **Create writer** in `src/adapters/claude-code/writers/{name}.writer.ts`:
   - Follow existing writer patterns (skill.writer.ts or mcp.writer.ts)
   - Use ConfigService for JSON files, BackupService before deletes
   - Handle toggle (enable/disable), add, and remove operations

4. **Register Zod schema** in `src/adapters/claude-code/schemas.ts`:
   - Create validation schema for the new tool type's config format
   - Register with `claudeCodeSchemas` object

5. **Update adapter routing** in `src/adapters/claude-code/claude-code.adapter.ts`:
   - Add case to `readTools()` switch
   - Add case to `writeTool()` switch
   - Add case to `removeTool()` switch
   - Add to `supportedToolTypes` set

6. **Update ConfigService** in `src/services/config.service.ts`:
   - Add applicable scopes for the new type in `APPLICABLE_SCOPES`

7. **Update tree view** in `src/views/tool-tree/`:
   - Add group node for new type in tree provider
   - Add icon mapping

8. **Add paths** in `src/adapters/claude-code/paths.ts`:
   - Add path constants for the new type's config files

9. **Create tests**:
   - Parser unit test
   - Writer unit test
   - Adapter routing test

10. Show a checklist of all files modified and created
