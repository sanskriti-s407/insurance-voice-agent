# Requirements

## Functional Requirements

### FR-001: Customer Authentication
The system shall authenticate existing customers using their registered mobile number, date of birth, and verification answers before granting access to insurance services.

### FR-002: Customer Onboarding
The system shall allow new customers to explore available insurance products, view product coverage, and create a new insurance policy after collecting the required customer information.

### FR-003: Multi-Policy Handling
The system shall retrieve all insurance policies associated with an authenticated customer and allow the customer to select the desired policy before performing policy-specific operations.

### FR-004: Policy Inquiry
The system shall provide policy details including policy number, policy type, status, coverage information, and expiry date.

### FR-005: Benefits Information
The system shall display the benefits, coverage, and services included in the selected insurance policy.

### FR-006: Claim Status
The system shall allow authenticated customers to check the current status and details of an existing insurance claim.

### FR-007: New Claim Initiation
The system shall allow authenticated customers to initiate a new claim for an eligible insurance policy.

### FR-008: Policy Renewal
The system shall allow customers to renew eligible insurance policies and provide updated policy validity details.

### FR-009: Customer Update Request
The system shall allow customers to submit requests for updating personal information such as mobile number, date of birth, etc. The request shall be stored for manual review before any changes are applied.

### FR-010: Update Request Status
The system shall allow customers to track the status of previously submitted update requests.

### FR-011: Proactive Policy Renewal
The system shall automatically notify customers when an authenticated policy is approaching its renewal date and offer the option to renew.

### FR-012: Human Escalation
The system shall create a support case and transfer the customer to a live support agent along with the complete conversation context whenever manual assistance is required.

### FR-013: Intent Detection and Routing
The system shall identify customer intent and route the conversation to the appropriate business service flow.

### FR-014: Session Management
The system shall maintain customer authentication status and conversation context throughout the interaction until the session expires or the conversation ends.

### FR-015: Backend API Integration
The system shall invoke backend APIs to retrieve and update customer, policy, claim, onboarding, and support case information.

---

# Non-Functional Requirements

### NFR-001: Security
The system shall securely handle customer information and authenticate users before providing access to protected insurance services.

### NFR-002: Performance
The system shall provide timely responses by integrating efficiently with backend APIs.

### NFR-003: Reliability
The system shall gracefully handle webhook failures, invalid inputs, no-match events, and no-input scenarios without terminating the conversation unexpectedly.

### NFR-004: Scalability
The conversational architecture shall support the addition of new insurance products, services, and business flows with minimal changes.

### NFR-005: Availability
The system shall be available to handle customer requests whenever the backend services are operational.

### NFR-006: Maintainability
The solution shall use a modular architecture with separate business flows to simplify maintenance and future enhancements.

### NFR-007: Usability
The agent shall provide clear, natural, and consistent conversational responses throughout the customer journey.

### NFR-008: Context Preservation
The system shall preserve conversation context and transfer it to a live support agent during human escalation.

### NFR-009: Accuracy
The system shall accurately identify customer intent and execute the corresponding business workflow.

### NFR-010: Auditability
The system shall maintain request IDs, support ticket IDs, and conversation summaries to support tracking and auditing of customer interactions.
