# Filesystem MCP Server

Official MCP reference server for secure local file operations.

## What it does

Provides controlled read, create, edit, move, and search operations on your local filesystem. You specify which directories the server can access, keeping everything else off-limits.

## Use cases

- Sandboxed file access for agent workflows
- Batch file renaming, organization, and cleanup
- Searching file contents across allowed directories
- Reading project files outside the current workspace

## Configuration

After installing, edit the last argument in `args` to point at the directory you want to expose:

```json
"args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/directory"]
```

## Requirements

- Node.js 18+

## Source

[modelcontextprotocol/servers/src/filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
