# Test Watcher

Reminds you to create or update tests whenever a source file is modified. Checks for corresponding `.test.*`, `.spec.*`, or `__tests__/` files and nudges you if none are found.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Test Watcher"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PostToolUse` for `Write` and `Edit` operations on `.ts`, `.tsx`, `.js`, `.jsx`, and `.py` files. It skips files that are already test files. If no matching test file is found, it prints a non-blocking reminder. Supports common test file patterns:
- `file.test.ts` / `file.spec.ts`
- `__tests__/file.ts`
- `test/file.ts`
