HVAC Inbox Intelligence Agent

An automated inbox intelligence system that classifies, extracts, and routes HVAC emails in real time—ensuring leads, service requests, and emergencies are never missed.

N8N · Gmail · Slack · OpenAI

🔔 Live Notifications
Slack alerts are sent in real time to channels such as:

#new-leads

#dispatch

#dispatch-emergency

#inbox-review

📊 Overview
This project answers the question:
How do HVAC companies reliably handle leads, service requests, and emergencies without inbox overload?

The system automatically:

Monitors the HVAC inbox continuously

Cleans and normalizes inbound email content

Detects website and CRM form submissions

Classifies emails into HVAC-specific operational categories

Extracts structured customer and job details

Sends actionable Slack alerts to the right team

Applies Gmail labels for auditability and deduplication

Falls back to human review when confidence is low

🔍 Key Capabilities

Emergency detection (gas smell, CO, smoke, electrical risk)

Website and CRM form recognition

Lead and service request extraction

Smart inbox routing (billing, scheduling, maintenance, HR, vendors)

Consistent Gmail labeling

Human-in-the-loop safety fallback

🛠️ Tech Stack

Component	Technology
Workflow Automation	N8N
Email Ingestion	Gmail API
Classification	JavaScript (rule-based HVAC classifier)
Data Extraction	OpenAI (LangChain agent)
Notifications	Slack API
Logging / Dedupe	Gmail Labels
Version Control	Git / GitHub

📐 Architecture

Gmail Inbox
→ Email Normalization
→ Form Signal Detection
→ AI Data Extraction
→ Slack Alerts + Gmail Labels

If not a form:
→ HVAC Classifier
→ Routing Switch
→ Slack Alerts + Gmail Labels + Forwarding


📁 Repository Structure

hvac-inbox-agent/
├── README.md
├── n8n-workflows/
│   └── hvac-inbox-agent.json
├── docs/
│   ├── setup-guide.md
│   └── slack-message-schema.md


📂 HVAC Email Categories

Emergency

Service Request / Repair

New Lead / Estimate Request

Maintenance / Membership

Scheduling / Dispatch Updates

Billing / Invoice

Vendor / Partner

Hiring / HR

Spam / Marketing

Needs Review

⚙️ Setup Instructions

Create required Gmail labels

Create Slack channels

Configure credentials in N8N

Import the workflow JSON

Test with sample emails

🧠 Skills Demonstrated

AI operations automation

Email intelligence and routing

Prompt engineering for structured extraction

Fault-tolerant workflow design

Human-in-the-loop safety systems

Business process automation

📬 Contact
Theodore Romero
LinkedIn: linkedin.com/in/theodoreromero
Email: theodore.romero@email.com

📄 License
This project is open source and available under the MIT License.
