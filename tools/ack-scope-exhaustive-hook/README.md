# ACK Scope Exhaustive Check

Detects `switch` statements on `ToolType` or `ConfigScope` enums that are missing a `default: throw` case. In ACK, all routing logic over tool types and config scopes must be exhaustive to prevent silent failures when new enum values are added.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "ACK Scope Exhaustive"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations on `.ts` files in `src/`. When a `switch` statement references `type`, `scope`, `toolType`, or `configScope` without a `default: throw` or `default: assertNever`, it issues a **warning**.

Designed specifically for the ACK VS Code extension codebase.
