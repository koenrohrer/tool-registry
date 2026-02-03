# Secret Guard

Prevents accidental exposure of secrets, API keys, tokens, and credentials in your codebase. This hook scans file content before writes and blocks operations that contain patterns matching known secret formats.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Secret Guard"
3. Click Install

## Configuration

No configuration required. The hook activates automatically on all file writes and edits.

## Usage

This hook triggers on `PreToolUse` for `Write` and `Edit` operations. It scans for:
- AWS access keys (`AKIA...`)
- OpenAI/Anthropic API keys (`sk-...`)
- GitHub personal access tokens (`ghp_...`)
- GitLab tokens (`glpat-...`)
- Slack tokens (`xox[bposatr]-...`)
- Generic patterns like `password = "..."`, `api_key: "..."`

If a match is found, the write is **blocked** with a warning. Review the flagged content and either remove the secret or use environment variables instead.
