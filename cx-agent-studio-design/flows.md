# CX Agent Studio Flows

## Flow List
1. Authentication Flow
2. Intent Routing Flow
3. New User Onboarding Flow
4. Policy Inquiry Flow
5. Benefits Information Flow
6. Claim Status Flow
7. New Claim Initiation Flow
8. Policy Renewal Flow
9. Agent Escalation Flow

## Design Principle
Authentication is the default entry flow. After successful authentication, the customer is routed to the Intent Routing Flow. Each business capability is implemented as a separate flow for scalability and easier maintenance.
