# ACK Validate Patterns

Runs a comprehensive audit of the ACK codebase checking for architectural pattern violations: missing `.js` import extensions, hardcoded paths, parser throw statements, raw `fs.writeFile` calls, and non-exhaustive switch statements.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Validate Patterns"
3. Click Install

## Configuration

No configuration required.

## Usage

Use with: `/ack-validate-patterns`

No arguments needed. Scans the entire `src/` directory.

Designed specifically for the ACK VS Code extension codebase.
