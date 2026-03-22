# AGENTS.md — Amazon Connect Expert Hub

This file provides context for all AI agents operating in this repository.

## Repository Purpose

This is a living knowledge base for Amazon Connect expertise. It is maintained by a combination of human input and automated agentic workflows. Agents should treat this repository as a curated, version-controlled knowledge store — not a scratch pad.

## Directory Responsibilities

| Directory | Agent Behaviour |
|---|---|
| `knowledge/updates/` | **Write target** for the Connect Sentinel. One file per weekly run, named `YYYY-MM-DD-weekly.md`. Never delete existing files. |
| `knowledge/patterns/` | **Write target** for the Pattern Synthesiser. One file per distilled pattern, named by topic (e.g. `flow-error-handling.md`). Update existing files rather than duplicating. |
| `knowledge/cheat-sheets/` | Human-maintained. Agents should not modify these unless explicitly instructed. |
| `knowledge/forums/` | Community-injected content. Agents may read but should not overwrite. |
| `ingest/pending/` | Staging area. Agents may move files out of here into the appropriate `knowledge/` subdirectory after processing. |
| `iac/modules/` | Terraform modules. Agents should not modify without explicit instruction. |
| `iac/blueprints/` | CloudFormation reference architectures. Read-only for agents. |
| `skills/` | Persona definitions. Human-maintained only. |

## Naming Conventions

- Weekly update files: `YYYY-MM-DD-weekly.md`
- Pattern files: `kebab-case-topic.md`
- Forum files: `YYYY-MM-DD-source-topic.md` (e.g. `2026-03-22-repost-queue-routing.md`)

## Safe Outputs

Agents operating via GitHub Agentic Workflows are permitted to:
- Create files in `knowledge/updates/` and `knowledge/patterns/`
- Open pull requests for review
- Create issues to flag anomalies or gaps

Agents must NOT:
- Modify `iac/` content without explicit instruction
- Delete any existing knowledge files
- Modify `skills/connect-architect.md`
