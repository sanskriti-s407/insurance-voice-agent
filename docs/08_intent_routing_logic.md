# Intent Routing Logic

## Customer Onboarding

**Example Utterances**

- I want to buy a new policy.
- I am a new customer.
- Get me insurance.
- Show me your insurance plans.
- I want Motor Insurance.
- I want Health Insurance.
- I want Life Insurance.

**Routes To**

- Customer Onboarding Agent

---

## Policy Services

**Example Utterances**

### Policy Inquiry

- Check my policy.
- Show my policy details.
- Policy status.
- Is my policy active?
- When does my policy expire?

### Benefits Information

- What benefits do I have?
- Show my coverage.
- What am I covered for?
- Does my policy include roadside assistance?

### Policy Renewal

- Renew my policy.
- Extend my insurance.
- My policy is expiring.
- Renew my Health Insurance.

**Routes To**

- Policy Services Agent

---

## Claims

**Example Utterances**

### Claim Status

- Check my claim.
- Track my claim.
- Claim status.
- Has my claim been approved?

### New Claim

- File a claim.
- Register a claim.
- Report an accident.
- I want to create a new claim.

**Routes To**

- Claims Agent

---

## Update Requests

**Example Utterances**

### Submit Update Request

- Update my address.
- Change my mobile number.
- Update my email.
- Change my date of birth.

### Check Request Status

- Check my update request.
- Track my request.
- Show my request status.
- Has my request been approved?

**Routes To**

- Update Request Agent

---

## Human Escalation

**Example Utterances**

- Talk to an agent.
- Connect me to customer support.
- Human assistance.
- Transfer me to a representative.
- I want to speak with an agent.

**Routes To**

- Human Escalation Agent

---

# Routing Design

After successful authentication, the Insurance Voice Agent analyzes the customer's utterance using intent detection and routes the conversation to the appropriate business agent:

- Customer Onboarding Agent
- Policy Services Agent
- Claims Agent
- Update Request Agent
- Human Escalation Agent

Each business agent manages its own workflows while maintaining the shared session context. If the system cannot confidently identify the customer's intent, the fallback handler is triggered. After repeated no-match or no-input events, the conversation is escalated to a live support agent with the complete conversation context.
