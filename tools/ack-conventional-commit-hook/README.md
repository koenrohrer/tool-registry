# ACK Conventional Commit

Validates that git commit messages follow the [Conventional Commits](https://www.conventionalcommits.org/) format before they're created. Blocks commits with non-conforming messages.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Conventional Commit"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Bash` operations containing `git commit`. It validates the `-m` message matches:

```
type(optional-scope): description
```

Valid types: `feat`, `fix`, `chore`, `refactor`, `test`, `docs`, `ci`, `style`, `perf`, `build`, `revert`

Examples:
- `feat: add user authentication` -- valid
- `fix(parser): handle empty files` -- valid
- `updated stuff` -- blocked

Designed specifically for the ACK VS Code extension codebase.
