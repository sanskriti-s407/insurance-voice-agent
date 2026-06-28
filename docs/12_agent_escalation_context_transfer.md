# Agent Escalation with Context Transfer

## Objective

This document defines the conditions under which the Insurance Conversational AI Voice Agent transfers a customer to a live support agent and specifies the conversation context that must be transferred to ensure a seamless customer experience.

---

# 1. Purpose

The chatbot should escalate the conversation to a live support agent whenever it cannot successfully resolve the customer's request. Before transferring the conversation, the chatbot should pass all relevant customer information and conversation details to the live agent to eliminate the need for the customer to repeat information.

---

# 2. Escalation Triggers

The chatbot should initiate agent escalation under the following conditions.

| Trigger ID | Scenario                                        | Escalation Required |
| ---------- | ----------------------------------------------- | ------------------- |
| ESC-001    | Authentication failed after 3 attempts          | Yes                 |
| ESC-002    | Customer repeatedly requests a live agent       | Yes                 |
| ESC-003    | Backend API unavailable after retry limit       | Yes                 |
| ESC-004    | Unexpected system error                         | Yes                 |
| ESC-005    | Customer issue cannot be resolved automatically | Yes                 |
| ESC-006    | Business rule requires manual review            | Yes                 |

---

# 3. Context Information to Transfer

When escalation occurs, the chatbot should transfer the following information to the live support agent.

| Information              | Description                             |
| ------------------------ | --------------------------------------- |
| Customer Name            | Name of the authenticated customer      |
| Registered Mobile Number | Customer's verified mobile number       |
| Authentication Status    | Successful or Failed                    |
| Customer ID              | Unique customer identifier              |
| Policy ID                | Selected policy (if applicable)         |
| Policy Type              | Vehicle, Health, or Life Insurance      |
| Claim ID                 | Claim reference number (if available)   |
| Current Intent           | Customer's current request              |
| Conversation Summary     | Brief summary of the interaction        |
| Previous Bot Responses   | Last chatbot responses                  |
| Last API Invoked         | Most recent backend API called          |
| API Status               | Success, Timeout, or Error              |
| Escalation Reason        | Reason for transferring to a live agent |
| Timestamp                | Date and time of escalation             |

---

# 4. Escalation Workflow

### Step 1

Identify that the customer's issue cannot be resolved automatically.

### Step 2

Inform the customer that the conversation will be transferred to a live support agent.

### Step 3

Collect and package the required conversation context.

### Step 4

Create a support case using the `createCase()` API.

### Step 5

Transfer the conversation and context to the live support agent.

### Step 6

Notify the customer that the transfer has been completed successfully.

---

# 5. Expected Bot Responses

## Authentication Failure

**Bot Response**

> "I'm sorry, but I couldn't verify your identity after multiple attempts. I'll connect you with a live support agent for further assistance."

---

## API Failure

**Bot Response**

> "Our system is currently unavailable. I'll transfer your request to a live support agent who can assist you."

---

## Customer Requests Human Support

**Bot Response**

> "Sure. I'll connect you to a live support agent. Please wait while I transfer your conversation."

---

# 6. Acceptance Criteria

The escalation feature will be considered successful when:

* The chatbot correctly identifies escalation scenarios.
* A support case is created successfully.
* Customer authentication status is transferred.
* Relevant customer, policy, and claim details are transferred.
* Conversation history is available to the live agent.
* The customer is informed before the transfer occurs.
* No customer information needs to be entered again after escalation.

---

# 7. API Mapping

| Function            | Purpose                                           |
| ------------------- | ------------------------------------------------- |
| `createCase()`      | Create a customer support ticket                  |
| `escalateToAgent()` | Transfer the conversation to a live support agent |

---

# Expected Outcome

Customers requiring human assistance are transferred smoothly to a live support agent with complete conversation context, reducing repeated questioning and improving the overall customer support experience.
