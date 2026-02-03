Debug why the tool `$ARGUMENTS` isn't loading correctly in ACK.

Trace the full read pipeline to find where the tool is being lost or misinterpreted:

1. **Identify the tool type and expected scope** from the tool name/description
2. **Check the raw config file** where the tool should be defined:
   - Skills: check `~/.claude/skills/` and `.claude/skills/` directories
   - MCP Servers: check `.mcp.json`, `~/.claude.json`
   - Hooks: check `settings.json` (user, project, local, managed)
   - Commands: check `~/.claude/commands/` and `.claude/commands/`
3. **Verify file contents** are valid:
   - JSON files: valid JSON/JSONC (check for comments, trailing commas)
   - Markdown files: valid frontmatter if expected
   - Schema: validate against the appropriate Zod schema from `schemas.ts`
4. **Check parser logic**:
   - Read the relevant parser file and trace how it would process this tool
   - Check for disabled status (`.disabled` suffix, `disabled` flag)
   - Verify the NormalizedTool fields it would produce
5. **Check scope resolution**:
   - Is the tool type supported in the expected scope? (check `APPLICABLE_SCOPES`)
   - Could it be overridden by a higher-precedence scope?
6. **Check adapter routing**:
   - Verify the tool type has a case in `readTools()` switch
7. **Report findings**:
   ```
   Tool Debug: $ARGUMENTS
   ======================
   Type: {detected type}
   Expected scope: {scope}
   Config file: {path} -- {exists/missing}
   File valid: {yes/no -- details}
   Schema valid: {yes/no -- validation errors}
   Parser output: {would produce NormalizedTool with status X}
   Scope supported: {yes/no}
   Resolution: {explanation of why it's not loading}
   Fix: {specific action to take}
   ```
