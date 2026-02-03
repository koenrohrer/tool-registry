# PostgreSQL MCP Server

Official MCP reference server for PostgreSQL database access.

## What it does

Connects to a PostgreSQL database and provides read-only query access and schema inspection. Your agent can explore tables, run SELECT queries, and understand database structure.

## Use cases

- Querying databases using natural language
- Exploring schema and table relationships
- Generating reports from database data
- Debugging data issues by inspecting rows

## Configuration

You will be prompted for your PostgreSQL connection string during install. The format is:

```
postgresql://user:password@host:port/database
```

## Requirements

- Node.js 18+
- A running PostgreSQL instance

## Source

[modelcontextprotocol/servers/src/postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres)
