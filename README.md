# HVAC Inbox Intelligence Agent

An automated inbox intelligence system that classifies, extracts, and routes HVAC emails in real time—ensuring leads, service requests, and emergencies are never missed.

![N8N](https://img.shields.io/badge/N8N-EA4B71?style=flat&logo=n8n&logoColor=white)
![Gmail](https://img.shields.io/badge/Gmail-EA4335?style=flat&logo=gmail&logoColor=white)
![Slack](https://img.shields.io/badge/Slack-4A154B?style=flat&logo=slack&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white)

---

## 🖼️ Workflow Preview

![n8n Workflow Overview](<img width="899" height="713" alt="hvac-n8n-workflow" src="https://github.com/user-attachments/assets/90c45b8c-b296-4154-85f6-f257033d66a1" />
)

---

## 📊 Overview

This project answers the question:  
**How do HVAC companies reliably handle leads, service requests, and emergencies without inbox overload?**

The system automatically:
- Monitors a shared HVAC inbox in real time
- Cleans and normalizes inbound email content
- Detects website and CRM form submissions
- Classifies emails into HVAC-specific operational categories
- Extracts structured customer and job details
- Sends actionable Slack alerts to the correct team
- Applies Gmail labels for auditability and deduplication
- Falls back to human review when confidence is low

---

## 🔍 Key Capabilities

- Emergency detection (gas smell, CO, smoke, electrical risk)
- Website and CRM form recognition
- Lead and service request extraction
- Smart inbox routing (billing, scheduling, maintenance, HR, vendors)
- Consistent Gmail labeling
- Human-in-the-loop safety fallback

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Workflow Automation | N8N |
| Email Ingestion | Gmail API |
| Classification | JavaScript (rule-based HVAC classifier) |
| Data Extraction | OpenAI (LangChain agent) |
| Notifications | Slack API |
| Logging / Dedupe | Gmail Labels |
| Version Control | Git/GitHub |

---

## 📐 Architecture

┌──────────────┐
│ Gmail Inbox │
└──────┬───────┘
▼
┌─────────────────────┐
│ Email Normalization │
└──────┬──────────────┘
▼
┌─────────────────────┐
│ Form Signal Detector│
└──────┬──────────────┘
│ Yes
▼
┌─────────────────────┐
│ AI Data Extraction │
└──────┬──────────────┘
▼
┌─────────────────────┐
│ Slack Notifications │
└──────┬──────────────┘
│
└──▶ Gmail Labels + Forwarding

yaml
Copy code
   No
   ▼
┌─────────────────────┐
│ HVAC Classifier │
└──────┬──────────────┘
▼
┌─────────────────────┐
│ Routing Switch │
└──────┬──────────────┘
▼
Slack Alerts + Gmail Labels

yaml
Copy code

---

## 📁 Repository Structure

hvac-inbox-agent/
├── README.md
├── n8n-workflows/
│ └── hvac-inbox-agent.json
├── docs/
│ ├── setup-guide.md
│ └── slack-message-schema.md

yaml
Copy code

---

## 📂 HVAC Email Categories

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

---

## ⚙️ Setup Instructions

### Prerequisites
- Gmail account connected to HVAC inbox
- Slack workspace
- N8N account (cloud or self-hosted)
- OpenAI API key

### Step 1: Gmail Setup
1. Create required HVAC labels
2. Ensure inbox receives all inbound messages
3. Enable Gmail API access

### Step 2: N8N Workflow
1. Import `hvac-inbox-agent.json`
2. Configure Gmail, Slack, and OpenAI credentials
3. Update Slack channel mappings
4. Activate workflow

### Step 3: Testing
1. Send test emails (lead, service, emergency, spam)
2. Verify Slack routing
3. Confirm Gmail labels are applied

---

## 🧠 Skills Demonstrated

- **AI Operations Automation**: LLM-assisted extraction and classification
- **Workflow Engineering**: Fault-tolerant automation in N8N
- **Email Intelligence**: Parsing, normalization, deduplication
- **Prompt Engineering**: Structured JSON extraction
- **System Design**: Human-in-the-loop safety and escalation

---

## 📬 Contact

**Theodore Romero**
- LinkedIn: [linkedin.com/in/theodoreromero](https://linkedin.com/in/theodoreromero)
- Email: theodore.romero@email.com

---

## 📄 License

This project is open source and available under the MIT License.
