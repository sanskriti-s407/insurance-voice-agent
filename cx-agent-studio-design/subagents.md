# Subagent Architecture

The Insurance Voice Agent follows a modular subagent architecture where each subagent is responsible for a specific business capability. The Root Agent authenticates the customer, maintains session context, detects customer intent, and invokes the appropriate subagent to fulfill the request.

---

## Authentication 
The Insurance Voice Agent acts as the Root Agent, responsible for customer authentication, session management, intent detection, and routing requests to the appropriate subagent. Authentication is performed within the Root Agent before any subagent is invoked.

---

## Policy Services Subagent

### Responsibilities

- Handle multi-policy selection
- Retrieve policy details
- Display policy benefits and coverage
- Process policy renewal requests

### Supported Services

- Policy Inquiry
- Benefits Information
- Policy Renewal

### Associated APIs

- `getPolicyDetails()`
- `getBenefitsInfo()`
- `renewPolicy()`

---

## Claims Management Subagent

### Responsibilities

- Initiate new insurance claims
- Track existing claim status
- Retrieve claim information

### Supported Services

- New Claim Initiation
- Claim Status

### Associated APIs

- `initiateClaim()`
- `getClaimsStatus()`

---

## Customer Onboarding Subagent

### Responsibilities

- Present available insurance products
- Display product coverage information
- Collect customer information
- Create a new customer profile
- Generate a new insurance policy

### Supported Services

- Product Coverage
- New Policy Purchase

### Associated APIs

- `getProductCoverage()`
- `OnBoardUser()`

---

## Update Request Subagent

### Responsibilities

- Accept customer information update requests
- Submit update requests for processing
- Track update request status

### Supported Services

- Submit Update Request
- Check Update Request Status

### Associated APIs

- `RequestUpdate()`
- `getRequestStatus()`

---

## Human Escalation Subagent

### Responsibilities

- Create customer support cases
- Generate support case IDs
- Transfer complete conversation context
- Connect customers with a live support agent

### Escalation Triggers

- Customer requests a human agent
- Authentication failure after maximum retries
- Webhook or backend failure
- Unrecognized customer requests

### Associated APIs

- `createCase()`
- `escalateToAgent()`

---

# Subagent Interaction Flow

```text
                    Insurance Voice Agent
                             │
                             |
                      Authentication
                             |
                       Intent Routing
                             |                
      ┌──────────────┬──────────────┬──────────────┬──────────────┐
      │              │              │              │              │
Policy Services   Claims      Customer       Update        Human
                               Onboarding    Request     Escalation
      │              │              │              │              │
  Policy Info    Claim Status   Product       Submit        Create Case
  Benefits       New Claim      Coverage      Request       Transfer Agent
  Renewal                      New Policy     Track Status
```

## Design Benefits

- **Modular Architecture** – Each subagent handles a dedicated business capability.
- **Scalable Design** – New services can be added without affecting existing flows.
- **Reusable Components** – Common authentication and routing logic are shared across all services.
- **Improved Maintainability** – Individual subagents can be updated independently.
- **Context Preservation** – Session parameters are maintained across subagents for a seamless customer experience.
- **Efficient Human Handoff** – Complete conversation context is transferred during escalation, eliminating the need for customers to repeat information.
