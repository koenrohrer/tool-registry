# Console Log Guard

Catches debug statements like `console.log`, `console.debug`, `print()`, and `debugger` before they make it into production code. Skips test files automatically.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Console Log Guard"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations. It scans for common debug patterns:
- `console.log()` / `console.debug()` (JavaScript/TypeScript)
- `print()` (Python)
- `debugger` (JavaScript)
- `Debug.Log` (C#/Unity)

Test files (`.test.*`, `.spec.*`, `_test.*`) are excluded. The hook issues a **warning** (non-blocking) so you can review before committing. Lines inside comments starting with `//` are ignored.
