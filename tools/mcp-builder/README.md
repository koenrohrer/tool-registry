# MCP Builder

Guide for building production-quality MCP (Model Context Protocol) servers.

## What it does

Walks your agent through a structured four-phase process for creating MCP servers: deep research and planning, implementation, review and testing, and evaluation creation. Covers both Python (FastMCP) and TypeScript (MCP SDK).

## Use cases

- Building MCP servers to integrate external APIs or services
- Creating well-designed tool interfaces for LLM consumption
- Following MCP best practices for naming, error handling, and schemas
- Writing evaluations to verify server quality

## Topics covered

- API coverage strategy and tool naming conventions
- Input/output schema design with Zod or Pydantic
- Error handling with agent-friendly messages
- Tool annotations (readOnly, destructive, idempotent)
- Testing with MCP Inspector

## Source

Based on [anthropics/skills/mcp-builder](https://github.com/anthropics/skills/tree/main/skills/mcp-builder)
