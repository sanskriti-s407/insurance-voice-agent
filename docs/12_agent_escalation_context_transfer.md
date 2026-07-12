# Human Escalation with Context Transfer

## Objective

This document defines when the Insurance Conversational AI Voice Agent transfers a customer to a live support agent and specifies the customer and conversation context that must accompany the transfer. The objective is to ensure a seamless transition without requiring customers to repeat previously shared information.

---

# 1. Purpose

Although the Insurance Voice Agent is designed to resolve most customer requests through automated workflows, certain situations require human intervention. When escalation is necessary, the agent should:

- Create a support case.
- Generate a unique case ID.
- Transfer the complete conversation context.
- Preserve the authenticated session and customer details.
- Connect the customer to a live support representative.

---

# 2. Escalation Triggers

| Trigger ID | Scenario | Escalation |
|------------|----------|------------|
| ESC-001 | Authentication fails after 3 attempts | Required |
| ESC-002 | Customer explicitly requests a human agent | Required |
| ESC-003 | Backend API timeout after retry limit | Required |
| ESC-004 | Backend service returns repeated errors | Required |
| ESC-005 | Repeated No-Match events | Required |
| ESC-006 | Repeated No-Input events | Required |
| ESC-007 | Unsupported or unresolved customer request | Required |
| ESC-008 | Update request requires manual review | Required |
| ESC-009 | Unexpected system failure | Required |

---

# 3. Context Information Transferred

Before transferring the conversation, the following information should be packaged and shared with the live support agent.

| Context | Description |
|----------|-------------|
| Case ID | Generated support case |
| Customer ID | Authenticated customer identifier |
| Customer Name | Customer name |
| Registered Mobile Number | Verified mobile number |
| Selected Policy | Policy currently being managed |
| Policy Type | Motor, Health, or Life Insurance |
| Claim ID | Selected claim (if applicable) |
| Request ID | Update Request ID (if applicable) |
| Current Business Agent | Policy Services, Claims, Update Requests, or Customer Onboarding |
| Current Intent | Active customer request |
| Last API Invoked | Most recent backend API |
| API Status | Success, Timeout, or Error |
| Escalation Reason | Reason for transfer |
| Conversation Summary | Summary of customer interaction |
| Timestamp | Date and time of escalation |

---

# 4. Escalation Workflow

```text
Customer Request
        │
        ▼
Issue Cannot Be Resolved
        │
        ▼
Inform Customer About Transfer
        │
        ▼
Generate Conversation Summary
        │
        ▼
Create Support Case
(createCase())
        │
        ▼
Generate Case ID
        │
        ▼
Transfer Customer Context
        │
        ▼
Transfer to Live Agent
(escalateToAgent())
        │
        ▼
Customer Connected
```

---

# 5. Bot Responses

## Authentication Failure

> "I couldn't verify your identity after multiple attempts. I'll connect you with a support representative who can assist you further."

---

## Backend Service Unavailable

> "I'm unable to access the requested information at the moment. I'll transfer your conversation to a support representative for further assistance."

---

## Customer Requests Human Assistance

> "Certainly. I'll create a support case and transfer your conversation to a live support representative."

---

## Update Request Submitted

> "Your update request has been submitted successfully. Since these requests require manual review, I'll connect you with a support representative if you need any additional assistance."

---

# 6. Acceptance Criteria

The human escalation feature is considered successful when:

- Escalation is triggered under the correct business conditions.
- A support case is created successfully.
- A unique case ID is generated.
- Authentication status is preserved.
- Customer, policy, claim, or update request information is transferred.
- The complete conversation summary is shared with the live agent.
- Customers are informed before the transfer begins.
- Customers do not need to repeat previously collected information after the transfer.

---

# 7. API Mapping

| API | Purpose |
|-----|---------|
| `createCase()` | Create a support case and generate a case ID |
| `escalateToAgent()` | Transfer the conversation and context to a live support agent |

---

# Expected Outcome

When automated resolution is no longer possible, the Insurance Conversational AI Voice Agent seamlessly transfers the customer to a live support representative by creating a support ticket, preserving the authenticated session, transferring all relevant conversation context, and ensuring the customer receives uninterrupted assistance without repeating previously provided information.
