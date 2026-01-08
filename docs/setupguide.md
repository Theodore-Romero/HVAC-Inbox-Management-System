# HVAC Inbox Intelligence Agent — Setup Guide

This guide explains how to deploy the HVAC Inbox Intelligence Agent using **n8n**, **Gmail**, **Slack**, and **OpenAI**.

---

## Prerequisites

- Gmail account connected to the HVAC inbox
- Slack workspace
- n8n (cloud or self-hosted)
- OpenAI API key

---

## Step 1: Gmail Setup

Create the following Gmail labels:

HVAC/Processed
HVAC/Emergency
HVAC/Lead
HVAC/Service
HVAC/Scheduling
HVAC/Billing
HVAC/Maintenance
HVAC/Vendor
HVAC/HR
HVAC/Spam
HVAC/Review

yaml
Copy code

Ensure the inbox receives all inbound emails and does not auto-archive messages.

---

## Step 2: Slack Setup

Create or map the following Slack channels:

- `#dispatch-emergency`
- `#service-request`
- `#estimate-quote`
- `#new-lead`
- `#maintenance-request`
- `#vendor`
- `#needs-review`

Channel names can be customized inside the workflow.

---

## Step 3: n8n Workflow Import

1. Open n8n
2. Import `hvac-inbox-intelligence-agent.json`
3. Configure credentials:
   - Gmail
   - Slack
   - OpenAI
4. Review routing logic
5. Activate the workflow

---

## Step 4: Testing

Send test emails for:
- Lead / estimate request
- Service request
- Emergency
- Scheduling update
- Spam email

Verify Slack routing and Gmail labels.

---

## Notes

- Credentials are managed inside n8n and are not stored in the workflow JSON
- Emergency messages always bypass confidence checks
