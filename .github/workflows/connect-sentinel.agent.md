---
name: Connect Sentinel Weekly Harvester
on:
  schedule:
    - cron: '0 0 * * 0' # Runs every Sunday at midnight GMT
  workflow_dispatch:      # Allows manual triggering via GitHub UI
permissions:
  contents: write
env:
  GEMINI_API_KEY: ${{ secrets.GEMINI_API_KEY }}
tools:
  - name: github_mcp_server
  - name: bash  # Replaces web_search and firecrawl. Allows the agent to run 'curl' commands.
---
# Identity
Read your core instructions and evaluation criteria from `skills/connect-architect.md`. You are tracking the Amazon Connect ecosystem.
# Tasks
## 1. Terraform Provider Scan
Use the `github_mcp_server` to inspect the `hashicorp/terraform-provider-aws` repository.
- Review releases and merged PRs from the last 7 days.
- Filter strictly for updates affecting `connect` or `aws_connect_*` resources.
## 2. CloudFormation & AWS Samples Scan
Use the `github_mcp_server` to check `aws-cloudformation/aws-cloudformation-templates` and the `aws-samples` organization.
- Look for new repositories or templates containing "Amazon Connect" published in the last 7 days.
## 3. Official AWS Release Notes & Blog RSS Scan
Use the `bash` tool to `curl` each RSS feed below directly (no Jina Reader — RSS is already structured XML). For every feed, parse the `<item>` elements and **keep only those where `<pubDate>` falls within the last 7 days**. If a feed returns no items in that window, note it as "no updates this week."

### Core Amazon Connect
```bash
curl -s https://docs.aws.amazon.com/connect/latest/adminguide/doc-history.xml.rss
curl -s https://docs.aws.amazon.com/connect/latest/APIReference/doc-history.xml.rss
```

### Agent Workspace (Amazon Q in Connect)
```bash
curl -s https://docs.aws.amazon.com/agentworkspace/latest/devguide/doc-history.xml.rss
# Also try the alternate PDF-variant feed the team has confirmed active:
curl -s https://docs.aws.amazon.com/agentworkspace/latest/devguide/developer-guide.pdf.rss
```

### Integrated CCaaS Services
```bash
curl -s https://docs.aws.amazon.com/lexv2/latest/dg/doc-history.xml.rss
curl -s https://docs.aws.amazon.com/bedrock/latest/userguide/doc-history.xml.rss
curl -s https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/doc-history.xml.rss
```

### AWS Blogs
```bash
# Contact Center blog — all entries are relevant
curl -s https://aws.amazon.com/blogs/contact-center/feed/
# Machine Learning blog — filter entries whose <title> or <description> mentions: Connect, Lex, Bedrock, contact center, or agent
curl -s https://aws.amazon.com/blogs/machine-learning/feed/
```

### AWS What's New (global feed — filter required)
```bash
curl -s https://aws.amazon.com/about-aws/whats-new/recent/feed/
```
From this global feed, keep only items whose `<title>` or `<description>` contains at least one of these keywords (case-insensitive): `amazon connect`, `lex`, `bedrock`, `contact center`, `agent workspace`, `q in connect`, `wisdom`.

Extract any feature launches, GA announcements, or deprecation notices from the filtered results.
## 4. Community Forum Ingestion
Use the `bash` tool to `curl` the AWS re:Post Amazon Connect tag via Jina Reader:
- `curl -s https://r.jina.ai/https://repost.aws/tags/TAO7Z4bBQpS4i7reB-xPZqbw/amazon-connect`
- Identify the URLs of the top 5 most active threads from the last 7 days.
- Run a new `curl` command via Jina Reader for each of those 5 thread URLs to read their content.
- Extract mentions of undocumented behaviors, bugs, or community workarounds.
- **Special Action:** If a thread contains a verified solution for a complex issue, save that thread as a separate file in `knowledge/forums/` named `{CURRENT_DATE}-repost-{TOPIC_SLUG}.md` (e.g. `2026-03-23-repost-queue-routing.md`).
## 5. Output Generation
Synthesize the findings from Tasks 1, 2, 3, and 4 into a comprehensive weekly briefing.
- Format the output strictly as Markdown.
- Organize the briefing with the following headers:
  - `## 🚨 Breaking Changes & IaC Updates`
  - `## 🏗️ New Blueprints & Features`
  - `## 🗣️ Community Pulse & Workarounds`
- Save this briefing to the repository at: `knowledge/updates/{CURRENT_DATE}-weekly.md`.
- Commit the file to the `main` branch with the commit message: "Automated Knowledge Hub Update: {CURRENT_DATE}".
## 6. Run Observability
Use the `github_mcp_server` to open a GitHub issue titled `Sentinel Run: {CURRENT_DATE}` with a body summarising:
- How many updates were found across all sources.
- Whether any deprecations were flagged (and if so, which features).
- Whether any forum thread summaries were saved to `knowledge/forums/`.
- Any sources that returned no updates this week.
