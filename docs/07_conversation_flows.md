# Conversation Flows

## 1. Customer Onboarding

### Flow Diagram

```mermaid
flowchart TD
    A[Customer wants a new policy] --> B[Show available insurance products]
    B --> C[Customer selects product]
    C --> D[Display product coverage]
    D --> E[Collect customer details]
    E --> F[OnBoardUser API]
    F --> G[Customer & Policy Created]
    G --> H[Display Customer ID and Policy ID]
```

### Flow Steps

1. Customer requests a new insurance policy.
2. Bot displays available insurance products.
3. Customer selects an insurance product.
4. Bot displays product coverage details.
5. Bot collects customer information.
6. System invokes **OnBoardUser()**.
7. Customer profile and policy are created.
8. Bot shares the Customer ID and Policy ID.

---

# 2. Policy Services

The Policy Services Agent handles:

- Policy Inquiry
- Benefits Information
- Policy Renewal

## Flow Diagram

```mermaid
flowchart TD
    A[Authenticated Customer] --> B[Retrieve Customer Policies]
    B --> C[Customer Selects Policy]

    C --> D{Requested Service}

    D -->|Policy Details| E[getPolicyDetails()]
    D -->|Benefits| F[getBenefitsInfo()]
    D -->|Renewal| G[renewPolicy()]

    E --> H[Display Policy Details]
    F --> I[Display Benefits]
    G --> J[Display Renewal Confirmation]
```

### Policy Inquiry Flow

1. Customer requests policy details.
2. System verifies authentication.
3. Customer selects a policy.
4. System invokes **getPolicyDetails()**.
5. Bot displays policy information.
6. Bot asks if additional assistance is required.

### Benefits Information Flow

1. Customer requests policy benefits.
2. Customer selects a policy.
3. System invokes **getBenefitsInfo()**.
4. Bot displays benefits and coverage.
5. Bot asks if additional assistance is required.

### Policy Renewal Flow

1. Customer requests policy renewal.
2. Customer selects a policy.
3. System invokes **renewPolicy()**.
4. Renewal is completed successfully.
5. Bot shares the updated validity date.

> **Proactive Renewal:** If a selected policy is approaching expiry, the agent automatically offers renewal before the customer requests it.

---

# 3. Claims

The Claims Agent handles:

- Claim Status
- New Claim Initiation

## Flow Diagram

```mermaid
flowchart TD
    A[Authenticated Customer] --> B[Retrieve Policies]
    B --> C[Customer Selects Policy]

    C --> D{Requested Service}

    D -->|Claim Status| E[Retrieve Claims]
    E --> F[Customer Selects Claim]
    F --> G[getClaimsStatus()]
    G --> H[Display Claim Status]

    D -->|New Claim| I[initiateClaim()]
    I --> J[Generate Claim ID]
    J --> K[Display Claim ID]
```

### Claim Status Flow

1. Customer requests claim status.
2. Customer selects a policy.
3. System retrieves associated claims.
4. Customer selects a claim.
5. System invokes **getClaimsStatus()**.
6. Bot displays claim details.

### New Claim Flow

1. Customer requests to file a claim.
2. Customer selects a policy.
3. System invokes **initiateClaim()**.
4. Claim is created successfully.
5. Bot displays the generated Claim ID.

---

# 4. Update Requests

The Update Request Agent handles:

- Submit Update Request
- Check Update Request Status

## Flow Diagram

```mermaid
flowchart TD
    A[Authenticated Customer] --> B{Request Type}

    B -->|Submit Update| C[Collect Updated Information]
    C --> D[RequestUpdate()]
    D --> E[Generate Request ID]

    B -->|Request Status| F[Enter Request ID]
    F --> G[getRequestStatus()]
    G --> H[Display Current Status]
```

### Submit Update Request Flow

1. Customer requests to update personal information.
2. Bot collects the updated information.
3. System invokes **RequestUpdate()**.
4. Update request is created.
5. Bot displays the generated Request ID.

### Update Request Status Flow

1. Customer requests the status of an update request.
2. Customer provides the Request ID.
3. System invokes **getRequestStatus()**.
4. Bot displays the latest request status.

---

# 5. Human Escalation

## Flow Diagram

```mermaid
flowchart TD
    A[Customer Requests Human Assistance] --> B[Collect Escalation Reason]
    B --> C[createCase()]
    C --> D[Generate Ticket]
    D --> E[Transfer Conversation Context]
    E --> F[escalateToAgent()]
    F --> G[Connected to Live Agent]
```

### Flow Steps

1. Customer requests human assistance.
2. Bot collects the escalation reason.
3. System invokes **createCase()**.
4. Support ticket is generated.
5. Conversation context is prepared.
6. System invokes **escalateToAgent()**.
7. Customer is transferred to a live support agent.
8. Bot shares the generated ticket number.

---

# Overall Conversation Flow

```mermaid
flowchart LR

A[Customer] --> B[Insurance Voice Agent]

B --> C{Authenticated?}

C -->|No| D[Customer Onboarding]

C -->|Yes| E[Intent Routing]

E --> F[Policy Services]

E --> G[Claims]

E --> H[Update Requests]

E --> I[Human Escalation]

F --> J[Backend APIs]
G --> J
H --> J
I --> J
```
