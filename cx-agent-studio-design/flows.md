# CX Agent Studio Flows

## Flow List

1. Authentication Flow
2. Intent Routing Flow
3. New User Onboarding Flow
4. Multi-Policy Selection Flow
5. Policy Inquiry Flow
6. Benefits Information Flow
7. Claim Status Flow
8. New Claim Initiation Flow
9. Policy Renewal Flow
10. Customer Update Request Flow
11. Agent Escalation Flow

---


```mermaid
flowchart TD

A[Intent Routing]

A --> B[Policy Services]
A --> C[Claims]
A --> D[Onboarding]
A --> E[Update Request]
A --> F[Human Escalation]

%% Policy Services
B --> B1[Policy Details]
B --> B2[Benefits Information]
B --> B3[Policy Renewal]

%% Claims
C --> C1[Claim Status]
C --> C2[Initiate Claim]

%% Onboarding
D --> D1[Health Onboarding]
D --> D2[Life Onboarding]
D --> D3[Vehicle Onboarding]

%% Update Request
E --> E1[Submit Request]
E --> E2[Request Status]

%% Human Escalation
F --> F1[Create Case]
F1 --> F2[Transfer to Live Agent]
```




## Design Principle

Authentication is the default entry flow for existing customers. New customers are routed directly to the New User Onboarding Flow.

After successful authentication, the customer is routed to the Intent Routing Flow, where the requested service is identified. If the customer has multiple policies, the Multi-Policy Selection Flow is invoked to determine the relevant policy before proceeding.

Each business capability is implemented as an independent flow to improve modularity, scalability, maintainability, and ease of future enhancements. The agent also supports customer onboarding, product coverage inquiries, customer information update requests, update request status tracking, and seamless escalation to a live agent with full conversation context when required.
