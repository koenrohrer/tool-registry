# ACK Raw FS Guard

Detects direct use of `fs.writeFile` or `fs.writeFileSync` in ACK source code. All file writes should go through `FileIOService.writeJsonFile()` which provides atomic writes (temp-then-rename via `write-file-atomic`) and automatic backup creation.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Raw FS Guard"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations on `.ts` files in `src/`. It skips test files and `fileio.service.ts` itself (where the raw calls are wrapped). Issues a **warning** when raw file system write calls are detected.

Designed specifically for the ACK VS Code extension codebase.
