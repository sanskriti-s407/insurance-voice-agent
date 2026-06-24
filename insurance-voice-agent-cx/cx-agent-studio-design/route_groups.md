# Route Groups

## Authenticated User Routes
Used after customer authentication.

Routes:
- policy_inquiry → Policy Inquiry Flow
- benefits_information → Benefits Information Flow
- claim_status → Claim Status Flow
- initiate_claim → New Claim Initiation Flow
- policy_renewal → Policy Renewal Flow
- agent_escalation → Agent Escalation Flow

## New User Routes
Used when the customer is not registered.

Routes:
- new_user_onboarding → New User Onboarding Flow

## Global Escalation Routes
Available from all major pages.

Trigger phrases:
- Talk to agent
- Human support
- Customer support
- Transfer my call
- Speak to representative

Route:
- Agent Escalation Flow

## Anything Else Routes
Used after flow completion.

Routes:
- Yes → Intent Routing Flow
- No → End Session
