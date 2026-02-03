# ACK Debug Tool Loading

Traces the full ACK read pipeline to diagnose why a specific tool isn't appearing or loading correctly. Checks config files, validates schemas, traces parser logic, and verifies scope resolution.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Debug Tool Loading"
3. Click Install

## Configuration

No configuration required.

## Usage

Use with: `/ack-debug-tool-loading [tool-name-or-description]`

Examples:
- `/ack-debug-tool-loading my-mcp-server`
- `/ack-debug-tool-loading the skill that should be in project scope`

Designed specifically for the ACK VS Code extension codebase.
