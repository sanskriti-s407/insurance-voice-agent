# Fallback, Retry & Verification Checkpoints

## Objective

This document defines the fallback mechanisms, retry policies, and verification checkpoints required to make the Insurance Conversational AI Voice Agent reliable and production-ready.

---

# 1. Fallback Strategy

Fallbacks ensure that the conversation continues smoothly whenever the bot cannot complete a request.

| Scenario                     | Bot Response                                                                     | Next Action                                               |
| ---------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Invalid phone number         | Inform the customer that the number is not registered.                           | Ask the customer to re-enter the registered phone number. |
| Invalid DOB                  | Inform the customer that verification failed.                                    | Ask for DOB again.                                        |
| Invalid verification answers | Inform the customer that verification failed.                                    | Repeat verification questions.                            |
| Invalid Policy ID            | Inform the customer that the policy could not be found.                          | Ask for the Policy ID again.                              |
| Invalid Claim ID             | Inform the customer that the claim could not be found.                           | Ask for the Claim ID again.                               |
| No active policy found       | Inform the customer that no active policy exists.                                | Offer Policy Purchase or Agent Support.                   |
| API Timeout                  | Inform the customer that the service is taking longer than expected.             | Retry the API call automatically.                         |
| API Internal Error           | Apologize for the inconvenience.                                                 | Offer another attempt or connect to a live agent.         |
| Empty API Response           | Inform the customer that information is unavailable.                             | Ask whether they would like to try again later.           |
| Unrelated User Input         | Inform the customer that the assistant supports insurance-related services only. | Redirect to supported intents.                            |
| User Silence                 | Reprompt the customer.                                                           | End the conversation after timeout.                       |

---

# 2. Retry Policy

Retry limits prevent infinite conversation loops while providing customers with sufficient opportunities to correct their input.

| Scenario               | Maximum Retries | Action After Retry Limit |
| ---------------------- | --------------: | ------------------------ |
| Phone Number           |               3 | Escalate to Live Agent   |
| Date of Birth          |               3 | Escalate to Live Agent   |
| Verification Questions |               3 | Escalate to Live Agent   |
| Policy ID              |               2 | Return to Main Menu      |
| Claim ID               |               2 | Return to Main Menu      |
| API Timeout            |               2 | Escalate to Live Agent   |
| User Silence           |               2 | End Conversation         |
| Unknown Intent         |               2 | Transfer to Live Agent   |

---

# 3. Verification Checkpoints

Before allowing access to sensitive insurance information, the following validations must be completed.

| Operation            | Verification Required                                |
| -------------------- | ---------------------------------------------------- |
| Policy Inquiry       | Customer Authentication Successful                   |
| Benefits Information | Active Policy Exists                                 |
| Claim Status         | Customer Authenticated + Valid Policy                |
| Claim Initiation     | Customer Authenticated + Active Policy               |
| Policy Renewal       | Customer Authenticated + Policy Eligible for Renewal |
| Agent Escalation     | Conversation Context Available                       |
| New User Onboarding  | Required Customer Details Provided                   |

---

# 4. Session Validation

The system should validate the customer session throughout the conversation.

| Checkpoint                  | Expected Behaviour                                     |
| --------------------------- | ------------------------------------------------------ |
| Session Timeout             | Ask the customer to authenticate again.                |
| Authentication Expired      | Restart the authentication flow.                       |
| Missing Required Parameters | Prompt the customer for the missing information.       |
| Invalid Session Data        | Clear session parameters and restart the conversation. |

---

# 5. Conversation Recovery

If the conversation cannot continue normally, the assistant should recover using the following strategy.

| Situation                 | Recovery Action                                     |
| ------------------------- | --------------------------------------------------- |
| API Failure               | Retry API → Apologize → Escalate                    |
| Invalid Customer Input    | Reprompt the customer                               |
| Multiple Invalid Inputs   | Transfer to a live agent                            |
| User Changes Intent       | Preserve authentication and route to the new intent |
| User Requests Human Agent | Immediately initiate agent escalation               |

---

# 6. Success Criteria

The conversational flow will be considered production-ready when:

* All authentication validation rules are enforced.
* Retry limits are correctly implemented.
* Fallback responses are displayed for every supported failure scenario.
* Verification checkpoints prevent unauthorized access.
* Conversation recovery successfully handles unexpected situations.
* Customers are transferred to a live agent whenever automated resolution is no longer possible.
