# Amazon Connect Expert Hub

A RAG-based knowledge base and automation hub for Amazon Connect expertise — combining live AWS documentation, community intelligence, and verified IaC patterns, surfaced via Claude Desktop.

## Structure

| Directory | Purpose |
|---|---|
| `.github/workflows/` | GitHub Agentic Workflow definitions (`.agent.md`) |
| `.github/mcp-configs/` | MCP tool definitions for Connect |
| `knowledge/updates/` | Raw weekly harvests from the Sentinel agent |
| `knowledge/patterns/` | Synthesised best practices from the Synthesiser agent |
| `knowledge/cheat-sheets/` | Quick-reference guides for CLI, Terraform, flows |
| `knowledge/forums/` | Community intelligence from re:Post, Reddit, and other forums |
| `ingest/pending/` | Staging area for raw content awaiting processing |
| `iac/modules/` | Verified, idempotent Terraform modules for Connect |
| `iac/blueprints/` | End-to-end CloudFormation reference architectures from AWS |
| `skills/` | System prompts and persona definitions for Claude Desktop |

## Agents

- **Connect Sentinel** — runs weekly, harvests AWS Connect release notes and documentation updates, commits raw output to `knowledge/updates/`
- **Pattern Synthesiser** — triggers on new files in `knowledge/updates/`, distils patterns and best practices into `knowledge/patterns/`

## Local Setup

Requires Claude Desktop with the following MCP servers configured:
- `awslabs.aws-documentation-mcp-server`
- `awslabs.aws-iac-mcp-server`
- `@modelcontextprotocol/server-github`
