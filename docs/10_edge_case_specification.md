# Week 2 – Edge Case Specification

## Objective

This document defines the edge cases that the Insurance Conversational AI Voice Agent must handle to ensure reliable, production-ready conversations. For each scenario, the expected system behavior, retry policy, fallback, and escalation conditions are specified.

---

# 1. Authentication Edge Cases

## EC-AUTH-001: Invalid Phone Number

### Scenario

The customer enters a phone number that is not registered in the system.

### Expected Bot Behaviour

* Inform the customer that the phone number could not be verified.
* Ask the customer to enter the registered phone number again.

### Retry Policy

* Maximum **3 attempts**.

### Fallback

* Return to the authentication step.

### Escalation

* After **3 failed attempts**, transfer the customer to a live agent.

---

## EC-AUTH-002: Invalid Date of Birth

### Scenario

The customer enters an incorrect date of birth.

### Expected Bot Behaviour

* Inform the customer that the DOB does not match the registered records.
* Prompt the customer to re-enter the DOB.

### Retry Policy

* Maximum **3 attempts**.

### Fallback

* Restart DOB verification.

### Escalation

* Escalate after the **third unsuccessful attempt**.

---

## EC-AUTH-003: Incorrect Verification Answers

### Scenario

The customer answers one or more security questions incorrectly.

### Expected Bot Behaviour

* Inform the customer that verification failed.
* Ask the verification questions again.

### Retry Policy

* Maximum **3 attempts**.

### Fallback

* Restart the verification process.

### Escalation

* Transfer to a live agent after **3 failed attempts**.

---

## EC-AUTH-004: Authentication Failure

### Scenario

Customer cannot be authenticated after all verification attempts.

### Expected Bot Behaviour

* Notify the customer that authentication could not be completed.
* Explain that a support agent will assist.

### Retry Policy

* No further retries.

### Escalation

* Create a support case and transfer the conversation to a live agent.

---

# 2. Policy Edge Cases

## EC-POL-001: No Active Policy Found

### Scenario

The authenticated customer does not have an active insurance policy.

### Expected Bot Behaviour

* Inform the customer that no active policy exists.
* Offer policy purchase options or live agent assistance.

---

## EC-POL-002: Expired Policy

### Scenario

The selected policy has expired.

### Expected Bot Behaviour

* Inform the customer that the policy has expired.
* Offer the **Policy Renewal** service.

---

## EC-POL-003: Invalid Policy ID

### Scenario

The entered Policy ID does not exist.

### Expected Bot Behaviour

* Inform the customer that the Policy ID is invalid.
* Ask the customer to verify and re-enter the Policy ID.

### Retry Policy

* Maximum **2 attempts**.

### Fallback

* Return to the main menu after the retry limit.

---

# 3. Claim Edge Cases

## EC-CLM-001: No Claims Under Selected Policy

### Scenario

The selected policy has no registered claims.

### Expected Bot Behaviour

* Inform the customer that no claims were found.
* Offer **New Claim Initiation**.

---

## EC-CLM-002: Invalid Claim ID

### Scenario

The entered Claim ID is invalid.

### Expected Bot Behaviour

* Ask the customer to verify and re-enter the Claim ID.

### Retry Policy

* Maximum **2 attempts**.

### Fallback

* Return to the previous menu.

---

## EC-CLM-003: Claim Already Closed

### Scenario

The customer checks the status of a closed claim.

### Expected Bot Behaviour

* Inform the customer that the claim has already been settled.
* Display the final claim status.

---

# 4. API Edge Cases

## EC-API-001: API Timeout

### Scenario

The backend service does not respond within the expected time.

### Expected Bot Behaviour

* Inform the customer that the request is taking longer than expected.

### Retry Policy

* Retry the API request **twice**.

### Fallback

* Suggest trying again later.

### Escalation

* Transfer to a live agent if the issue continues.

---

## EC-API-002: API Error

### Scenario

The backend returns an internal server error.

### Expected Bot Behaviour

* Apologize for the inconvenience.
* Inform the customer that the service is temporarily unavailable.

### Escalation

* Transfer to a live agent if required.

---

## EC-API-003: Empty Response

### Scenario

The API returns no data.

### Expected Bot Behaviour

* Inform the customer that no information is available.
* Ask whether they would like to try again.

---

## EC-API-004: Invalid Response Format

### Scenario

The API response is incomplete or corrupted.

### Expected Bot Behaviour

* Log the error.
* Display a generic system error message.
* Escalate if necessary.

---

# 5. Conversation Edge Cases

## EC-CONV-001: Unrelated User Input

### Scenario

The customer asks a question unrelated to insurance services.

### Expected Bot Behaviour

* Politely inform the customer that the assistant supports insurance-related queries.
* Redirect the customer to available services.

---

## EC-CONV-002: User Silence

### Scenario

The customer does not respond.

### Expected Bot Behaviour

* Reprompt the customer **twice**.
* End the conversation after prolonged inactivity.

---

## EC-CONV-003: Repeated Request for Human Support

### Scenario

The customer repeatedly asks to speak with a human agent.

### Expected Bot Behaviour

* Immediately initiate the agent escalation flow.
* Transfer the current conversation context to the live agent.

---

## EC-CONV-004: User Changes Intent Mid-Conversation

### Scenario

The customer switches to a different request before completing the current one.

### Expected Bot Behaviour

* Detect the new intent.
* Preserve the authenticated session.
* Route the conversation to the newly requested intent.

---

# Summary

| Category       | Number of Edge Cases |
| -------------- | -------------------: |
| Authentication |                    4 |
| Policy         |                    3 |
| Claims         |                    3 |
| API            |                    4 |
| Conversation   |                    4 |
| **Total**      |               **18** |
