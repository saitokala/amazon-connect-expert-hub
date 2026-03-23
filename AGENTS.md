# 🤖 Active Agentic Workflows

This repository employs several automated agents to maintain its "Super Intelligent" state.

### 1. The Sentinel (`connect-sentinel.agent.md`)

* **Trigger:** Scheduled (Cron: Every Sunday at Midnight) & Manual Dispatch.
* **Role:** The Harvester.
* **Duties:** Scans HashiCorp Terraform releases, AWS official documentation, and community forums. Dumps raw findings into `knowledge/updates/`.

### 2. The Synthesizer (`pattern-synthesizer.agent.md`)

* **Trigger:** Triggers automatically when The Sentinel completes a run.
* **Role:** The Architect.
* **Duties:** Reads the raw weekly updates. If a consistent workaround or new standard is found, it formats it into a permanent Best Practice document and saves it to `knowledge/patterns/`.

### 3. The Diagrammer (Manual Trigger via Codespace)

* **Trigger:** Prompt-based via Kiro CLI / Gemini.
* **Role:** The Visualizer.
* **Duties:** Monitors the `/ingest/pending/` folder. Converts uploaded webinar screenshots or PDFs into Mermaid.js code and Terraform snippets.

---

## AGENTS.md — Amazon Connect Expert Hub

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
