# ACK Throw Guard

Catches `throw` statements in ACK parser files. By convention, ACK parsers never throw exceptions — they return `NormalizedTool` objects with `status: ToolStatus.Error` and a descriptive `statusDetail`. This ensures the extension degrades gracefully when encountering invalid config files.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Throw Guard"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations on files matching `*parser*.ts` or files in `parsers/` directories. It issues a **warning** when `throw new Error` is found, reminding you to return error-status tools instead.

Designed specifically for the ACK VS Code extension codebase.
