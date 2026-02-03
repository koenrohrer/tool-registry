<h1 align="center">ACK Community Tool Registry</h1>

<p align="center">
  <strong>MCP servers, skills, commands, and hooks</strong><br/>
  ready to install from the <a href="https://github.com/koenrohrer/ack">ACK</a> marketplace.
</p>

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack"><img src="https://img.shields.io/visual-studio-marketplace/v/koenrohrer.ack?label=ACK&color=007ACC" alt="ACK Version" /></a>
  <a href="https://github.com/koenrohrer/ack/blob/master/LICENSE"><img src="https://img.shields.io/github/license/koenrohrer/tool-registry?color=007ACC" alt="License" /></a>
  <img src="https://img.shields.io/badge/tools-42-007ACC" alt="Tool count" />
</p>

---

This is the default community registry for [ACK (Agent Config Keeper)](https://github.com/koenrohrer/ack). When you open the ACK marketplace in VS Code, this is where the tool listings come from.

---

## Available Tools

### MCP Servers

| Tool | Author | Description |
|------|--------|-------------|
| **Playwright** | Microsoft | Browser automation and testing through structured accessibility snapshots |
| **Filesystem** | MCP | Secure file operations with configurable directory access controls |
| **Memory** | MCP | Knowledge graph-based persistent memory across sessions |
| **Fetch** | MCP | Web content fetching and conversion for LLM usage |
| **Git** | MCP | Read, search, and manipulate Git repositories |
| **Sequential Thinking** | MCP | Structured, multi-step reasoning with revision and backtracking |
| **PostgreSQL** | MCP | Read-only database access for querying and schema inspection |
| **Brave Search** | MCP | Privacy-first web and local search via the Brave Search API |

### Skills

| Tool | Author | Description |
|------|--------|-------------|
| **Web App Testing** | Anthropic | Test local web apps with Playwright -- verify UI, capture screenshots, view logs |
| **MCP Builder** | Anthropic | Guide for building production-quality MCP servers in TypeScript or Python |
| **Frontend Design** | Anthropic | Distinctive, production-grade frontend interfaces that avoid generic aesthetics |
| **Doc Co-Authoring** | Anthropic | Structured workflow for writing specs, proposals, RFCs, and guides |
| **Algorithmic Art** | Anthropic | Generative art with p5.js, seeded randomness, and interactive parameters |
| **Agent Evaluation** | Community | Testing and benchmarking LLM agents with reliability metrics |
| **AI Agents Architect** | Community | Design autonomous agents with tool use, memory, and orchestration |
| **Skill Creator** | Community | Meta-skill for creating and packaging new Claude Code skills |
| **Web Design Guidelines** | Vercel | Review UI code for accessibility, design, and UX best practices |
| **Social Content** | Community | Social media content creation with platform-specific strategies |

### Hooks

| Tool | Author | Description |
|------|--------|-------------|
| **Secret Guard** | Community | Blocks file writes containing API keys, tokens, passwords, or credentials |
| **TODO Tracker** | Community | Surfaces TODO/FIXME/HACK comments after file writes |
| **Test Watcher** | Community | Reminds you to create tests when source files are modified |
| **Console Log Guard** | Community | Warns on debug statements in production code |
| **Large File Warning** | Community | Flags files exceeding 500 lines |
| **Dependency Change** | Community | Reminds you to install after dependency files change |
| **ACK Import Guard** | koenrohrer | Enforces `.js` extensions on relative imports (ESM) |
| **ACK Path Guard** | koenrohrer | Detects hardcoded paths that should use `ClaudeCodePaths` |
| **ACK Throw Guard** | koenrohrer | Catches throw statements in parser files |
| **ACK Raw FS Guard** | koenrohrer | Warns on raw `fs.writeFile` instead of `FileIOService` |
| **ACK Scope Exhaustive** | koenrohrer | Flags switch statements missing default case on enums |
| **ACK Conventional Commit** | koenrohrer | Validates conventional commit message format |

### Commands

| Tool | Author | Description |
|------|--------|-------------|
| **Scaffold Feature** | Community | Scaffold source + test files following project conventions |
| **Write Tests** | Community | Generate thorough unit tests for any source file |
| **Review Code** | Community | Focused code review for bugs, security, and performance |
| **Explain Codebase** | Community | Concise architectural overview of a project or subsystem |
| **Create Migration** | Community | Database migration file for any framework (Prisma, Knex, etc.) |
| **Refactor File** | Community | Analyze and apply targeted refactoring improvements |
| **ACK Add Parser** | koenrohrer | Scaffold a new ACK parser with adapter pattern and tests |
| **ACK Add Service** | koenrohrer | Scaffold a new ACK service with DI and Result types |
| **ACK Validate Patterns** | koenrohrer | Audit ACK codebase for pattern violations |
| **ACK Add Tree Command** | koenrohrer | Add a VS Code command with handler and menu registration |
| **ACK Add Tool Type** | koenrohrer | Walk through adding a new tool type end-to-end |
| **ACK Debug Tool Loading** | koenrohrer | Trace the read pipeline to debug tool loading issues |

---

## How It Works

ACK fetches `registry.json` from this repo at runtime. Each entry points to a tool directory containing:

```
tools/
└── my-tool/
    ├── manifest.json    ← Install config (type, command, args, env, files)
    ├── README.md        ← Shown in the marketplace detail view
    └── SKILL.md         ← Skill content (skills only)
```

When a user clicks **Install** in the ACK marketplace, the extension reads `manifest.json` and writes the tool into their Claude Code configuration.

---

## Contributing a Tool

### 1. Create a tool directory

```bash
mkdir tools/my-tool
```

### 2. Write a `manifest.json`

**For an MCP server:**

```json
{
  "type": "mcp_server",
  "name": "my-server",
  "version": "1.0.0",
  "description": "What this server does.",
  "runtime": "npx",
  "config": {
    "command": "npx",
    "args": ["-y", "@scope/package-name"],
    "env": {
      "API_KEY": {
        "required": true,
        "sensitive": true,
        "description": "Your API key"
      }
    }
  }
}
```

**For a skill:**

```json
{
  "type": "skill",
  "name": "my-skill",
  "version": "1.0.0",
  "description": "What this skill does.",
  "files": ["SKILL.md"],
  "config": {}
}
```

**For a command:**

```json
{
  "type": "command",
  "name": "my-command",
  "version": "1.0.0",
  "description": "What this command does.",
  "files": ["my-command.md"],
  "config": {}
}
```

**For a hook:**

```json
{
  "type": "hook",
  "name": "my-hook",
  "version": "1.0.0",
  "description": "What this hook does.",
  "config": {
    "event": "PreToolUse",
    "matcher": "Write|Edit",
    "hooks": [
      {
        "type": "command",
        "command": "bash -c 'echo \"hook triggered\" >&2'"
      }
    ]
  }
}
```

### 3. Write a `README.md`

This is rendered in the marketplace detail view. Keep it concise: what the tool does, use cases, any requirements or setup steps.

### 4. Add the tool to `registry.json`

Add an entry to the `tools` array:

```json
{
  "id": "my-tool",
  "name": "My Tool",
  "type": "mcp_server",
  "description": "Short description for the marketplace card.",
  "author": "your-name",
  "version": "1.0.0",
  "tags": ["relevant", "tags"],
  "stars": 0,
  "installs": 0,
  "readmePath": "tools/my-tool/README.md",
  "contentPath": "tools/my-tool",
  "createdAt": "2026-01-01T00:00:00Z",
  "updatedAt": "2026-01-01T00:00:00Z"
}
```

### 5. Open a pull request

Submit your PR with the new tool directory and the `registry.json` update. Include a brief description of what the tool does and how you've tested it.

---

## Manifest Reference

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `type` | `string` | yes | `mcp_server`, `skill`, `command`, or `hook` |
| `name` | `string` | yes | Tool name (used as the config key) |
| `version` | `string` | yes | Semver version |
| `description` | `string` | no | Shown in the marketplace |
| `runtime` | `string` | no | Runtime hint for MCP servers (`npx`, `uvx`, `node`, `python`) |
| `files` | `string[]` | no | Files to download for skills/commands (default: `["SKILL.md"]`) |
| `config.command` | `string` | MCP only | Executable command |
| `config.args` | `string[]` | MCP only | Command arguments |
| `config.env` | `object` | no | Environment variables with `required`, `sensitive`, `description`, `defaultValue` |
| `config.event` | `string` | hook only | Hook trigger event (`PreToolUse`, `PostToolUse`, `Notification`, `Stop`) |
| `config.matcher` | `string` | no | Regex pattern matching tool names (e.g., `Write\|Edit`) |
| `config.hooks` | `array` | hook only | Array of `{ "type": "command", "command": "..." }` objects |

---

## Using a Custom Registry

Teams can fork this repo and point ACK at their own copy. In VS Code settings:

```jsonc
"ack.registrySources": [
  {
    "id": "my-team",
    "name": "Team Tools",
    "owner": "my-org",
    "repo": "tool-registry",
    "branch": "main",
    "indexPath": "registry.json"
  }
]
```

The default community registry is always included alongside custom sources.

---

## License

[MIT](https://github.com/koenrohrer/ack/blob/master/LICENSE) -- Koen Rohrer
