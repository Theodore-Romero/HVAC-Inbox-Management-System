# Slack Message Schema — HVAC Inbox Intelligence Agent

This document defines the Slack message formats and routing used by the **HVAC Inbox Intelligence Agent**.

Slack messages are designed to be **consistent**, **scannable**, and **actionable** for dispatch, sales, and operations teams.

> **Note:** Billing and Spam/Marketing emails are handled via **email forwarding only** and do not generate Slack messages.

---

## ✅ General Message Standards

All Slack messages follow a consistent structure:

1. **Header** — emoji + message type
2. **Core fields** — Subject, From, Thread (when available)
3. **Summary / Details** — short, truncated email content

### Design Rules
- One Slack message per email
- Messages are optimized for fast scanning (mobile-friendly)
- Emergency messages always send (no confidence gating)
- Ambiguous or low-confidence emails route to **Needs Review**
- Gmail remains the system of record

---

## 🚨 Emergency → `#dispatch-emergency`

Emergency messages bypass all confidence checks and send immediately.

**Format**
🚨 EMERGENCY

Subject: "subject line"

From: "sender"

Details: "summarized body message"


**Notes**
- Always delivered to `#dispatch-emergency`
- Includes as much message context as possible (truncated if needed)

---

## 🆕 New Lead / Estimate → `#estimate-quote` or `#new-lead`

Used for new business inquiries and estimate requests.

**Format**
🆕 New Lead / Estimate 

Subject: "subject line"

From: "sender"

Details: "summarized body message"


---

## 🔧 Service Request / Repair → `#service-request`

Used for standard HVAC service or repair requests.

**Format**
🔧 Service Request 

Subject: "subject line"

From: "sender"

Details: "summarized body message"

---

## 📆 Scheduling / Dispatch Update → `#service-request`

Used for schedule changes, confirmations, or dispatch coordination.

**Format**
📆 Scheduling / Dispatch Update

Subject: "subject line"

From: "sender"

Details: "summarized body message"

---

## 🛠️ Maintenance / Membership → `#maintenance-request`

Used for maintenance plans and membership-related requests.

**Format**
🛠️ Maintenance / Membership

Subject: "subject line"

From: "sender"

Details: "summarized body message"

---

## 🤝 Vendor / Partner → `#vendor`

Used for vendor, supply house, or partner communications.

**Format**
🤝 Vendor / Partner

Subject: "subject line"

From: "sender"

Details: "summarized body message"

---

## 👤 Hiring / HR → `#needs-review`

Used for resumes, job inquiries, and HR-related emails.

**Format**
👤 Hiring / HR

Subject: "subject line"

From: "sender"

Details: "summarized body message"


---

## ❓ Needs Review (Fallback) → `#needs-review`

Used when classification confidence is low or signals conflict.

**Format**
❓ Needs Review (confidence: <confidence>)

Subject: "subject line"

From: "sender"

Details: "summarized body message"


**Notes**
- Acts as the human-in-the-loop safety bucket
- Confidence value may be omitted

---

## 🚫 No-Slack Categories (Email Forward Only)

### 🧾 Billing / Invoice
- **Slack:** none  
- **Handling:** forwarded or routed via email rules

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
