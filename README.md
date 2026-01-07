# HVAC Inbox Intelligence Agent

An automated email-triage and dispatch system for HVAC companies that detects web form requests, service emergencies, and operational emails—instantly notifying the right team via Slack.

**n8n · Gmail · Slack · OpenAI**

---

## 🔔 Live Notifications

Slack alerts are sent in real time to:

- `#new-leads`
- `#dispatch`
- `#dispatch-emergency`
- `#inbox-review`

> Slack channels and routing rules are fully configurable per company.

---

## 📊 Overview

This project answers the operational question:

**“How do HVAC companies ensure no lead, service request, or emergency email is ever missed?”**

The system automatically:

- Monitors the HVAC company inbox in real time
- Cleans and normalizes inbound email content
- Detects web form submissions using deterministic rules
- Classifies incoming emails into HVAC-specific operational categories
- Extracts structured customer and job details using AI
- Sends actionable Slack notifications to dispatch and sales teams
- Routes emails to the correct inbox, label, or department
- Applies safeguards for failures, ambiguity, and duplicate processing

---

## 🔍 Key Capabilities

- 🚨 **Emergency detection** (gas smell, CO, smoke, electrical risk)
- 🧾 **Form submission recognition** (website, CRM, and intake tools)
- 📞 **Lead & service request parsing** into structured JSON
- 📬 **Smart inbox routing** (billing, scheduling, maintenance, HR, vendors)
- 🏷️ **Consistent Gmail labeling** for auditability
- ⚠️ **“Needs Review” safety bucket** for low-confidence messages

---

## 🛠️ Tech Stack

| Component | Technology |
|---------|------------|
| Workflow Automation | n8n |
| Email Ingestion | Gmail API |
| Classification | JavaScript (rule-based HVAC classifier) |
| Data Extraction | OpenAI (LangChain agent) |
| Notifications | Slack API |
| Logging / Dedupe | Gmail Labels |

---

## 📐 Architecture

