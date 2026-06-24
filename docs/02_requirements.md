# Requirements

## Functional Requirements

### FR-001: Authentication
The system shall authenticate customers using registered mobile number, date of birth, and two verification questions.

### FR-002: New User Onboarding
The system shall allow new customers to explore insurance products and create a new policy after OTP and required data validation.

### FR-003: Policy Inquiry
The system shall provide policy details such as policy type, status, coverage details, and expiry date.

### FR-004: Benefits Information
The system shall provide policy benefits, coverage information, and included services.

### FR-005: Claim Status
The system shall allow authenticated customers to check the status of existing claims.

### FR-006: New Claim Initiation
The system shall allow authenticated customers to register a new claim against an active policy.

### FR-007: Policy Renewal
The system shall allow customers to renew an active or expiring insurance policy.

### FR-008: Agent Escalation
The system shall transfer unresolved or complex issues to a live support agent with context.

### FR-009: Intent Routing
The system shall identify customer intent and route the conversation to the correct business flow.

## Non-Functional Requirements
- Secure handling of customer data
- Session context maintained during the call
- Consistent and accurate responses
- Scalable API-driven design
- Error and fallback handling
- Seamless live agent transfer
