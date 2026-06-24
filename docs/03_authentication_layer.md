# Authentication Layer

## Purpose
Authentication acts as the first security checkpoint of the Insurance Voice Agent. It ensures that only verified customers can access sensitive insurance services.

## Protected Services
- Policy Inquiry
- Benefits Information
- Claim Status
- New Claim Initiation
- Policy Renewal
- Agent Escalation

## Design Decision
Authentication is not treated as a separate customer intent. It is handled as a common entry layer before intent routing.

## Authentication Rules
- Customer authentication is mandatory before accessing any insurance service.
- Customer must provide a valid registered mobile number and date of birth.
- Customer must correctly answer two verification questions.
- Maximum authentication attempts allowed: 3.
- If authentication fails after 3 attempts, the conversation is escalated to a live support agent.

## Session Handling
- Authentication is performed only once at the beginning of the conversation.
- After successful verification, the customer session remains active throughout the call.
- The customer is not required to authenticate repeatedly for every intent.
- Re-authentication is required only if the session expires, the call is disconnected, or sensitive account changes are requested.

## After Successful Authentication
The system retrieves all policies associated with the authenticated customer and displays them. The customer can then select a policy or ask questions related to a displayed policy without manually entering the policy ID.

## Example Response
Authentication successful. Welcome, Amit Verma.

Your Policies:
P101 – Vehicle Insurance (Active)

How can I help you today?

## Authentication Workflow
```text
Customer Starts Call
↓
Voice Agent Welcomes Customer
↓
Bot Collects Registered Mobile Number
↓
System Validates Mobile Number
↓
Bot Collects Date of Birth
↓
System Validates DOB
↓
Bot Asks Verification Question 1
↓
Customer Answers Question 1
↓
Bot Asks Verification Question 2
↓
Customer Answers Question 2
↓
System Calls validateUser(phone, dob, verification_answers)
↓
Is Authentication Successful?

YES:
Fetch Customer Profile
↓
Store Authentication Status
↓
Proceed to Intent Routing
↓
Customer Request Routed to Correct Flow

NO:
Show Authentication Failed Message
↓
Increase Retry Count
↓
Retry Count Less Than 3?
YES → Ask Details Again
NO → Create Escalation Case
↓
Transfer to Live Agent With Context
```
