#  Edge Case Specification

## Objective

This document defines the edge cases that the Insurance Conversational AI Voice Agent must handle to ensure secure, reliable, and production-ready conversations. It covers authentication, onboarding, policy services, claims, update requests, backend failures, and conversation handling.

---

# 1. Authentication Edge Cases

## EC-AUTH-001: Invalid Mobile Number

### Scenario

The customer enters an unregistered mobile number.

### Expected Bot Behaviour

- Inform the customer that the mobile number could not be verified.
- Ask the customer to enter the registered mobile number again.

### Retry Policy

- Maximum **3 attempts**.

### Escalation

- After **3 failed attempts**, create a support case and transfer the customer to a live agent.

---

## EC-AUTH-002: Invalid Date of Birth

### Scenario

The customer enters an incorrect date of birth.

### Expected Bot Behaviour

- Inform the customer that the entered DOB does not match the records.
- Ask the customer to try again.

### Retry Policy

- Maximum **3 attempts**.

### Escalation

- Escalate after the third unsuccessful attempt.

---

## EC-AUTH-003: Incorrect Verification Answers

### Scenario

The customer provides incorrect verification answers.

### Expected Bot Behaviour

- Inform the customer that verification failed.
- Ask the verification questions again.

### Retry Policy

- Maximum **3 attempts**.

### Escalation

- Transfer the customer to a live support agent.

---

## EC-AUTH-004: Authentication Failure

### Scenario

The customer cannot be authenticated.

### Expected Bot Behaviour

- Notify the customer that authentication was unsuccessful.
- Explain that the conversation will be transferred to a support representative.

### Escalation

- Generate a support case and transfer the conversation.

---

# 2. Customer Onboarding Edge Cases

## EC-ONB-001: Unsupported Insurance Product

### Scenario

The customer requests an product that is not supported.

### Expected Bot Behaviour

- Inform the customer about the available insurance products.
- Ask the customer to choose Motor, Health, or Life Insurance.

---

## EC-ONB-002: Duplicate Customer

### Scenario

The customer already exists in the system.

### Expected Bot Behaviour

- Inform the customer that an account already exists.
- Recommend signing in instead of creating a new account.

---

## EC-ONB-003: Missing Mandatory Information

### Scenario

The customer skips mandatory onboarding information.

### Expected Bot Behaviour

- Inform the customer which information is missing.
- Continue only after all required information is collected.

---

# 3. Policy Services Edge Cases

## EC-POL-001: Policy Nearing Expiry

### Scenario

A selected policy is approaching its expiry date.

### Expected Bot Behaviour

- Proactively inform the customer.
- Offer immediate policy renewal.

---

## EC-POL-002: Policy Already Expired

### Scenario

The selected policy has expired.

### Expected Bot Behaviour

- Inform the customer that the policy has expired.
- Offer the renewal process if applicable.

---

# 4. Claims Edge Cases

## EC-CLM-001: No Claims Found

### Scenario

The customer has no registered claims.

### Expected Bot Behaviour

- Inform the customer that no claims were found.
- Offer the option to initiate a new claim.

---

## EC-CLM-002: Closed Claim

### Scenario

The selected claim has already been settled.

### Expected Bot Behaviour

- Inform the customer that the claim has been closed.
- Display the final claim outcome.

---

# 5. Update Request Edge Cases

## EC-UPD-001: Invalid Update Request

### Scenario

The customer attempts to update an unsupported field.

### Expected Bot Behaviour

- Inform the customer about the fields that can be updated.
- Request a valid update type.

---

## EC-UPD-002: Duplicate Update Request

### Scenario

An update request for the same field is already pending.

### Expected Bot Behaviour

- Inform the customer that a request is already under review.
- Recommend checking the existing request status.

---

## EC-UPD-003: Invalid Request ID

### Scenario

The customer enters an invalid Request ID.

### Expected Bot Behaviour

- Inform the customer that the Request ID could not be found.
- Ask the customer to verify the Request ID.

---

# 6. API Edge Cases

## EC-API-001: API Timeout

### Scenario

The backend service does not respond.

### Expected Bot Behaviour

- Inform the customer that the request is taking longer than expected.

### Retry Policy

- Retry twice.

### Escalation

- Transfer to a live support agent if the issue persists.

---

## EC-API-002: Internal Server Error

### Scenario

The backend returns an error.

### Expected Bot Behaviour

- Display a customer-friendly error message.
- Do not expose technical details.

---

## EC-API-003: Empty Response

### Scenario

The backend returns no data.

### Expected Bot Behaviour

- Inform the customer that no information is available.
- Ask whether they would like to try again.

---

## EC-API-004: Invalid Response

### Scenario

The API response is incomplete or corrupted.

### Expected Bot Behaviour

- Log the error.
- Display a generic error message.
- Escalate if required.

---

# 7. Conversation Edge Cases

## EC-CONV-001: Unknown Intent

### Scenario

The customer asks an unrelated question.

### Expected Bot Behaviour

- Inform the customer that only insurance-related services are supported.
- Redirect the conversation to available services.

---

## EC-CONV-002: No Response

### Scenario

The customer remains silent.

### Expected Bot Behaviour

- Reprompt twice.
- End or escalate after prolonged inactivity.

---

## EC-CONV-003: Intent Switching

### Scenario

The customer changes their request during the conversation.

### Expected Bot Behaviour

- Detect the new intent.
- Preserve authentication and session context.
- Route the customer to the appropriate business agent.

---

## EC-CONV-004: Human Assistance Requested

### Scenario

The customer asks for a support representative.

### Expected Bot Behaviour

- Create a support ticket.
- Transfer the complete conversation context.
- Connect the customer to a live support agent.

---

# Summary

| Category | Number of Edge Cases |
|----------|---------------------:|
| Authentication | 4 |
| Customer Onboarding | 3 |
| Policy Services | 2 |
| Claims | 2 |
| Update Requests | 3 |
| API | 4 |
| Conversation | 4 |
| **Total** | **22** |
