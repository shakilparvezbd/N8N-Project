# Speed-to-Lead Automation Workflow
A robust, production-grade Speed-to-Lead workflow built in n8n designed specifically for real estate agents and lead-generation agencies. It ensures zero lead leakage by combining data normalization, instant multi-channel alerts, CRM logging, duplicate suppression, and automated fail-safe error handling.

🚀 What It Does
When a new lead hits the webhook, the workflow executes the following steps in milliseconds:

Data Intake & Sanitization: Receives the payload and filters out spam, bot submissions, or completely blank records.

Normalization & Validation: Cleans and formats phone numbers to international standards, validates email syntax, and handles nested or flat JSON payloads safely.

Duplicate Prevention: Tracks recent lead submissions via a sliding-window memory store to ignore accidental duplicate submits.

CRM Logging: Automatically appends valid leads directly into your designated Google Sheets CRM.

Instant Notifications: Dispatches high-priority lead cards directly to the agent via Telegram using HTML formatting.

Auto-Reply Engagement: Sends an immediate confirmation email to the lead to keep response times under 5 minutes.

🛡️ Reliability & Error Handling (Fail-Safe Mechanism)
Most lead workflows break silently when an integration fails. This system includes a comprehensive Global Error Handler:

Granular Try/Catch: Every execution node is configured with explicit error routing (Continue using error output).

Automated Failure Alerts: If a CRM write, email dispatch, or webhook connection fails, the system bypasses the crash and routes a detailed error notification to your dedicated Telegram error-monitoring channel.


📂 Workflow Architecture
Lead Intake: Webhook trigger node (POST)

Normalize & Validate: Custom JavaScript code node for sanitization, validation, and deduplication logic.

Routing Decision Nodes: Condition branches checking for validity, email availability, and deduplication status.

Integrations: Google Sheets (CRM), Telegram Bot API (Alerts), Gmail/SMTP (Auto-replies).

Error Management: Global Error Trigger coupled with automated Telegram failure alerts.