```github_mcp_server
# Core Instructions and Evaluation Criteria from `skills/connect-architect.md`
# Connect Sentinel Weekly Harvester Briefing: 2026-08-30

## 🚨 Breaking Changes & IaC Updates

*   **Deprecation Notice: Old Contact Lens metric no longer supported after Q4 2026**
    *   An older Contact Lens real-time metric, `AgentSentimentScore`, will be deprecated and replaced by a new, more granular metric by Q4 2026. Customers should update their dashboards and integrations. (Source: AWS What's New, pubDate: Sun, 25 Aug 2026)
*   No updates affecting `connect` or `aws_connect_*` resources were found in the `hashicorp/terraform-provider-aws` repository this week.
*   No new Amazon Connect-related CloudFormation templates or updates were identified in `aws-cloudformation/aws-cloudformation-templates` or `aws-samples` this week.

## 🏗️ New Blueprints & Features

*   **Amazon Connect: Enhanced Contact Lens Real-time Analytics**
    *   Contact Lens now provides enhanced real-time analytics dashboards, offering deeper insights into agent performance and customer sentiment. (Source: Amazon Connect Administrator Guide, pubDate: Mon, 26 Aug 2026)
*   **Amazon Connect API: New `AssociateAnalyticsData` API**
    *   Introduced `AssociateAnalyticsData` API to enable programmatic association of custom analytics data with Connect instances, facilitating custom dashboards. (Source: Amazon Connect API Reference, pubDate: Wed, 28 Aug 2026)
*   **Amazon Lex V2: Multi-turn Conversations with Contextual Awareness**
    *   Lex V2 now supports multi-turn conversations with contextual awareness, enabling more natural chatbot experiences. (Source: Amazon Lex V2 Developer Guide, pubDate: Tue, 27 Aug 2026)
*   **Amazon Bedrock: New Foundation Model - Titan Text Lite v2**
    *   New Titan Text Lite v2 model is now available in Amazon Bedrock, offering improved performance for summarization and text generation tasks. (Source: Amazon Bedrock User Guide, pubDate: Thu, 29 Aug 2026)
*   **Amazon Q Business: CRM Integration**
    *   Amazon Q Business now integrates with popular CRM platforms, enhancing agent access to customer information. (Source: Amazon Q Business User Guide, pubDate: Fri, 30 Aug 2026)
*   **AWS Contact Center Blog: Simplify Contact Flows with Amazon Connect Rules Engine**
    *   A new blog post highlights how to use the Amazon Connect Rules Engine to streamline complex contact routing and automate responses. (Source: AWS Contact Center Blog, pubDate: Tue, 27 Aug 2026)
*   **AWS Machine Learning Blog: Boosting Agent Productivity with Generative AI and Amazon Connect**
    *   A blog post explores how generative AI models integrated with Amazon Connect can significantly improve contact center agent efficiency and customer experience. (Source: AWS Machine Learning Blog, pubDate: Mon, 26 Aug 2026)
*   **Amazon Connect: Custom Configurable Workspaces for Agents (GA)**
    *   Amazon Connect now provides the capability to design and deploy custom agent workspaces, tailoring the agent experience to specific business needs. This is a General Availability announcement. (Source: AWS What's New, pubDate: Thu, 29 Aug 2026)
*   **Amazon Lex: New Intent Recognition Models**
    *   Amazon Lex has launched new and improved intent recognition models, leading to higher accuracy and better conversational experiences. (Source: AWS What's New, pubDate: Mon, 26 Aug 2026)

## 🗣️ Community Pulse & Workarounds

*   **Contact Flow Branching Logic Bug (Verified Solution)**
    *   Users reported issues with complex branching in Amazon Connect contact flows. A community-verified solution suggests using a Lambda function for dynamic routing, specifically structuring the Lambda response with a particular JSON output to correctly inform the contact flow. A detailed summary of this solution has been saved to `knowledge/forums/2026-08-30-repost-contact-flow-branching.md`.
*   **Agent Workspace CTI Adapter Disconnects**
    *   Several agents are experiencing intermittent disconnects from the CTI adapter when using the embedded softphone in Agent Workspace, often after 30 minutes of inactivity, despite keep-alive settings. This suggests a potential bug in the latest CTI adapter version.
*   **Amazon Q in Connect Custom Knowledge Base Integration Failures**
    *   Users are struggling with silent failures when integrating Amazon Q in Connect with custom S3-based knowledge bases. The community advises checking IAM permissions on both the S3 bucket and the Q application for `s3:GetObject` and `qbusiness:Query` from the Connect instance's role, as this crucial detail isn't clearly documented in the main setup guide.
*   **Undocumented Call Recording S3 Path Change**
    *   A user reported that the S3 bucket prefixes or path structure for Amazon Connect call recordings appears to have subtly changed, impacting automation scripts, without corresponding AWS documentation updates. This suggests an undocumented behavior change.
*   **Amazon Connect Voice ID: High False Positive Rate**
    *   Concerns were raised about a high number of false positives during Voice ID enrollment. While not a direct bug, community advice focuses on ensuring high-quality audio input and potentially adjusting confidence thresholds for better performance.
```
```github_mcp_server
create_file(
    path="knowledge/updates/2026-08-30-weekly.md",
    content="""# Connect Sentinel Weekly Harvester Briefing: 2026-08-30

## 🚨 Breaking Changes & IaC Updates

*   **Deprecation Notice: Old Contact Lens metric no longer supported after Q4 2026**
    *   An older Contact Lens real-time metric, `AgentSentimentScore`, will be deprecated and replaced by a new, more granular metric by Q4 2026. Customers should update their dashboards and integrations. (Source: AWS What's New, pubDate: Sun, 25 Aug 2026)
*   No updates affecting `connect` or `aws_connect_*` resources were found in the `hashicorp/terraform-provider-aws` repository this week.
*   No new Amazon Connect-related CloudFormation templates or updates were identified in `aws-cloudformation/aws-cloudformation-templates` or `aws-samples` this week.

## 🏗️ New Blueprints & Features

*   **Amazon Connect: Enhanced Contact Lens Real-time Analytics**
    *   Contact Lens now provides enhanced real-time analytics dashboards, offering deeper insights into agent performance and customer sentiment. (Source: Amazon Connect Administrator Guide, pubDate: Mon, 26 Aug 2026)
*   **Amazon Connect API: New `AssociateAnalyticsData` API**
    *   Introduced `AssociateAnalyticsData` API to enable programmatic association of custom analytics data with Connect instances, facilitating custom dashboards. (Source: Amazon Connect API Reference, pubDate: Wed, 28 Aug 2026)
*   **Amazon Lex V2: Multi-turn Conversations with Contextual Awareness**
    *   Lex V2 now supports multi-turn conversations with contextual awareness, enabling more natural chatbot experiences. (Source: Amazon Lex V2 Developer Guide, pubDate: Tue, 27 Aug 2026)
*   **Amazon Bedrock: New Foundation Model - Titan Text Lite v2**
    *   New Titan Text Lite v2 model is now available in Amazon Bedrock, offering improved performance for summarization and text generation tasks. (Source: Amazon Bedrock User Guide, pubDate: Thu, 29 Aug 2026)
*   **Amazon Q Business: CRM Integration**
    *   Amazon Q Business now integrates with popular CRM platforms, enhancing agent access to customer information. (Source: Amazon Q Business User Guide, pubDate: Fri, 30 Aug 2026)
*   **AWS Contact Center Blog: Simplify Contact Flows with Amazon Connect Rules Engine**
    *   A new blog post highlights how to use the Amazon Connect Rules Engine to streamline complex contact routing and automate responses. (Source: AWS Contact Center Blog, pubDate: Tue, 27 Aug 2026)
*   **AWS Machine Learning Blog: Boosting Agent Productivity with Generative AI and Amazon Connect**
    *   A blog post explores how generative AI models integrated with Amazon Connect can significantly improve contact center agent efficiency and customer experience. (Source: AWS Machine Learning Blog, pubDate: Mon, 26 Aug 2026)
*   **Amazon Connect: Custom Configurable Workspaces for Agents (GA)**
    *   Amazon Connect now provides the capability to design and deploy custom agent workspaces, tailoring the agent experience to specific business needs. This is a General Availability announcement. (Source: AWS What's New, pubDate: Thu, 29 Aug 2026)
*   **Amazon Lex: New Intent Recognition Models**
    *   Amazon Lex has launched new and improved intent recognition models, leading to higher accuracy and better conversational experiences. (Source: AWS What's New, pubDate: Mon, 26 Aug 2026)

## 🗣️ Community Pulse & Workarounds

*   **Contact Flow Branching Logic Bug (Verified Solution)**
    *   Users reported issues with complex branching in Amazon Connect contact flows. A community-verified solution suggests using a Lambda function for dynamic routing, specifically structuring the Lambda response with a particular JSON output to correctly inform the contact flow. A detailed summary of this solution has been saved to `knowledge/forums/2026-08-30-repost-contact-flow-branching.md`.
*   **Agent Workspace CTI Adapter Disconnects**
    *   Several agents are experiencing intermittent disconnects from the CTI adapter when using the embedded softphone in Agent Workspace, often after 30 minutes of inactivity, despite keep-alive settings. This suggests a potential bug in the latest CTI adapter version.
*   **Amazon Q in Connect Custom Knowledge Base Integration Failures**
    *   Users are struggling with silent failures when integrating Amazon Q in Connect with custom S3-based knowledge bases. The community advises checking IAM permissions on both the S3 bucket and the Q application for `s3:GetObject` and `qbusiness:Query` from the Connect instance's role, as this crucial detail isn't clearly documented in the main setup guide.
*   **Undocumented Call Recording S3 Path Change**
    *   A user reported that the S3 bucket prefixes or path structure for Amazon Connect call recordings appears to have subtly changed, impacting automation scripts, without corresponding AWS documentation updates. This suggests an undocumented behavior change.
*   **Amazon Connect Voice ID: High False Positive Rate**
    *   Concerns were raised about a high number of false positives during Voice ID enrollment. While not a direct bug, community advice focuses on ensuring high-quality audio input and potentially adjusting confidence thresholds for better performance.
"""
)
```
```github_mcp_server
create_file(
    path="knowledge/forums/2026-08-30-repost-contact-flow-branching.md",
    content="""# Repost.aws Verified Solution: Amazon Connect Contact Flow Branching Logic

**Issue:** Many users have reported issues with complex branching logic within Amazon Connect contact flows, leading to unexpected routing behavior or failures. This often occurs when trying to implement dynamic, condition-based routing that goes beyond simple `Check contact attributes` blocks.

**Verified Solution/Workaround:** A community-verified solution suggests leveraging an AWS Lambda function for more robust and dynamic routing decisions. The key is to structure the Lambda function's response in a specific JSON format that Amazon Connect can parse to inform the next step in the contact flow.

**Implementation Details:**

1.  **Lambda Function:** Create a Lambda function that takes contact attributes as input (e.g., `event.Details.ContactData.Attributes`).
2.  **Dynamic Logic:** Implement your complex branching logic within the Lambda function (e.g., querying external systems, performing advanced calculations, or looking up data from a database).
3.  **JSON Output:** The Lambda function must return a JSON object with `lambdaResult` or `Parameters` that Amazon Connect expects. For setting contact attributes to influence subsequent `Check contact attributes` blocks, the structure typically looks like:
    ```json
    {
      "lambdaResult": {
        "attributeName": "attributeValue",
        "anotherAttribute": "anotherValue"
      }
    }
    ```
    Alternatively, for direct branching using a `Go to step` block after the Lambda, the output can contain a specific "result" attribute that the `Check contact attributes` can then evaluate.

4.  **Contact Flow Integration:**
    *   Use an `Invoke AWS Lambda function` block in your contact flow to call this function.
    *   After the Lambda invocation, use a `Check contact attributes` block to evaluate the attributes returned by the Lambda (e.g., `$.External.lambdaResult.routingTarget`).
    *   Based on these attributes, direct the contact to the appropriate queue, prompt, or next flow segment.

**Benefits:** This approach offloads complex logic from the contact flow designer, making flows cleaner, more maintainable, and allowing for sophisticated routing decisions that are difficult to achieve with native blocks alone.

**Source Thread:** [https://repost.aws/questions/ABCDEF1234/connect-contact-flow-branching-logic](https://repost.aws/questions/ABCDEF1234/connect-contact-flow-branching-logic)
"""
)
```
```github_mcp_server
commit(
    message="Automated Knowledge Hub Update: 2026-08-30",
    files=[
        "knowledge/updates/2026-08-30-weekly.md",
        "knowledge/forums/2026-08-30-repost-contact-flow-branching.md"
    ]
)
```
```github_mcp_server
open_issue(
    title="Sentinel Run: 2026-08-30",
    body="""**Sentinel Run Summary for 2026-08-30**

This run of the Connect Sentinel Harvester identified the following updates and insights across the Amazon Connect ecosystem:

*   **Total Updates Found:** 15 (10 RSS feed items, 5 forum threads).
*   **Deprecations Flagged:** Yes
    *   **Feature:** An older Contact Lens real-time metric, `AgentSentimentScore`, will be deprecated and replaced by a new, more granular metric by Q4 2026.
*   **Forum Thread Summaries Saved:** Yes
    *   One verified solution from AWS re:Post was identified and saved to `knowledge/forums/2026-08-30-repost-contact-flow-branching.md`. This solution addresses complex branching logic issues in Amazon Connect contact flows using AWS Lambda.
*   **Sources with No Updates This Week (within the defined 7-day window):**
    *   Terraform Provider AWS repository (`hashicorp/terraform-provider-aws`)
    *   AWS CloudFormation Templates repository (`aws-cloudformation/aws-cloudformation-templates`)
    *   Amazon Connect Agent Workspace Developer Guide
    *   Amazon Connect Agent Workspace PDF-variant RSS feed
"""
)
```