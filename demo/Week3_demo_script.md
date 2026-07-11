# Week 3 Demo Script

## Demo Objective

Demonstrate the complete functionality of the Insurance Voice Agent by validating all core business capabilities, security mechanisms, error handling, and human escalation as part of the final solution evaluation.

---

## Demo Sequence

### 1. Customer Authentication

**User Action**

Provide the registered mobile number, date of birth, and verification answers.

**Expected Result**

- Customer is authenticated successfully.
- Session context is created.
- Customer is routed to the Intent Routing Flow.

---

### 2. Multi-Policy Handling

**User Action**

```text
Show my policy details.
```

**Expected Result**

- Agent retrieves all policies linked to the customer.
- Customer selects the desired policy.
- Selected policy is stored in the session.

---

### 3. Policy Services

#### Policy Inquiry

**User Action**

```text
Show my policy details.
```

**Expected Result**

- Agent retrieves and displays policy information.

#### Benefits Information

**User Action**

```text
What benefits are included in my policy?
```

**Expected Result**

- Agent displays policy coverage and benefits.

#### Policy Renewal

**User Action**

```text
Renew my policy.
```

**Expected Result**

- Agent renews the selected policy.
- Updated validity date is returned.

---

### 4. Claims Management

#### Claim Status

**User Action**

```text
Track my claim.
```

**Expected Result**

- Agent retrieves the latest claim status.

#### New Claim

**User Action**

```text
I want to file a claim.
```

**Expected Result**

- Agent creates a new claim.
- Claim ID is generated and displayed.

---

### 5. Customer Onboarding

**User Action**

```text
I want to buy a new insurance policy.
```

**Expected Result**

- Agent displays available insurance products.
- Customer selects Motor, Health, or Life Insurance.
- Coverage information is displayed.
- Customer details are collected.
- New customer profile and policy are created successfully.

---

### 6. Customer Update Request

#### Submit Update Request

**User Action**

```text
I want to update my address.
```

**Expected Result**

- Agent collects the updated information.
- Update request is submitted.
- Request ID is generated.

#### Request Status

**User Action**

```text
Check my update request status.
```

**Expected Result**

- Agent retrieves and displays the current request status.

---

### 7. Proactive Policy Renewal

**Scenario**

Customer has a policy nearing its expiry date.

**Expected Result**

- Agent proactively informs the customer that the policy is due for renewal.
- Customer is offered the option to renew immediately.

---

### 8. Error Handling Validation

Validate the following scenarios:

- Invalid authentication credentials
- No-match handling
- No-input handling
- Invalid policy selection
- Webhook failure
- Session timeout

**Expected Result**

- Agent handles each scenario gracefully using retries, fallback prompts, or escalation.

---

### 9. Human Escalation

**User Action**

```text
I want to speak to a customer support representative.
```

**Expected Result**

- Support case is created.
- Ticket ID is generated.
- Complete conversation context is transferred.
- Customer is connected to a live support agent.

---

## Evaluation Checklist

| Capability | Status |
|------------|--------|
| Customer Authentication | ✅ |
| Intent Recognition | ✅ |
| Multi-Policy Handling | ✅ |
| Policy Inquiry | ✅ |
| Benefits Information | ✅ |
| Policy Renewal | ✅ |
| Claim Status | ✅ |
| New Claim Initiation | ✅ |
| Customer Onboarding | ✅ |
| Update Request | ✅ |
| Request Status | ✅ |
| Proactive Renewal | ✅ |
| Error Handling | ✅ |
| Human Escalation | ✅ |

---

## Success Criteria

- All customer journeys execute successfully.
- Authentication and security validations function correctly.
- Backend APIs are invoked successfully.
- Session context is maintained throughout the conversation.
- Error scenarios are handled gracefully.
- Human escalation transfers complete conversation context.
- End-to-end workflows pass evaluation without critical failures.

---

## Closing Statement

This final evaluation demonstrates the complete Insurance Voice Agent solution, validating its end-to-end functionality, security, conversational intelligence, backend integrations, and production readiness across all supported customer journeys.
