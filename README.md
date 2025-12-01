Multi-Agent Newsletter Automation (n8n)

An automated end-to-end newsletter creation system built using n8n, multi-agent LLM coordination, Google Sheets, and Gmail.

This workflow researches topics, generates newsletter sections, edits them, performs quality checks, and finally delivers a ready to send HTML newsletter with zero manual writing.


⚙️ Features
🔄 Automated Topic Fetching (Google Sheets)

Reads the next pending topic from your Newsletter Sheet and kicks off the full pipeline.

Initial & Sub-Topic Research (Tavily API)

Conducts initial research on the main topic.

Breaks the newsletter into 3 sub-topics and collects fresh articles for each.

Multi-Agent Workflow


Each agent performs a specialized job:

Planning Agent — Creates the newsletter outline (title + 3 topics).

Section Writer Agent — Writes three independent, researched sections in Markdown.

Editor Agent — Converts Markdown into polished, responsive HTML with formatting, layout, links, and structure.

QA Agent — Final accuracy, tone, and quality check before delivery.


🧩 Automated Formatting & Assembly

Merges all sections, applies styling rules, converts sources into a unified block, and prepares the final email body.


✉️ Auto Email Delivery (Gmail)

If approved: creates a newsletter email draft in Gmail with subject + HTML body.


❌ Rejection Handling (CRM Logging)

If the content fails QA:

Logs failure details

Saves feedback in a separate CRM sheet

Marks the topic for review


📅 Scheduled Execution

Runs automatically based on the n8n Schedule Trigger (e.g., every week at a set time).


🧩 Workflow Structure

Schedule Trigger
Get Topic (Google Sheets)
Initial Research (Tavily)
Planning Agent
Split Out Topics
Sub-Topic Research (Tavily)
Section Writer Agent
Aggregate Sections
Editor Agent
QA Agent + Structured Output Parser
IF Check (Approved or Rejected)
Gmail Draft Sender OR Rejection CRM Sheet


Recommended to use Google Sheets OAuth and Gmail OAuth credentials.

Tavily API is required for topic and article research.

Designed for creators, agencies, and businesses producing weekly newsletters.

Produces a fully polished HTML newsletter ready for sending or further edits.

Modular design: each agent can be replaced or upgraded independently.


🚀 Automation Value

Reduces newsletter creation time from hours to minutes

Ensures consistent weekly output

Produces research-backed, structured, high quality content

Offloads writing, editing, formatting, and QA

Ideal for scaling newsletter production without added workload


👤 Author

Created by: Hussain Faizi
Version: v1.0
Platform: n8n.io
