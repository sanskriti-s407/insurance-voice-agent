# Callbacks

## Overview

Callbacks are event-driven components in CX Agent Studio that execute automatically during different stages of a conversation. They allow the agent to validate requests, enforce security, maintain conversation context, and process API responses without affecting the user experience.

In the Happy Insurance Voice Agent, callbacks are used to improve reliability, security, response quality, and conversation continuity.

---

# Callback Execution Flow

```
Customer Request
        │
        ▼
Before Model Callback
        │
        ▼
Intent Detection
        │
        ▼
Before Tool Callback
        │
        ▼
Backend API
        │
        ▼
After Tool Callback
        │
        ▼
Model Generates Response
        │
        ▼
After Model Callback
        │
        ▼
Response Delivered to Customer
```

---

# Callback Types (WE USED)

## 1. Before Tool Callback

### Purpose

Executes immediately before a backend API is invoked.

### Responsibilities

- Validate authentication status.
- Verify required session parameters.
- Ensure Policy ID is available when required.
- Validate API input parameters.
- Prevent invalid or unauthorized API requests.

### Benefits

- Prevents invalid API calls.
- Improves backend reliability.
- Reduces processing errors.
- Enhances application security.

---

## 2. After Tool Callback

### Purpose

Executes immediately after a backend API returns a response.

### Responsibilities

- Validate API response.
- Store important values in session parameters.
- Handle API failures.
- Prepare data for the next conversational step.
- Log API execution results.
- Normalize response before sending it to the model.

### Benefits

- Maintains conversation context.
- Improves response consistency.
- Simplifies error handling.
- Enables better monitoring.

---

## 3. Before LLM Callback

### Purpose

Executes before the language model generates a response.

### Responsibilities

- Detect prompt injection attempts.
- Apply conversation guardrails.
- Mask sensitive customer information.
- Validate conversation context.
- Enforce business rules.
- Prevent unsafe model behavior.

### Benefits

- Improves response safety.
- Protects customer data.
- Prevents prompt manipulation.
- Maintains compliance with security policies.

---

## 4. After LLM Callback

### Purpose

Executes after the model generates a response and before it is delivered to the customer.

### Responsibilities

- Validate generated response.
- Remove restricted information.
- Apply response formatting.
- Ensure company policy compliance.
- Log conversation metrics.
- Record model performance.

### Benefits

- Delivers consistent responses.
- Improves customer experience.
- Supports analytics and monitoring.
- Enhances overall response quality.

---

# Callback Usage in Happy Insurance

| Callback | Usage |
|----------|-------|
| Before Tool | Validates authentication, Policy ID, and API inputs before backend execution. |
| After Tool | Stores API results, updates session parameters, and prepares data for the next step. |
| Before LLM | Applies prompt injection protection, masks sensitive information, and enforces guardrails. |
| After LLM | Validates responses, removes sensitive information, and logs conversation metrics. |

---

# Key Benefits

- Improves application security
- Reduces invalid API requests
- Maintains session continuity
- Enhances response quality
- Simplifies error handling
- Protects sensitive customer information
- Enables conversation analytics
- Supports KPI monitoring
- Improves backend reliability
- Provides a consistent customer experience

---

# Summary

Callbacks provide an additional control layer in the Happy Insurance Voice Agent by validating requests, protecting customer data, managing session context, and ensuring reliable communication between CX Agent Studio and backend services. They operate automatically throughout the conversation lifecycle and significantly improve the overall performance, security, and reliability of the conversational AI system.
