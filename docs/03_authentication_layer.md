# Authentication Layer

## Purpose

The Authentication Layer serves as the primary security gateway of the Insurance Voice Agent. It verifies customer identity before granting access to protected insurance services and ensures that sensitive customer information is accessed only by authorized users.

Authentication is performed once at the beginning of the conversation and remains valid for the duration of the active session.

---

## Protected Services

Authentication is required before accessing the following services:

- Policy Inquiry
- Benefits Information
- Claim Status
- New Claim Initiation
- Policy Renewal
- Customer Information Update Requests
- Update Request Status
- Human Escalation

> **Note:** Customer Onboarding and Product Coverage are public services and do not require authentication.

---

## Design Decision

Authentication is implemented as a common entry layer rather than a standalone customer intent.

Once authentication is successful, the Root Agent stores the customer context and routes the conversation to the appropriate business service based on the detected intent.

---

## Authentication Rules

- Customers must provide their registered mobile number.
- Customers must provide their registered date of birth.
- Customers must correctly answer the configured verification questions.
- Authentication is mandatory before accessing protected services.
- A maximum of **three authentication attempts** is allowed.
- After three unsuccessful attempts, the conversation is escalated to a live support agent.

---

## Session Management

- Authentication is performed only once per conversation.
- Customer context is maintained throughout the active session.
- Customers are not required to authenticate again when switching between supported services.
- Re-authentication is required only when:
  - The session expires.
  - The conversation is disconnected.
  - The customer starts a new conversation.

---

## Multi-Policy Handling

After successful authentication:

1. The system retrieves all insurance policies associated with the authenticated customer.
2. If multiple policies exist, the customer is prompted to select one.
3. The selected policy is stored in the session context.
4. All subsequent policy and claim operations use the selected policy until the customer chooses another.

---

## Proactive Policy Renewal

After retrieving the customer's policies, the backend automatically checks whether any policy is approaching its renewal date.

If an eligible policy is found, the agent proactively informs the customer and offers the option to renew it before proceeding with other requests.

---

## Example Conversation

**Agent**

Authentication successful.

Welcome, Amit Verma.

I found the following policies associated with your account:

- Motor Insurance (POL-MOTOR-001)
- Health Insurance (POL-HEALTH-001)
- Life Insurance (POL-LIFE-001)

Which policy would you like to manage today?

---

## Authentication Workflow

<p align="center">
<img src="https://github.com/user-attachments/assets/572b5d09-54b8-419b-b785-49510c441109" width="700">
</p>

---

## Security Considerations

- Authentication is required before exposing customer-specific information.
- Sensitive customer information is never modified directly through the conversational agent.
- Customer information updates are submitted as update requests and require manual approval before changes are applied.
- Conversation context is securely transferred during live-agent escalation.
- Authentication retry limits help prevent unauthorized access attempts.
