# ACK Path Guard

Detects hardcoded file paths in ACK adapter and service code. All Claude Code configuration paths (`settings.json`, `.mcp.json`, skills/, commands/) must use the centralized `ClaudeCodePaths` constants to prevent path traversal bugs and ensure cross-platform compatibility.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Path Guard"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations on `.ts` files in `src/adapters/` and `src/services/`. It issues a **warning** (non-blocking) when it finds `path.join` or `path.resolve` calls that reference Claude Code config paths without going through `ClaudeCodePaths`.

Designed specifically for the ACK VS Code extension codebase.
