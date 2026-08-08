<div align="center">

# 🤖 AI Customer Support Employee

### A real-world AI Customer Support Employee built with n8n

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
## 💼 The Business Problem

Customer support looks simple from the outside.

A customer sends an email. Someone reads it, checks the relevant information, writes a response, and moves on.

But at scale, that simple process turns into hours of repetitive operational work.

A typical ecommerce support team may repeatedly handle requests like:

> 📦 *"Where is my order?"*  
> ↩️ *"Can I get a refund?"*  
> ❌ *"Please cancel my order."*  
> 💔 *"My product arrived damaged."*  
> ❓ *"Is this product compatible with my device?"*  
> 😠 *"I've contacted support multiple times and still haven't received help."*

The challenge isn't just **writing a response**.

Before responding, a support agent may need to:

1. Read and understand the customer's message
2. Determine what type of request it is
3. Identify its urgency and sentiment
4. Extract relevant information such as an order number
5. Find the order in the business records
6. Verify that the order actually belongs to the customer
7. Decide whether the request can be handled automatically
8. Escalate refunds, cancellations, complaints, or risky cases
9. Write an appropriate response
10. Record what happened for future reference

Doing this manually for every email is slow, repetitive, and difficult to scale.

---

## 🏗️ Inside the n8n Workflow

The business logic described above is implemented as a single connected **n8n AI automation workflow**.

Rather than treating the LLM as the entire system, the workflow is divided into specialized stages. Each stage has one responsibility: receive the request, structure the data, add AI intelligence, verify business information, enforce safety rules, take the appropriate action, and record the result.

### 🔎 Real Workflow Overview

<div align="center">

<img
  src="docs/images/workflow-overview.png"
  alt="n8n AI Customer Support Employee workflow with Gmail, Google Gemini AI Agent, Google Sheets order verification, Slack escalation and automated customer support"
  width="100%"
/>

<br>

<sub>
<strong>Real n8n implementation:</strong> customer email → AI analysis → order verification → safety decision → automated reply or human escalation → support logging
</sub>

</div>

> [!NOTE]
> The workflow above is the actual implementation used in this project.  
> Credentials, account information, browser UI, webhook URLs, and other sensitive details should be removed or hidden from public screenshots.

---

## 🔄 End-to-End Execution Flow

Every support request moves through a controlled pipeline.

```text
┌──────────────────────────────────────────────────────────────┐
│  01 · INTAKE                                                 │
│                                                              │
│  📩 Gmail Trigger                                            │
│  A new customer support email enters the workflow.           │
└────────────────────────────┬─────────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────────┐
│  02 · DATA PREPARATION                                       │
│                                                              │
│  🧹 Normalize Email                                          │
│        ↓                                                     │
│  🔎 Extract Deterministic Fields                             │
│                                                              │
│  Raw email → clean, predictable support data                 │
└────────────────────────────┬─────────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────────┐
│  03 · AI INTELLIGENCE                                        │
│                                                              │
│  🧠 Google Gemini                                            │
│        ↓                                                     │
│  🧩 Parse AI Response                                        │
│                                                              │
│  Intent • Priority • Sentiment • Confidence                  │
│  Summary • Escalation Recommendation • Draft Reply           │
└────────────────────────────┬─────────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────────┐
│  04 · BUSINESS DATA VERIFICATION                             │
│                                                              │
│  📦 Read Orders Sheet                                        │
│        ↓                                                     │
│  🔐 Verify Order + Customer                                  │
│                                                              │
│  Order number + customer identity are checked against        │
│  actual business records before order data can be used.      │
└────────────────────────────┬─────────────────────────────────┘
                             │
                             ▼
┌──────────────────────────────────────────────────────────────┐
│  05 · SAFETY DECISION                                        │
│                                                              │
│  🛡️ Apply Safety Rules                                      │
│                                                              │
│  AI output + verification result + business rules            │
│  determine whether autonomous action is allowed.             │
└───────────────┬──────────────────────────────┬───────────────┘
                │                              │
          SAFE + VERIFIED              SENSITIVE / UNSAFE
                │                              │
                ▼                              ▼
┌───────────────────────────┐      ┌───────────────────────────┐
│  06A · AUTO RESOLUTION    │      │  06B · HUMAN HANDOFF     │
│                           │      │                           │
│  📧 Send Safe Gmail Reply │      │  💬 Slack Escalation     │
│                           │      │                           │
│  Customer receives an     │      │  Support team receives   │
│  approved response.       │      │  the case for review.    │
└──────────────┬────────────┘      └─────────────┬─────────────┘
               │                                 │
               └────────────────┬────────────────┘
                                │
                                ▼
┌──────────────────────────────────────────────────────────────┐
│  07 · AUDIT & OBSERVABILITY                                  │
│                                                              │
│  🧾 Prepare Support Log                                      │
│        ↓                                                     │
│  📊 Append Support Log                                       │
│                                                              │
│  The final decision and interaction are recorded.            │
└──────────────────────────────────────────────────────────────┘
```

This structure creates a clear separation between **AI reasoning**, **business verification**, **safety control**, and **execution**.

---

## 01 — 📩 Customer Email Intake

### `Gmail Trigger`

The workflow begins when a matching customer email reaches the connected Gmail inbox.

Gmail acts as the customer-facing communication layer, allowing the AI Employee to work with a channel businesses already use every day.

The trigger passes the incoming message into the automation with information such as:

```text
Message ID
Thread ID
Sender
Subject
Email Content
```

The original Gmail identifiers are preserved because they are needed later when the workflow sends a response back into the correct conversation.

<div align="center">

**Customer → Gmail → n8n**

</div>

---

## 02 — 🧹 Normalize Unstructured Email Data

### `Normalize Email`

Email payloads are not automatically shaped like clean application data.

The normalization layer converts the incoming Gmail payload into a consistent internal structure that downstream nodes can reliably use.

For example:

```json
{
  "message_id": "19fc...",
  "thread_id": "19fc...",
  "customer_email": "customer@example.com",
  "customer_name": "Sarah Johnson",
  "subject": "Order Status",
  "email_body": "Can you check my order ORD-1002?",
  "received_at": "2026-08-03T16:19:59.259Z",
  "source": "Gmail"
}
```

From this point forward, the rest of the automation doesn't need to understand Gmail's original payload structure.

It works with one predictable support object.

---

## 03 — 🔎 Extract Facts Before Asking AI

### `Extract Deterministic Fields`

Not every piece of information needs an LLM.

Before the message reaches Gemini, deterministic JavaScript logic extracts information that can be identified reliably from the customer's text.

Examples include:

```text
Order Number
Email Address
Phone Number
Tracking ID
Quantity
Amount
```

For example:

```text
"Can you check my order ORD-1002?"
                     │
                     ▼
          extracted_order_number
                     │
                     ▼
                 ORD-1002
```

This is an important architectural decision.

Instead of asking the AI model to reproduce an exact order identifier and risking an incorrect value, the workflow extracts deterministic identifiers directly from the original customer message.

> **Use AI for interpretation. Use code for exact data.**

---

## 04 — 🧠 Add the AI Intelligence Layer

### `Message a model — Google Gemini`

Once the deterministic information has been captured, the cleaned customer request is passed to **Google Gemini**.

The AI layer analyzes the support conversation and converts natural language into structured operational information.

The model evaluates:

```text
Category
Priority
Sentiment
Confidence
Escalation Recommendation
Support Summary
Draft Reply
```

A customer might write:

> *"Hi, can you please check the current status of my order ORD-1002?"*

The workflow needs more than a generated sentence.

It needs structured information that later nodes can reason about.

Conceptually, the AI layer transforms the message into:

```json
{
  "category": "order_status",
  "priority": "normal",
  "sentiment": "neutral",
  "confidence": 0.95,
  "escalate": false,
  "summary": "Customer is requesting the current status of an order.",
  "draft_reply": "..."
}
```

At this stage, however, the AI has **not been given authority to execute a business-critical action**.

It has analyzed the request.

The workflow still needs to validate its output.

---

## 05 — 🧩 Parse & Validate the AI Response

### `Parse AI Response`

LLM output is treated as external, non-deterministic input.

The parsing layer converts the Gemini response into the workflow's expected schema and provides controlled fallback behavior if the response cannot be safely interpreted.

This protects downstream nodes from depending directly on raw model output.

The resulting support object now contains both:

```text
DETERMINISTIC DATA
├── Customer Email
├── Customer Name
├── Order Number
├── Message ID
└── Thread ID

AI-GENERATED CONTEXT
├── Category
├── Priority
├── Sentiment
├── Confidence
├── Summary
├── Escalation Recommendation
└── Draft Reply
```

The two layers now meet — but business data still has to be verified.

---

## 06 — 📦 Look Up the Real Order

### `Read Orders Sheet`

For requests involving an order, the workflow checks the connected **Google Sheets order database**.

The sheet acts as the project's business data source and contains records such as:

```text
Order Number
Customer Name
Customer Email
Product
Quantity
Order Date
Status
Tracking Link
Estimated Delivery
Order Total
```

The workflow does not ask Gemini to invent or remember an order status.

It reads the business record.

<div align="center">

**AI understands what the customer wants.**  
**Google Sheets provides what the business actually knows.**

</div>

---

## 07 — 🔐 Verify Order Ownership

Finding an order number is not enough.

Before using order information in a response, the workflow verifies that the order belongs to the customer who sent the email.

Conceptually:

```text
Incoming Request
      │
      ├── Order Number → ORD-1002
      │
      └── Sender → customer@example.com
                         │
                         ▼
                  Orders Database
                         │
                ┌────────┴────────┐
                │                 │
              MATCH            NO MATCH
                │                 │
                ▼                 ▼
            VERIFIED          UNVERIFIED
```

This prevents a customer from receiving another customer's order information simply by supplying a valid order number.

Verified order data can then be attached to the support context, including available information such as:

```text
Verified Order Status
Tracking Link
Estimated Delivery
```

If verification fails, the automation does not invent an answer.

The case moves toward human review.

---

## 08 — 🛡️ Apply the Safety Rules

### `Apply Safety Rules`

This is the control layer of the AI Employee.

The workflow now has three important sources of information:

```text
1. Original customer data
2. AI Agent analysis
3. Verified business data
```

The safety layer evaluates them together before any customer-facing action is allowed.

Examples of conditions that can force escalation include:

```text
Refund Request
Cancellation Request
Damaged Item
Complaint
Low AI Confidence
Missing Required Order Number
Order Verification Failure
Sensitive Request
AI Recommended Escalation
```

This means:

```text
AI says "reply"
        +
Order is not verified
        =
DO NOT AUTO-REPLY WITH ORDER DATA
```

The deterministic safety layer has the final operational authority.

> [!IMPORTANT]
> **The LLM can recommend an action. The workflow decides whether that action is allowed.**

---

## 09 — 🔀 Route the Case

After safety evaluation, the request reaches one of two operational outcomes.

<table>
<tr>
<td width="50%" valign="top">

### ✅ Automated Resolution

Used when the request is safe, sufficiently understood, and any required business information has been verified.

The workflow can:

- Build the final response
- Use verified order information
- Preserve the original conversation
- Send the customer a Gmail reply
- Record the successful resolution

**Outcome**

```text
Status: Auto Replied
Escalated: FALSE
Reply Sent: TRUE
```

</td>
<td width="50%" valign="top">

### 🚨 Human Escalation

Used when the request requires judgment, approval, additional verification, or human intervention.

The workflow can:

- Stop autonomous resolution
- Preserve the AI-generated summary
- Preserve relevant customer context
- Notify the support team in Slack
- Record why the case was escalated

**Outcome**

```text
Status: Escalated
Escalated: TRUE
Reply Sent: FALSE
```

</td>
</tr>
</table>

---

## 10 — 📧 Send the Safe Customer Reply

### `Send Safe Gmail Reply`

When all required checks pass, the workflow sends the approved response through Gmail.

Because the original message and thread identifiers were preserved at intake, the response can remain connected to the customer's existing email conversation rather than creating an unrelated support message.

For verified order-status requests, the final response can use real business data such as:

```text
Order Number
Current Status
Estimated Delivery
Tracking Information
```

The AI helps communicate the answer.

The business system provides the facts.

---

## 11 — 💬 Escalate to the Human Support Team

When autonomous resolution is not appropriate, the workflow routes the case to **Slack**.

Instead of forwarding only the original customer email, the AI Employee can provide structured context for the human agent, including:

```text
Customer
Email
Category
Priority
Order Number
AI Confidence
Support Summary
Escalation Reason
Suggested Response
```

This changes escalation from:

> *"Here's an email. Please figure it out."*

into:

> *"Here's the customer, what they need, why automation stopped, and the context you need to take over."*

The AI Employee handles the triage work before the human enters the loop.

---

## 12 — 📊 Create the Support Audit Log

### `Prepare Support Log` → `Append Support Log`

Both workflow paths eventually produce a structured support record.

The log captures operational information such as:

| Field | Purpose |
|---|---|
| Ticket ID | Unique message/request reference |
| Received At | Request timestamp |
| Customer Name | Customer identity |
| Customer Email | Contact identity |
| Subject | Email subject |
| Message | Original customer request |
| Intent | AI-classified request type |
| Priority | Support priority |
| Order Number | Extracted order identifier |
| Order Status | Verified business status |
| AI Confidence | Model confidence |
| Action Taken | Automatic reply or human escalation |
| Escalated | Escalation state |
| Escalation Reason | Why automation stopped |
| Reply Sent | Whether an automatic response was sent |
| Slack Notification Sent | Whether the team was notified |
| Final Response | Final prepared customer response |
| Thread ID | Original Gmail conversation |
| Status | Final workflow state |
| Error Message | Processing error when applicable |

This gives the automation an audit trail instead of allowing AI interactions to disappear after execution.

---

## 🧪 Real Test Scenarios & Workflow Validation

A customer support automation is only useful if it behaves correctly when the input changes.

This AI Customer Support Employee was therefore designed around more than a single “happy path.”

The workflow needs to distinguish between:

- a request it can understand,
- an order it can find,
- a customer it can verify,
- an action it is allowed to automate,
- and a case that should immediately move to a human.

<div align="center">

### The goal isn't to make the AI answer everything.

### The goal is to make the **correct operational decision** for each request.

</div>

---

## 🎯 What Is Being Tested?

Each scenario evaluates the complete decision chain rather than testing Gemini in isolation.

```text
Customer Request
       │
       ▼
Can the request be understood?
       │
       ▼
Can exact data be extracted?
       │
       ▼
Is business data required?
       │
       ▼
Can the customer / order be verified?
       │
       ▼
Do the safety rules allow automation?
       │
       ▼
┌──────────────────┬──────────────────┐
│                  │                  │
▼                  ▼
AUTO RESOLUTION    HUMAN ESCALATION
│                  │
└─────────┬────────┘
          ▼
     AUDIT LOG
```

This makes the tests useful for validating the **AI layer, deterministic logic, business rules, routing, and final action together**.

---

# Test 01 — Verified Order Status Request

### Customer Request

```text
From:
Verified Customer <customer@example.com>

Subject:
Order Status

Message:
Hi, can you please check the current status
of my order ORD-1001?
```

### Expected Processing

```text
📩 Email received
      │
      ▼
🧹 Customer information normalized
      │
      ▼
🔎 ORD-1001 extracted
      │
      ▼
🧠 Intent → order_status
      │
      ▼
📦 ORD-1001 found in order records
      │
      ▼
🔐 Customer email matches order owner
      │
      ▼
🛡️ Safety checks pass
      │
      ▼
📧 Automatic response allowed
      │
      ▼
📊 Interaction logged
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Intent | `order_status` |
| Order Number | `ORD-1001` |
| Order Found | ✅ |
| Customer Verified | ✅ |
| Sensitive Action | ❌ |
| Human Escalation | ❌ |
| Automatic Reply | ✅ |
| Support Log | ✅ |

### Why this matters

This is the workflow's primary **safe automation path**.

The AI Employee isn't replying merely because it understands the question.

It replies because:

```text
Intent understood
        +
Order found
        +
Customer verified
        +
Safety rules passed
        =
AUTOMATIC RESOLUTION
```

---

# Test 02 — Valid Order, Wrong Customer

This scenario tests an important privacy boundary.

A customer asks about a real order, but the email address does not match the customer stored against that order.

### Customer Request

```text
From:
Sarah Johnson <sarah.johnson@example.com>

Subject:
Order Status

Message:
Hello, can you please check the current status
of my order ORD-1002?
```

The order database contains:

```text
Order Number:
ORD-1002

Customer:
Sarah Davis

Customer Email:
sarah.davis2@example.com

Product:
Smart Watch

Status:
Processing
```

The order itself is valid.

The sender is not the verified owner.

### Decision Flow

```text
ORD-1002 extracted
       │
       ▼
Order exists
       │
       ▼
Compare customer identity
       │
       ▼

sarah.johnson@example.com
          ≠
sarah.davis2@example.com

       │
       ▼
❌ VERIFICATION FAILED
       │
       ▼
🚫 DO NOT DISCLOSE ORDER DATA
       │
       ▼
💬 HUMAN ESCALATION
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Intent | `order_status` |
| Order Number | `ORD-1002` |
| Order Found | ✅ |
| Customer Verified | ❌ |
| Order Status Disclosed | ❌ |
| Automatic Reply With Order Data | ❌ |
| Human Escalation | ✅ |
| Support Log | ✅ |

### Why this matters

This test proves that:

> **Knowing a valid order number is not enough to access order information.**

Even if Gemini correctly understands the request with high confidence, failed customer verification overrides the AI's ability to proceed autonomously.

```text
HIGH AI CONFIDENCE
        +
FAILED VERIFICATION
        =
HUMAN ESCALATION
```

---

# Test 03 — Unknown Order Number

Now consider a customer supplying an order number that doesn't exist in the connected order records.

### Customer Request

```text
Subject:
Where is my order?

Message:
Can you check the status of ORD-9999?
```

### Expected Flow

```text
Intent → order_status
        │
        ▼
Extract → ORD-9999
        │
        ▼
Search business records
        │
        ▼
❌ No matching order
        │
        ▼
Cannot verify request
        │
        ▼
🚨 Safe fallback / Human review
```

The system should never allow Gemini to compensate for missing business data by inventing an order status.

### Expected Decision

| Check | Expected Result |
|---|---|
| Intent Understood | ✅ |
| Order Number Extracted | `ORD-9999` |
| Order Found | ❌ |
| Order Verified | ❌ |
| Fabricated Order Information | ❌ |
| Autonomous Disclosure | ❌ |
| Safe Handling / Escalation | ✅ |
| Support Log | ✅ |

### Key rule

```text
NO BUSINESS RECORD
        ≠
ASK AI TO GUESS

NO BUSINESS RECORD
        =
DO NOT CLAIM AN ORDER STATUS
```

---

# Test 04 — Refund Request

Some requests may be easy for AI to understand but still inappropriate for autonomous execution.

### Customer Request

```text
Subject:
Refund Request

Message:
Hi, I received my order but I'm not happy with it.
I would like a refund for ORD-1005.
```

Gemini may confidently classify the request as:

```json
{
  "category": "refund_request",
  "priority": "normal",
  "sentiment": "negative",
  "confidence": 0.98
}
```

But confidence is not permission.

### Expected Flow

```text
Customer requests refund
        │
        ▼
🧠 AI correctly understands request
        │
        ▼
Category → refund_request
        │
        ▼
🛡️ Sensitive-action rule triggered
        │
        ▼
🚫 No autonomous refund approval
        │
        ▼
💬 Human support notified
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Request Understood | ✅ |
| Category | `refund_request` |
| AI Can Draft Response | ✅ |
| AI Can Approve Refund | ❌ |
| Human Escalation | ✅ |
| Escalation Context Prepared | ✅ |
| Support Log | ✅ |

### Why this matters

This demonstrates the difference between:

```text
UNDERSTANDING AN ACTION
```

and

```text
BEING AUTHORIZED TO PERFORM THAT ACTION
```

The AI Employee can understand and prepare the case without being allowed to make the financial decision.

---

# Test 05 — Cancellation Request

### Customer Request

```text
Subject:
Cancel My Order

Message:
Please cancel order ORD-1006.
I placed it by mistake.
```

### Expected Processing

```text
Intent → cancellation
        │
        ▼
Order number → ORD-1006
        │
        ▼
AI understands requested action
        │
        ▼
🛡️ Cancellation safety rule
        │
        ▼
🚫 No autonomous cancellation
        │
        ▼
💬 Human escalation
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Intent | `cancellation` |
| Order Extracted | ✅ |
| Request Understood | ✅ |
| Order Automatically Cancelled | ❌ |
| Human Review | ✅ |
| Suggested Response Available | ✅ |
| Interaction Logged | ✅ |

The workflow does not confuse **intent detection** with **permission to modify business records**.

---

# Test 06 — Damaged Product

### Customer Request

```text
Subject:
Product Arrived Damaged

Message:
My order arrived today but the product is broken.
Can you send me a replacement?
```

A damaged-item case may involve:

```text
Replacement approval
Refund policy
Evidence / photos
Shipping decisions
Inventory
Customer history
```

These decisions go beyond simple email generation.

### Expected Flow

```text
🧠 Detect damaged_item
        │
        ▼
Determine priority / sentiment
        │
        ▼
Prepare support summary
        │
        ▼
🛡️ Sensitive case detected
        │
        ▼
💬 Human escalation
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Category | `damaged_item` |
| AI Triage | ✅ |
| Automatic Replacement Approval | ❌ |
| Automatic Refund Approval | ❌ |
| Human Escalation | ✅ |
| Support Context Prepared | ✅ |
| Interaction Logged | ✅ |

---

# Test 07 — Customer Complaint

### Customer Request

```text
Subject:
Very Disappointed With Support

Message:
I've contacted your team several times and nobody
has solved my issue. This is extremely frustrating.
```

The AI layer can help detect:

```text
Intent:
complaint

Sentiment:
negative

Priority:
potentially elevated
```

But complaints often involve context and judgment that shouldn't be reduced to a generic automatic response.

### Expected Flow

```text
Complaint detected
       │
       ▼
Sentiment evaluated
       │
       ▼
Priority assigned
       │
       ▼
Summary prepared
       │
       ▼
🚨 Human attention required
       │
       ▼
💬 Slack escalation
```

### Why this matters

Automation is most useful when it can recognize that **not automating the final conversation is the better decision**.

---

# Test 08 — Low AI Confidence

The workflow must also handle cases where the customer's request is ambiguous.

### Customer Request

```text
Subject:
Need Help

Message:
Hi, the thing from before still isn't right.
Can someone sort this out?
```

The message contains little actionable context.

An AI model might still generate a plausible interpretation.

The safer behavior is to recognize uncertainty.

### Expected Flow

```text
Ambiguous request
       │
       ▼
🧠 AI analysis
       │
       ▼
📉 Confidence below threshold
       │
       ▼
🛡️ Safety rule triggered
       │
       ▼
🚫 Do not guess
       │
       ▼
👤 Human review
```

### Expected Decision

| Check | Expected Result |
|---|---|
| Message Received | ✅ |
| AI Analysis Attempted | ✅ |
| Confidence Sufficient | ❌ |
| AI Guess Treated as Fact | ❌ |
| Human Escalation | ✅ |
| Interaction Logged | ✅ |

---

# Test 09 — Missing Order Number

A customer may clearly ask about an order without providing the identifier required to verify it.

### Customer Request

```text
Subject:
Order Update

Message:
Hi, can you tell me where my order is?
```

The AI may correctly identify:

```text
category = order_status
```

but deterministic extraction returns:

```text
order_number = ""
```

### Expected Flow

```text
Intent → order_status
        │
        ▼
Order number required
        │
        ▼
🔎 No order number extracted
        │
        ▼
Cannot perform deterministic lookup
        │
        ▼
🛡️ Safe handling required
```

### Why this matters

Correct intent classification does not magically create missing business information.

```text
AI KNOWS THE CUSTOMER'S INTENT
             │
             ▼
BUT
             │
             ▼
THE WORKFLOW STILL LACKS
THE DATA REQUIRED TO ACT
```

The system therefore avoids pretending that the order has been verified.

---

# Test 10 — Product Question

Not every customer request requires order verification.

### Customer Request

```text
Subject:
Product Compatibility

Message:
Are the wireless headphones compatible
with Android phones?
```

The AI Agent can classify the request as:

```text
product_question
```

Unlike a refund or cancellation, a product question is not automatically a privileged business action.

However, the final behavior still depends on whether the workflow has reliable information available to answer the question.

### Decision Principle

```text
Product Question
       │
       ▼
AI understands request
       │
       ▼
Is reliable answer context available?
       │
   ┌───┴───┐
   │       │
  YES      NO
   │       │
   ▼       ▼
Safe     Human /
Reply    Safe Fallback
```

The important rule remains:

> **The AI Employee should not convert missing product knowledge into invented facts.**

---

# 🧪 Validation Matrix

The scenarios above can be summarized as a decision matrix.

| Scenario | AI Understands | Verification Required | Auto Reply | Human Escalation |
|---|:---:|:---:|:---:|:---:|
| Verified Order Status | ✅ | ✅ | ✅ | ❌ |
| Order / Customer Mismatch | ✅ | ✅ | ❌ | ✅ |
| Unknown Order | ✅ | ✅ | ❌ | ✅ |
| Refund Request | ✅ | Contextual | ❌ | ✅ |
| Cancellation Request | ✅ | Contextual | ❌ | ✅ |
| Damaged Product | ✅ | Contextual | ❌ | ✅ |
| Complaint | ✅ | ❌ | ❌ | ✅ |
| Low AI Confidence | ⚠️ | Contextual | ❌ | ✅ |
| Missing Order Number | ✅ | ✅ | ❌ | Safe fallback / review |
| Product Question | ✅ | Depends on knowledge | Conditional | Conditional |

> [!NOTE]
> The exact automated outcome depends on the safety rules configured in the workflow. The matrix documents the intended operating model rather than giving the language model unrestricted authority.

---

## 🛠️ Technology Stack

| Technology | Responsibility |
|---|---|
| **n8n** | Workflow orchestration, routing, and execution |
| **Google Gemini** | Language understanding, classification, summaries, confidence, and draft responses |
| **JavaScript** | Normalization, exact extraction, parsing, verification, and deterministic safety rules |
| **Gmail** | Customer email intake and approved replies |
| **Google Sheets** | Order records and support audit logging |
| **Slack** | Human escalation and internal handoff |

The design separates responsibilities: **AI handles language ambiguity, code handles exact rules, business records provide facts, and humans retain control over sensitive decisions.**

---

## 🚀 Setup & Quick Start

Want to run this AI Customer Support Employee in your own n8n environment?

### 1. Import the Workflow

Download the workflow JSON from this repository and import it into **n8n**.

```text
n8n → Workflows → Import from File
```

---

### 2. Connect Required Services

Configure your own credentials inside n8n:

| Integration | Purpose |
|---|---|
| 📧 **Gmail** | Receive customer emails & send approved replies |
| 🧠 **Google Gemini** | Understand, classify & draft responses |
| 📊 **Google Sheets** | Order verification & support logging |
| 💬 **Slack** | Human escalation notifications |

> [!IMPORTANT]
> Credentials, API keys, private Sheet IDs, and account information are **not included** in this repository.

---

### 3. Create the Orders Sheet

The workflow expects an order data source with fields similar to:

```text
Order Number | Customer Name | Customer Email | Product | Quantity | Order Date | Status | Tracking | Estimated Delivery | Total
```

Example:

```text
ORD-1001 | John Smith | john@example.com | Wireless Headphones | 1 | 2026-07-01 | Shipped | TRK-1001 | 2026-07-05 | $149.99
```

The workflow uses the order number and customer information to verify requests before exposing order-specific data.

---

### 4. Create the Support Log

Create another Google Sheet with these columns:

```text
Ticket ID | Received At | Customer Name | Customer Email | Subject | Message | Intent | Priority | Order Number | Order Status | AI Confidence | Action Taken | Escalated | Escalation Reason | Reply Sent | Slack Notification Sent | Final Response | Thread ID | Status | Error Message
```

Every processed request can then be recorded as a structured support event.

---

### 5. Configure the Workflow

After importing, review these core stages:

```text
📩 Gmail Trigger
      ↓
🧹 Normalize Email
      ↓
🔎 Extract Order Data
      ↓
🧠 Gemini AI Analysis
      ↓
🧩 Parse AI Response
      ↓
📦 Order Lookup
      ↓
🔐 Customer Verification
      ↓
🛡️ Safety Rules
      ↓
┌──────────────┴──────────────┐
│                             │
▼                             ▼
📧 Automatic Reply       💬 Human Escalation
│                             │
└──────────────┬──────────────┘
               ▼
         📊 Support Log
```

Make sure each node points to **your own credentials, Google Sheets, Gmail account, and Slack channel**.

---

### 6. Test Before Activation

Start with test emails such as:

```text
[AI SUPPORT TEST] Order Status

Hi,

Can you check the status of my order ORD-1001?
```

Test both major paths:

```text
✅ Verified + Safe Request
        ↓
Automatic Response

❌ Unverified / Sensitive / Uncertain Request
        ↓
Human Escalation
```

Confirm that the correct order is retrieved, customer verification works, unsafe actions are blocked, Slack receives escalations, and the final result is written to the support log.

---

### 🔒 Security

Before using the workflow with real customers:

- Never commit API keys, OAuth tokens, or credentials to GitHub.
- Remove real customer data from exported workflows and examples.
- Review your organization's refund, cancellation, privacy, and escalation policies.
- Test all automation and human-escalation paths before activation.
- Replace Google Sheets with your CRM, ecommerce platform, ERP, or database when required.

> [!CAUTION]
> This repository provides the automation architecture. Production permissions, policies, credentials, and business rules must be configured for the organization deploying it.

---

<div align="center">

### 📥 Import → 🔗 Connect → ⚙️ Configure → 🧪 Test → 🚀 Activate

**Your AI Customer Support Employee is ready to become part of the support workflow.**

</div>

---

## 📁 Repository Structure & Project Files

This repository is organized to make the AI Customer Support Employee easy to understand, import, test, and extend.

```text
n8n-ai-employee-customer-support/
│
├── 📄 README.md
│
├── 🤖 workflow/
│   └── ai-customer-support-employee.json
│
├── 📊 sample-data/
│   ├── orders-sample.csv
│   └── support-log-template.csv
│
├── 📚 docs/
│   ├── images/
│   │   └── workflow-overview.png
│   └── setup-notes.md
│
├── 🔒 .gitignore
└── 📜 LICENSE
```

> [!NOTE]
> The exact repository structure can be simplified depending on which supporting files you decide to publish.

---

### 🤖 `workflow/`

Contains the exported **n8n workflow JSON**.

```text
workflow/
└── ai-customer-support-employee.json
```

This is the core project file that can be imported directly into n8n and configured with your own credentials and integrations.

---

### 📊 `sample-data/`

Contains safe example data for testing the workflow without exposing real customer information.

```text
sample-data/
├── orders-sample.csv
└── support-log-template.csv
```

**`orders-sample.csv`**

Provides example order records for testing:

```text
Order lookup
Customer verification
Order status requests
Verification failures
```

**`support-log-template.csv`**

Provides the expected structure for the workflow's support audit log.

---

### 📚 `docs/`

Optional supporting documentation for configuration or future extensions.

```text
docs/
├── images/
│   └── workflow-overview.png
└── setup-notes.md
```

The main project explanation stays inside the `README.md`, keeping the repository easy to explore.

---

### 📄 `README.md`

The main documentation for the project, covering:

```text
✓ Business problem
✓ AI Employee architecture
✓ Workflow logic
✓ Safety guardrails
✓ Features
✓ Test scenarios
✓ Technology stack
✓ Setup instructions
✓ Project structure
```

---

## 🔐 What Is NOT Included

For security and privacy, the public repository should never contain:

```text
❌ API Keys
❌ OAuth Tokens
❌ Gmail Credentials
❌ Gemini Credentials
❌ Slack Credentials
❌ Private Webhook URLs
❌ Real Customer Information
❌ Production Order Data
❌ Private Spreadsheet IDs
```

Credentials should always be configured securely inside **n8n Credentials** after importing the workflow.

---

## 🧩 Built to Be Extended

The current implementation uses:

```text
Gmail + Gemini + Google Sheets + Slack
```

but the architecture can be extended to real business systems.

```text
Google Sheets  →  Shopify / WooCommerce / CRM / ERP / SQL

Gmail          →  Help Desk / Shared Support Inbox

Slack          →  Microsoft Teams / Ticketing System

Gemini         →  Other LLM Providers
```

This makes the repository more than a fixed automation.

It provides a reusable foundation for building larger **n8n AI Agents, AI Employees, and customer support automation systems**.

---

<div align="center">

### Clean Architecture • Modular Integrations • Secure Configuration • Easy to Extend

**Built as a reusable foundation for real-world AI automation.**

</div>

---
## 👨‍💻 About the Developer

Hi, I'm **Ikram** — an Automation Specialist focused on building practical systems that combine **AI, workflow automation, APIs, and business processes**.

My work focuses on moving beyond simple AI demos and building automations that can perform meaningful work inside real business operations.

I work with technologies including:

<div align="center">

![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![AI Agents](https://img.shields.io/badge/AI-Agents-6C63FF?style=flat-square)
![Python](https://img.shields.io/badge/Python-Automation-3776AB?style=flat-square&logo=python&logoColor=white)
![GoHighLevel](https://img.shields.io/badge/GoHighLevel-CRM_Automation-00AEEF?style=flat-square)
![APIs](https://img.shields.io/badge/APIs-Integrations-009688?style=flat-square)
![Gemini](https://img.shields.io/badge/Google_Gemini-AI-4285F4?style=flat-square&logo=google&logoColor=white)

</div>

```text
AI Agents
     +
n8n Automation
     +
Business Logic
     +
APIs & Integrations
     +
Human Oversight
     =
Real-World AI Automation
```

---

## 🌱 Where This Architecture Can Go Next

The same AI Employee architecture can be expanded into systems for:

```text
📞 AI Receptionists

🎯 Lead Qualification Agents

📅 Appointment Management

💼 Sales Operations

📧 Intelligent Email Management

🛒 Ecommerce Operations

📊 CRM Automation

🧾 Administrative Workflows

🔍 Research & Data Processing

🤝 Customer Success

⚙️ Internal Business Operations
```

Each system can follow the same core philosophy:

<div align="center">

### AI for understanding.  
### Code for precision.  
### Business systems for truth.  
### Guardrails for control.  
### Humans for judgment.

</div>

---

## 🤝 Let's Build Something Useful

If you're a **business owner, agency, automation professional, or developer** interested in:

- AI Agents & AI Employees
- n8n workflow automation
- Customer support automation
- CRM & business process automation
- API integrations
- AI-powered operational systems

I'm always interested in connecting, collaborating, and building practical automation solutions.

---

## ⭐ Found This Project Useful?

If this repository helped you understand how **n8n, AI Agents, and business automation** can work together:

### ⭐ Star the repository

It helps support the project and makes it easier for other developers and businesses exploring real-world AI automation to discover it.

You can also **fork the repository**, experiment with the workflow, and adapt the architecture to your own use case.

---

<div align="center">

## 🤖 n8n AI Customer Support Employee

**Built to understand. Designed to verify. Controlled by guardrails. Ready to escalate.**

<br>

### AI should not just generate responses.

### It should help businesses get work done.

<br>

**Built by Ikram**

*n8n • AI Agents • AI Employees • Workflow Automation • Business Process Automation*

<br>

⭐ **If you like the project, consider giving the repository a star.**

</div>

---

## 📬 Connect

**GitHub:** `https://github.com/YOUR-USERNAME`  
**LinkedIn:** `YOUR-LINKEDIN-URL`  
**Email:** `YOUR-PROFESSIONAL-EMAIL`

---

### 📄 License

This project is available under the **MIT License**.

You are welcome to learn from, modify, and build upon the project in accordance with the license terms.

---

<div align="center">

### 🚀 More AI Employees coming soon.

**Follow the repository and connect with me to see what I'm building next.**

</div>
