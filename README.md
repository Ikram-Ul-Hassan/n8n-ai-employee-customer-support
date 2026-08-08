<div align="center">

# 🤖 AI Customer Support Employee

### A production-ready Customer Support AI Agent built with n8n

**Reads customer emails · Understands intent · Verifies orders · Responds safely · Escalates to humans · Logs every interaction**

<br>

<img src="https://img.shields.io/badge/n8n-AI_Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white" alt="n8n AI Automation"/>
<img src="https://img.shields.io/badge/AI_Employee-Customer_Support-6C63FF?style=for-the-badge" alt="AI Employee"/>
<img src="https://img.shields.io/badge/AI_Agent-Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Google Gemini AI Agent"/>
<img src="https://img.shields.io/badge/Human--in--the--Loop-Safety-22A06B?style=for-the-badge" alt="Human in the Loop"/>

<br><br>

<img src="https://img.shields.io/badge/Gmail-Email_Trigger-EA4335?logo=gmail&logoColor=white" alt="Gmail"/>
<img src="https://img.shields.io/badge/Google_Sheets-Order_Verification-34A853?logo=googlesheets&logoColor=white" alt="Google Sheets"/>
<img src="https://img.shields.io/badge/Slack-Human_Escalation-4A154B?logo=slack&logoColor=white" alt="Slack"/>
<img src="https://img.shields.io/badge/JavaScript-Business_Logic-F7DF1E?logo=javascript&logoColor=black" alt="JavaScript"/>

<br><br>

> **Not another chatbot.**  
> This is an end-to-end AI customer support workflow designed to operate like a real support team member while keeping business-critical decisions under deterministic control.

</div>

---

## 👋 Meet the AI Customer Support Employee

This project turns a customer support inbox into an intelligent, automated support operation using **n8n, AI Agents, Google Gemini, Gmail, Google Sheets, Slack, and JavaScript business logic**.

When a customer sends an email, the system doesn't simply forward the message to an LLM and send whatever comes back.

It runs the request through a complete support process:

<table>
<tr>
<td width="50%" valign="top">

### 🧠 It understands

- Who contacted the business
- What the customer is asking
- The intent behind the message
- Request priority and sentiment
- Whether an order number is present
- Whether AI confidence is sufficient

</td>
<td width="50%" valign="top">

### 🛡️ It acts safely

- Verifies orders against business data
- Validates the customer before sharing order details
- Applies deterministic safety rules
- Automatically replies only when safe
- Escalates sensitive cases to Slack
- Records the final outcome for auditing

</td>
</tr>
</table>

---

### From customer email to business action

```text
📩 CUSTOMER EMAIL
        │
        ▼
🧹 NORMALIZE + EXTRACT DATA
        │
        ▼
🧠 GEMINI AI AGENT
Understand intent • Priority • Sentiment • Draft response
        │
        ▼
📦 ORDER VERIFICATION
Check real order data + customer ownership
        │
        ▼
🛡️ SAFETY & BUSINESS RULES
Decide what the AI Employee is allowed to do
        │
        ├──────────────────────────────┐
        ▼                              ▼
✅ SAFE REQUEST                  🚨 SENSITIVE / UNSAFE
        │                              │
        ▼                              ▼
📧 Automatic Gmail Reply         💬 Human Escalation in Slack
        │                              │
        └──────────────┬───────────────┘
                       ▼
                📊 SUPPORT AUDIT LOG
```

<div align="center">

### One workflow. Two outcomes. Human control where it matters.

**Safe & verified → AI handles it automatically**  
**Sensitive, uncertain or unverified → Human takes over**

</div>

---

## 🎯 What makes this different?

A basic AI email automation can **generate a reply**.

This system is designed to decide whether that reply should be sent at all.

The **AI Agent provides intelligence** — understanding the request, classifying intent, evaluating sentiment, assigning priority, summarizing the issue, and drafting a response.

The **n8n workflow provides control** — extracting deterministic data, checking real order records, verifying customer ownership, enforcing safety rules, routing cases, sending approved responses, escalating risky requests, and maintaining an audit log.

> ### 🧠 AI understands the customer.
> ### ⚙️ n8n orchestrates the operation.
> ### 🛡️ Deterministic rules protect the business.
> ### 👤 Humans stay in control of sensitive decisions.

---

<div align="center">

### Built as a real-world AI Automation project — not a prompt engineering demo.

This repository demonstrates how **n8n + AI Agents** can be used to build an **AI Employee** that performs meaningful operational work inside an actual business process.

</div>

---
