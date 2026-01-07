# HVAC Inbox Intelligence Agent

An automated inbox triage and dispatch system for HVAC companies built with **n8n**, **Gmail**, **Slack**, and **OpenAI**.

This workflow ensures that **no lead, service request, emergency, or operational email is missed**, while routing each message to the correct team in real time.

---

## 🔔 What This Does

The HVAC Inbox Intelligence Agent:

- Monitors a shared HVAC inbox continuously
- Cleans and normalizes inbound email content
- Detects website and CRM form submissions
- Classifies emails into HVAC-specific categories
- Detects emergencies with hard safety overrides
- Extracts structured customer and job data
- Sends formatted Slack notifications
- Applies Gmail labels for auditability
- Forwards emails to dispatch or billing when needed
- Falls back safely to human review when uncertain

---

## 🧠 Categories Handled

Exactly one category is assigned per email:

1. Emergency
2. Service Request / Repair
3. New Lead / Estimate Request
4. Maintenance / Membership
5. Scheduling / Dispatch Updates
6. Billing / Invoice
7. Vendor / Partner
8. Hiring / HR
9. Spam / Marketing
10. Needs Review (fallback)

---

## 🧰 Tech Stack

| Function | Technology |
|--------|------------|
| Workflow Automation | n8n |
| Email Ingestion | Gmail API |
| Classification Logic | JavaScript (deterministic) |
| Data Extraction | OpenAI (LangChain Agent) |
| Notifications | Slack API |
| Logging / Dedupe | Gmail Labels |

---

## 🧩 High-Level Architecture

