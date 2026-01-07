HVAC Inbox Intelligence Agent

An automated email-triage and dispatch system for HVAC companies that detects web form requests, service emergencies, and operational emails—instantly notifying the right team via Slack.

n8n · Gmail · Slack · OpenAI

LIVE NOTIFICATIONS
Slack alerts are sent in real time to:
- #new-leads
- #dispatch
- #dispatch-emergency
- #inbox-review

OVERVIEW
This project answers the operational question:
“How do HVAC companies ensure no lead, service request, or emergency email is ever missed?”

The system automatically:
- Monitors the HVAC company inbox in real time
- Cleans and normalizes inbound email content
- Detects web form submissions using deterministic rules
- Classifies incoming emails into HVAC-specific operational categories
- Extracts structured customer and job details using AI
- Sends actionable Slack notifications to dispatch and sales teams
- Routes emails to the correct inbox, label, or department
- Applies safeguards for failures, ambiguity, and duplicate processing

KEY CAPABILITIES
- Emergency detection (gas smell, CO, smoke, electrical risk)
- Form submission recognition (website, CRM, intake tools)
- Lead & service request parsing into structured JSON
- Smart inbox routing (billing, scheduling, maintenance, HR, vendors)
- Consistent Gmail labeling for auditability
- “Needs Review” safety bucket for low-confidence messages

TECH STACK
Workflow Automation: n8n
Email Ingestion: Gmail API
Classification: JavaScript (rule-based HVAC classifier)
Data Extraction: OpenAI (LangChain agent)
Notifications: Slack API
Logging / Dedupe: Gmail Labels

ARCHITECTURE
Gmail Inbox
→ Email Normalization
→ Form Signal Detector
→ AI Data Extraction
→ Slack Dispatch + Gmail Labels

If not a form:
→ HVAC Classifier
→ Routing Switch
→ Slack Alerts + Gmail Labels + Forwarding

REPOSITORY STRUCTURE
hvac-inbox-agent/
- README.md
- n8n-workflows/hvac-inbox-agent.json
- docs/setup-guide.md
- docs/slack-message-schema.md

HVAC EMAIL CATEGORIES
1. Emergency
2. Service Request / Repair
3. New Lead / Estimate Request
4. Maintenance / Membership
5. Scheduling / Dispatch Updates
6. Billing / Invoice
7. Vendor / Partner
8. Hiring / HR
9. Spam / Marketing
10. Needs Review

SETUP INSTRUCTIONS
See setup-guide.md for:
- Gmail labels and permissions
- Slack channel configuration
- n8n credential setup
- Workflow import and testing

SKILLS DEMONSTRATED
- AI operations automation
- Email intelligence and routing
- Prompt engineering for structured extraction
- Fault-tolerant workflow design
- Human-in-the-loop safety systems
- Business process automation

FUTURE ENHANCEMENTS
- CRM integration (ServiceTitan, Jobber, Housecall Pro)
- Persistent deduplication datastore
- Zip-code–based dispatch routing
- SMS escalation for emergencies
- Auto job creation
- After-hours escalation logic

