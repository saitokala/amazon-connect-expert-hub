# 🧠 Amazon Connect Expert Hub

This repository is an autonomous, agent-driven knowledge base and Infrastructure-as-Code (IaC) library dedicated to Amazon Connect.

## 🏗️ Architecture

This project uses **GitHub Agentic Workflows** to stay continuously updated:

* **The Sentinel:** Wakes up weekly to scrape official AWS Docs, Terraform AWS Provider releases, and AWS re:Post forums.
* **The Synthesizer:** Converts raw weekly updates into verified architectural patterns.
* **The Knowledge Hub:** Stores idempotent Terraform modules, CloudFormation blueprints, and community workarounds.

## 📂 Directory Guide

| Directory | Purpose |
|---|---|
| `.github/workflows/` | GitHub Agentic Workflow definitions (`.agent.md`) |
| `.github/mcp-configs/` | MCP tool definitions for Connect |
| `knowledge/updates/` | Raw weekly harvests from the Sentinel agent |
| `knowledge/patterns/` | Synthesized best practices from the Synthesizer agent |
| `knowledge/cheat-sheets/` | Quick-reference guides for CLI, Terraform, flows |
| `knowledge/forums/` | Community intelligence from re:Post, Reddit, and other forums |
| `ingest/pending/` | Dropzone for manual webinar transcripts and PDFs |
| `iac/modules/` | Verified, idempotent Terraform modules for Connect |
| `iac/blueprints/` | End-to-end CloudFormation reference architectures from AWS |
| `skills/` | The core system prompts defining the AI's "Connect Architect" persona |

## 🤖 Usage

Connect your Claude Desktop or Gemini AI Studio to this repository via MCP (Model Context Protocol) using the configurations found in `.github/mcp-configs/`.

Requires the following MCP servers configured:
- `awslabs.aws-documentation-mcp-server`
- `awslabs.aws-iac-mcp-server`
- `@modelcontextprotocol/server-github`
