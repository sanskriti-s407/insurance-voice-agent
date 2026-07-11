# Week 2 Demo Script

## Demo Objective

Demonstrate the production readiness of the Insurance Voice Agent by validating authentication failures, fallback handling, invalid inputs, webhook failures, session management, and seamless human escalation.

---

## Demo Sequence

### 1. Authentication Failure

**User Action**

Provide an incorrect mobile number, date of birth, or verification answer three times.

**Expected Result**

- Agent prompts the customer to retry authentication.
- Authentication retry count is incremented.
- After three unsuccessful attempts, authentication fails.
- A support case is created.
- The conversation is transferred to a live support agent with the conversation context.

---

### 2. No-Match Handling

**User Action**

Provide an unrelated or unsupported request.

**Example**

```text
I love cricket.
```

**Expected Result**

- Agent asks the customer to repeat the request.
- After repeated no-match events, the conversation is escalated to a live support agent.

---

### 3. No-Input Handling

**User Action**

Remain silent without providing any response.

**Expected Result**

- Agent prompts the customer again.
- After repeated no-input events, the conversation is transferred to a live support agent.

---

### 4. Invalid Policy Selection

**User Action**

```text
Show policy ABC123.
```

**Expected Result**

- Agent informs the customer that the policy could not be found.
- Customer is prompted to select a valid policy.
- Conversation continues after a valid policy is selected.

---

### 5. Webhook Failure

**Scenario**

The backend API is unavailable or returns an error.

**Expected Result**

- Agent informs the customer that the requested information cannot be retrieved at the moment.
- A support case is created.
- The conversation is transferred to a live support agent.

---

### 6. Session Timeout

**Scenario**

The customer remains inactive for an extended period.

**Expected Result**

- Agent informs the customer that the session has expired.
- Customer is prompted to authenticate again before continuing.

---

### 7. Human Escalation

**User Action**

```text
I want to speak to a customer support representative.
```

**Expected Result**

- Agent creates a support case.
- A case ID is generated.
- Conversation context is summarized.
- Customer is transferred to a live support agent.

---

## Validation Checklist

| Scenario | Expected Outcome |
|----------|------------------|
| Authentication Failure | Escalation after maximum retries |
| No-Match | Reprompt followed by escalation |
| No-Input | Reprompt followed by escalation |
| Invalid Policy | Prompt for valid policy selection |
| Webhook Failure | Graceful error handling and escalation |
| Session Timeout | Re-authentication required |
| Human Escalation | Support ticket created and context transferred |

---

## Success Criteria

- Authentication retry mechanism functions correctly.
- Event handlers respond appropriately to invalid inputs.
- Backend failures are handled gracefully.
- Session timeout triggers re-authentication.
- Complete conversation context is transferred during escalation.
- All fallback scenarios execute without interrupting the customer experience.

---

## Closing Statement

This Week 3 demonstration validates the production readiness of the Insurance Voice Agent by showcasing robust authentication, fallback handling, retry mechanisms, session management, backend failure recovery, and seamless live-agent escalation with full conversation context.
