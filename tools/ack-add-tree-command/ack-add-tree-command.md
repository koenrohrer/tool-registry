Add a new VS Code command called `$ARGUMENTS` to the ACK tool tree.

1. Read existing command handlers in `src/views/tool-tree/` to understand conventions:
   - `tool-tree.commands.ts` — tree navigation commands
   - `tool-tree.management.ts` — tool operations (toggle, delete, move)
   - `tool-tree.profile-commands.ts` — profile operations
   - Pattern: `vscode.commands.registerCommand('ack.commandName', async (node?: TreeNode) => { ... })`

2. Determine which file the command belongs in based on its purpose:
   - Navigation/view → `tool-tree.commands.ts`
   - Tool operations → `tool-tree.management.ts`
   - Profile operations → `tool-tree.profile-commands.ts`

3. Add the command handler using `getServices()` to access services

4. Register in `package.json`:
   - Add to `contributes.commands` with title and icon
   - Add to appropriate menu (`view/item/context`, `view/title`, or submenu)
   - Add `when` clause for context menu visibility (e.g., `viewItem == toolNode`)

5. Add a test in the corresponding test file

6. Show a summary of all changes made
