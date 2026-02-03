# Dependency Change Reminder

Reminds you to run the appropriate install command after dependency files are modified. Supports multiple ecosystems: npm, pip, Cargo, Go, Ruby, and Poetry/uv.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Dependency Change"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PostToolUse` for `Write` and `Edit` operations. It detects changes to:

| File | Reminder |
|------|----------|
| `package.json` | `npm install` |
| `requirements.txt` | `pip install -r` |
| `pyproject.toml` | pip/poetry/uv |
| `Cargo.toml` | `cargo build` |
| `go.mod` | `go mod tidy` |
| `Gemfile` | `bundle install` |
