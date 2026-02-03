# Large File Warning

Flags files that exceed 500 lines when they're being written, suggesting they may benefit from being split into smaller, more focused modules.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Large File Warning"
3. Click Install

## Configuration

No configuration required. The threshold is 500 lines.

## Usage

This hook triggers on `PreToolUse` for `Write` operations. When a file exceeds 500 lines, it prints a non-blocking warning. This is a nudge, not a hard gate — some files legitimately need to be long. Use your judgment.
