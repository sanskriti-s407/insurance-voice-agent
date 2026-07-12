# Fallback, Retry & Verification Checkpoints

## Objective

This document defines the fallback strategies, retry policies, verification checkpoints, and session validation rules that ensure the Insurance Conversational AI Voice Agent delivers secure, reliable, and production-ready conversations.

---

# 1. Fallback Strategy

Fallbacks help the conversation recover gracefully whenever the requested action cannot be completed.

| Scenario | Bot Response | Next Action |
|----------|--------------|-------------|
| Invalid Mobile Number | Inform the customer that the mobile number could not be verified. | Ask the customer to enter the registered mobile number again. |
| Invalid Date of Birth | Inform the customer that the DOB does not match the records. | Ask the customer to enter the DOB again. |
| Incorrect Verification Answers | Inform the customer that verification failed. | Repeat the verification questions. |
| Multiple Policies Available | Display all available policies. | Ask the customer to select the required policy. |
| No Active Policies | Inform the customer that no active policies were found. | Offer new policy purchase or human assistance. |
| No Claims Found | Inform the customer that no claims exist. | Offer New Claim Initiation. |
| Invalid Claim Selection | Inform the customer that the selected claim could not be found. | Ask the customer to select another claim. |
| Invalid Update Request ID | Inform the customer that the Request ID is invalid. | Ask the customer to verify the Request ID. |
| API Timeout | Inform the customer that the service is taking longer than expected. | Retry the API automatically. |
| Backend Error | Apologize for the inconvenience. | Retry or transfer to a live agent. |
| Empty API Response | Inform the customer that no information is available. | Ask whether the customer would like to try again. |
| Unknown Intent | Inform the customer about supported insurance services. | Redirect to Intent Routing. |
| No User Response | Reprompt the customer. | End or escalate after retry limit. |

---

# 2. Retry Policy

Retry limits prevent endless conversation loops while giving customers sufficient opportunities to correct their input.

| Scenario | Maximum Retries | Action After Retry Limit |
|----------|----------------:|--------------------------|
| Mobile Number | 3 | Escalate to Live Agent |
| Date of Birth | 3 | Escalate to Live Agent |
| Verification Questions | 3 | Escalate to Live Agent |
| Policy Selection | 2 | Return to Policy Selection |
| Claim Selection | 2 | Return to Claims Menu |
| Update Request ID | 2 | Return to Update Request Menu |
| API Timeout | 2 | Escalate to Live Agent |
| Unknown Intent | 2 | Transfer to Live Agent |
| No User Response | 2 | End Conversation |

---

# 3. Verification Checkpoints

The following validations must be completed before sensitive operations are performed.

| Operation | Verification Required |
|-----------|----------------------|
| Policy Services | Customer Authenticated + Policy Selected |
| Claim Status | Customer Authenticated + Claim Selected |
| New Claim Initiation | Customer Authenticated + Active Policy |
| Update Request Submission | Customer Authenticated |
| Update Request Status | Valid Request ID |
| Policy Renewal | Customer Authenticated + Eligible Policy |
| Human Escalation | Conversation Context Available |
| Customer Onboarding | Required Customer Details Collected |

---

# 4. Session Validation

The system continuously validates session information throughout the conversation.

| Checkpoint | Expected Behaviour |
|------------|-------------------|
| Session Timeout | Request re-authentication. |
| Authentication Expired | Restart authentication flow. |
| Missing Required Parameters | Prompt the customer for missing information. |
| Multiple Policies Available | Preserve selected policy throughout the session. |
| Invalid Session Data | Clear session variables and restart the conversation. |
| Customer Changes Policy | Update the selected policy and continue the conversation. |

---

# 5. Conversation Recovery

If the conversation cannot continue normally, the assistant should recover using the following strategy.

| Situation | Recovery Action |
|-----------|-----------------|
| Backend Failure | Retry → Friendly Error Message → Live Agent |
| Invalid Customer Input | Reprompt the customer |
| Multiple Invalid Inputs | Transfer to Live Agent |
| Customer Changes Intent | Preserve session and route to the appropriate business agent |
| Customer Requests Human Assistance | Immediately initiate Human Escalation |
| Policy Nearing Expiry | Proactively offer Policy Renewal |
| Pending Update Request | Inform the customer and offer Request Status Tracking |

---

# 6. Escalation Triggers

The conversation is automatically transferred to a live support agent under the following conditions:

- Authentication fails after three attempts.
- Repeated no-match events.
- Repeated no-input events.
- Backend API failures continue after retries.
- Customer explicitly requests human assistance.
- Conversation cannot continue because of missing or invalid session data.

Before transfer, the system:

- Creates a support case.
- Generates a Ticket ID.
- Transfers the complete conversation summary.
- Preserves authentication and customer context for the live agent.

---

# 7. Success Criteria

The Insurance Conversational AI Voice Agent is considered production-ready when:

- Authentication and authorization rules are consistently enforced.
- Retry limits prevent infinite conversation loops.
- Fallback responses exist for all supported failure scenarios.
- Session context is preserved across multiple customer requests.
- Customers with multiple policies can seamlessly switch between policies.
- Update requests are submitted securely without directly modifying customer information.
- Backend failures are handled gracefully without exposing internal system details.
- Human escalation includes the complete conversation context and Ticket ID.
- The agent supports smooth recovery from unexpected situations while maintaining a secure and consistent customer experience.
