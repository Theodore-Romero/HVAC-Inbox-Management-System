# Slack Message Schema — HVAC Inbox Intelligence Agent

This document defines the Slack message formats and channel routing used by the HVAC Inbox Intelligence Agent.

Messages are designed to be **consistent**, **scannable**, and **actionable** for dispatch, sales, and operations teams.

> **Important:** Billing and Spam/Marketing emails are handled via **email forwarding only** and do **not** generate Slack messages.

---

## ✅ General Message Standards

All Slack messages follow a consistent structure:

1. **Header** — emoji + message type
2. **Core fields** — Subject, From, Thread (when available)
3. **Summary / Details** — short, truncated email content

### Design Rules
- One Slack message per email
- Messages are optimized for fast scanning
- Emergency messages always send (no confidence gating)
- Ambiguous or low-confidence messages route to **Needs Review**
- Gmail remains the source of truth

---

## 🚨 Emergency → `#dispatch-emergency`

Emergency messages bypass all confidence checks and send immediately.

**Format**
🚨 EMERGENCY
Subject: <subject>
From: <from>

Details: <truncated email body>


**Notes**
- Always delivered to `#dispatch-emergency`
- Includes as much body context as possible (truncated if needed)

---

## 🆕 New Lead / Estimate → `#estimate-quote` or `#new-lead`

Used for new business inquiries and estimate requests.

**Format**
🆕 New Lead / Estimate (urgency)
Subject: <subject>
From: <from>

Summary: <short body snippet>


---

## 🔧 Service Request / Repair → `#service-request`

Used for standard service or repair requests.

**Format**
🔧 Service Request (urgency)
Subject: <subject>
From: <from>

Summary: <short body snippet>


## 📆 Scheduling / Dispatch Update → `#service-request`

Used for schedule changes, confirmations, or dispatch coordination.

**Format**
📆 Scheduling / Dispatch Update
Subject: <subject>
From: <from>
Thread: <thread_id>

Summary: <short body snippet>

---

## 🛠️ Maintenance / Membership → `#maintenance-request`

Used for maintenance plans and membership-related requests.

**Format**
🛠️ Maintenance / Membership
Subject: <subject>
From: <from>
Thread: <thread_id>

---

## 🤝 Vendor / Partner → `#vendor`

Used for vendor, supply house, or partner communications.

**Format**
🤝 Vendor / Partner
Subject: <subject>
From: <from>

Summary: <short body snippet>

---

## 👤 Hiring / HR → `#needs-review`

Used for hiring, resumes, and HR-related emails.

**Format**
👤 Hiring / HR
Subject: <subject>
From: <from>

Summary: <short body snippet>

---

## ❓ Needs Review (Fallback) → `#needs-review`

Used when classification confidence is low or signals conflict.

**Format**
❓ Needs Review (confidence: <confidence>)
Subject: <subject>
From: <from>

Summary: <short body snippet>


**Notes**
- Acts as the human-in-the-loop safety bucket
- Confidence value may be omitted

---

## 🚫 No-Slack Categories (Email Forward Only)

### 🧾 Billing / Invoice
- **Slack:** none  
- **Handling:** forwarded or routed via email

### 🧹 Spam / Marketing
- **Slack:** none  
- **Handling:** labeled and archived or forwarded

---

## 📌 Slack Channel Summary

| Category | Slack Channel |
|--------|---------------|
| Emergency | `#dispatch-emergency` |
| Service Request | `#service-request` |
| Scheduling Updates | `#service-request` |
| New Lead / Estimate | `#estimate-quote`, `#new-lead` |
| Maintenance / Membership | `#maintenance-request` |
| Vendor / Partner | `#vendor` |
| Hiring / HR | `#needs-review` |
| Needs Review | `#needs-review` |
| Billing | Email only |
| Spam / Marketing | Email only |
