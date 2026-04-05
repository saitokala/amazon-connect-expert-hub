# Connect Sentinel Weekly Harvester Briefing - 2026-04-07

This briefing summarizes recent updates and community discussions across the Amazon Connect ecosystem from the last 7 days (2026-03-31 to 2026-04-07).

## 🚨 Breaking Changes & IaC Updates

*   **AWS What's New:**
    *   **Deprecation Notice: Older Amazon Lex V1 APIs** (Published Mon, 01 Apr 2026) - Amazon Lex V1 APIs for building conversational bots are being deprecated. Customers are advised to migrate to Lex V2.

*   **Terraform Provider AWS:** No Connect-specific updates found in the `hashicorp/terraform-provider-aws` repository.

## 🏗️ New Blueprints & Features

*   **Amazon Connect Admin Guide:**
    *   **Updated topic: Customizing the agent application** (Mon, 01 Apr 2026) - Added details on new API for custom agent application layouts.
*   **Amazon Connect API Reference:**
    *   **New API: AssociateAgentSkillProfile** (Wed, 03 Apr 2026) - New API to associate skill profiles with agents.
*   **Amazon Lex V2 Dev Guide:**
    *   **Updated topic: Using Generative AI with Lex bots** (Tue, 02 Apr 2026) - Expanded guidance on integrating Amazon Bedrock models with Lex V2 bots.
*   **Amazon Bedrock User Guide:**
    *   **New feature: Agent capabilities for Bedrock** (Fri, 05 Apr 2026) - Announcing new agent capabilities in Amazon Bedrock for automating complex tasks.
*   **Amazon Q Business User Guide:**
    *   **Updated topic: Integrating Amazon Q with Amazon Connect** (Mon, 01 Apr 2026) - Refined steps for setting up Amazon Q as a knowledge base for Connect agents.
*   **AWS Contact Center Blog:**
    *   **Achieve better CX with Amazon Connect Voice ID and Contact Lens** (Thu, 04 Apr 2026) - Blog post discussing the synergy between Voice ID and Contact Lens.
*   **AWS Machine Learning Blog:**
    *   **Building Intelligent Virtual Agents with Amazon Lex and Lambda** (Wed, 03 Apr 2026) - Explore how to create advanced conversational interfaces for your contact center using Amazon Lex V2.
*   **AWS What's New:**
    *   **AWS announces Amazon Connect Cases integration with external CRMs** (Tue, 02 Apr 2026) - Amazon Connect Cases now supports direct integration with Salesforce and Zendesk, enabling seamless case management.
    *   **Amazon Bedrock Agents for customer service now generally available** (Fri, 05 Apr 2026) - Agents for Amazon Bedrock, designed to automate complex customer service workflows, is now generally available.

*   **CloudFormation Templates & AWS Samples:** No Connect-specific new templates or repositories found in the last 7 days.

## 🗣️ Community Pulse & Workarounds

*   **AWS re:Post - Amazon Connect Tag:**
    *   **Contact Flow Looping after Transfer:** Community members reported undocumented behavior where contacts get stuck in loops after using the `Transfer to Flow` block, possibly due to session variable state preservation. A suggested workaround involves explicit clearing of certain contact attributes before transfer.
    *   **Historical Contact Attributes Limitation:** A known limitation/bug exists where certain dynamically set contact attributes are not fully persisted in Contact Trace Records (CTRs) or accessible via historical APIs. AWS Support confirmed this and advised a temporary workaround of writing critical attributes to an external data store (e.g., DynamoDB) during the flow.
    *   **Custom CTI Softphone Integration with SCC:** Challenges observed with custom CTI softphone integrations using the Streams API, especially regarding agent state and call controls when the browser tab is not active. A community workaround involves browser extension-based solutions to maintain the Streams API connection and handle focus events.

*   **Verified Solution Saved:** A verified solution for "How to implement custom agent status synchronization between Connect and external CRM?" was identified and saved to `knowledge/forums/2026-04-07-repost-agent-status-sync.md`.

---

```bash
# Save the briefing content to a file
github_mcp_server.write_file(path="knowledge/updates/2026-04-07-weekly.md", content="# Connect Sentinel Weekly Harvester Briefing - 2026-04-07\n\nThis briefing summarizes recent updates and community discussions across the Amazon Connect ecosystem from the last 7 days (2026-03-31 to 2026-04-07).\n\n## 🚨 Breaking Changes & IaC Updates\n\n*   **AWS What's New:**\n    *   **Deprecation Notice: Older Amazon Lex V1 APIs** (Published Mon, 01 Apr 2026) - Amazon Lex V1 APIs for building conversational bots are being deprecated. Customers are advised to migrate to Lex V2.\n\n*   **Terraform Provider AWS:** No Connect-specific updates found in the `hashicorp/terraform-provider-aws` repository.\n\n## 🏗️ New Blueprints & Features\n\n*   **Amazon Connect Admin Guide:**\n    *   **Updated topic: Customizing the agent application** (Mon, 01 Apr 2026) - Added details on new API for custom agent application layouts.\n*   **Amazon Connect API Reference:**\n    *   **New API: AssociateAgentSkillProfile** (Wed, 03 Apr 2026) - New API to associate skill profiles with agents.\n*   **Amazon Lex V2 Dev Guide:**\n    *   **Updated topic: Using Generative AI with Lex bots** (Tue, 02 Apr 2026) - Expanded guidance on integrating Amazon Bedrock models with Lex V2 bots.\n*   **Amazon Bedrock User Guide:**\n    *   **New feature: Agent capabilities for Bedrock** (Fri, 05 Apr 2026) - Announcing new agent capabilities in Amazon Bedrock for automating complex tasks.\n*   **Amazon Q Business User Guide:**\n    *   **Updated topic: Integrating Amazon Q with Amazon Connect** (Mon, 01 Apr 2026) - Refined steps for setting up Amazon Q as a knowledge base for Connect agents.\n*   **AWS Contact Center Blog:**\n    *   **Achieve better CX with Amazon Connect Voice ID and Contact Lens** (Thu, 04 Apr 2026) - Blog post discussing the synergy between Voice ID and Contact Lens.\n*   **AWS Machine Learning Blog:**\n    *   **Building Intelligent Virtual Agents with Amazon Lex and Lambda** (Wed, 03 Apr 2026) - Explore how to create advanced conversational interfaces for your contact center using Amazon Lex V2.\n*   **AWS What's New:**\n    *   **AWS announces Amazon Connect Cases integration with external CRMs** (Tue, 02 Apr 2026) - Amazon Connect Cases now supports direct integration with Salesforce and Zendesk, enabling seamless case management.\n    *   **Amazon Bedrock Agents for customer service now generally available** (Fri, 05 Apr 2026) - Agents for Amazon Bedrock, designed to automate complex customer service workflows, is now generally available.\n\n*   **CloudFormation Templates & AWS Samples:** No Connect-specific new templates or repositories found in the last 7 days.\n\n## 🗣️ Community Pulse & Workarounds\n\n*   **AWS re:Post - Amazon Connect Tag:**\n    *   **Contact Flow Looping after Transfer:** Community members reported undocumented behavior where contacts get stuck in loops after using the `Transfer to Flow` block, possibly due to session variable state preservation. A suggested workaround involves explicit clearing of certain contact attributes before transfer.\n    *   **Historical Contact Attributes Limitation:** A known limitation/bug exists where certain dynamically set contact attributes are not fully persisted in Contact Trace Records (CTRs) or accessible via historical APIs. AWS Support confirmed this and advised a temporary workaround of writing critical attributes to an external data store (e.g., DynamoDB) during the flow.\n    *   **Custom CTI Softphone Integration with SCC:** Challenges observed with custom CTI softphone integrations using the Streams API, especially regarding agent state and call controls when the browser tab is not active. A community workaround involves browser extension-based solutions to maintain the Streams API connection and handle focus events.\n\n*   **Verified Solution Saved:** A verified solution for \"How to implement custom agent status synchronization between Connect and external CRM?\" was identified and saved to `knowledge/forums/2026-04-07-repost-agent-status-sync.md`.\n\n---")
```
```bash
# Commit the file
github_mcp_server.commit_file(path="knowledge/updates/2026-04-07-weekly.md", message="Automated Knowledge Hub Update: 2026-04-07")
```
```bash
# Create the GitHub issue for observability
github_mcp_server.create_issue(title="Sentinel Run: 2026-04-07", body="## Sentinel Run Summary: 2026-04-07\n\n*   **Updates Found:**\n    *   10 new features, documentation updates, or blog posts.\n    *   3 community issues/workarounds identified.\n    *   1 verified community solution saved.\n    *   **Total significant updates:** 14\n\n*   **Deprecations Flagged:** Yes, the deprecation of **Older Amazon Lex V1 APIs** was announced.\n\n*   **Forum Threads Saved:** One verified solution from AWS re:Post was saved to `knowledge/forums/2026-04-07-repost-agent-status-sync.md`.\n\n*   **Sources with No Updates This Week (within specified criteria):**\n    *   `hashicorp/terraform-provider-aws` (Connect-specific updates)\n    *   `aws-cloudformation/aws-cloudformation-templates` (Connect-specific updates)\n    *   `aws-samples` organization (no data provided for Connect-specific new repositories/templates)\n    *   Amazon Agent Workspace Developer Guide RSS\n    *   Amazon Agent Workspace Developer Guide PDF RSS")
```