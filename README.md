# Insurance Conversational AI Voice Agent

## Overview

The Insurance Conversational AI Voice Agent is an AI-powered virtual assistant developed using **CX Agent Studio**. It automates common insurance customer interactions, including customer authentication, policy management, claims processing, customer onboarding, update requests, and human escalation.

The solution uses a modular, multi-agent architecture to provide secure, scalable, and context-aware conversations while integrating with backend services through webhooks and mock APIs.

---

## Business Problem

Insurance contact centers receive a large volume of customer requests every day, including:

- Policy inquiries
- Benefits and coverage information
- Claim status tracking
- New claim initiation
- Policy renewals
- Customer information updates
- New policy purchases

Handling these requests manually increases customer wait times, operational costs, and support workload while leading to inconsistent customer experiences.

This project demonstrates how Conversational AI can automate these processes while maintaining security, accuracy, and a seamless customer experience.

---

## Solution Overview

The Insurance Voice Agent authenticates customers, identifies their intent, routes requests to the appropriate business service, invokes backend APIs, and provides contextual responses.

For scenarios requiring manual intervention, the agent creates a support case and transfers the complete conversation context to a live support representative.

The solution supports both existing and new customers through dedicated onboarding and policy management workflows.

---

## Key Features

### Customer Authentication

- Secure customer authentication
- Mobile number and date of birth verification
- Security question validation
- Session management
- Authentication retry handling

### Policy Services

- Multi-policy handling
- Policy inquiry
- Benefits information
- Policy renewal
- Proactive renewal notifications

### Claims Management

- Claim status tracking
- New claim initiation

### Customer Onboarding

- Product coverage information
- New customer registration
- New policy purchase

### Customer Update Requests

- Submit customer information update requests
- Track update request status
- Human approval workflow for sensitive updates

### Human Escalation

- Support case creation
- Conversation context transfer
- Live agent handoff

---

## Solution Architecture

```
                    Customer
                        │
                        ▼
          Insurance Voice Agent
      (Authentication + Intent Routing)
                        │
     ┌────────────┬────────────┬────────────┬────────────┐
     │            │            │            │
Policy Services  Claims   Customer    Update Request
                            Onboarding
     │            │            │            │
     └────────────┴────────────┴────────────┘
                        │
                        ▼
               Backend Webhook APIs
                        │
                        ▼
                BigQuery Dataset
                        │
                        ▼
              Human Support (Escalation)
```

---

## Technology Stack

| Category | Technology |
|----------|------------|
| Conversational AI | Google Cloud Platform |
| Agent Platform | CX Agent Studio |
| Backend | Cloud Run / Python |
| Data Storage | BigQuery |
| API Integration | Webhooks |
| Data Format | JSON |
| Documentation | GitHub Markdown |

---

## Core Capabilities

- Customer Authentication
- Intent Detection
- Context Management
- Multi-Policy Handling
- Policy Inquiry
- Benefits Information
- Claim Status
- New Claim Initiation
- Policy Renewal
- Product Coverage
- Customer Onboarding
- Customer Update Requests
- Request Status Tracking
- Human Escalation
- Backend API Integration

---

## Project Structure

```
Insurance-Voice-Agent/
│
├── architecture/
├── apis/
├── cx-agent-studio-design/
├── demo/
├── docs/
├── mock-data/
├── testing/
├── testing_excel_reports/
└── README.md
```

### Folder Description

| Folder | Description |
|---------|-------------|
| **architecture/** | High-level architecture, authentication workflow, intent routing, and system diagrams |
| **apis/** | Backend API contracts and sample requests/responses |
| **cx-agent-studio-design/** | Agent design including flows, intents, entities, session parameters, webhooks, and implementation details |
| **demo/** | Demo scripts, screenshots, and sample utterances |
| **docs/** | Business requirements, user stories, acceptance criteria, authentication design, conversation flows, and guardrails |
| **mock-data/** | Sample customer, policy, claim, and request datasets |
| **testing/** | Test strategy, functional testing, regression testing, and evaluation scenarios |
| **testing_excel_reports/** | Golden evaluations, scenario evaluations, QA reports, regression reports, and KPI tracking |

---

## Backend APIs

The solution integrates with backend services through webhooks.

| API | Purpose |
|------|---------|
| `validateUser()` | Authenticate existing customers |
| `getPolicyDetails()` | Retrieve policy information |
| `getBenefitsInfo()` | Retrieve policy benefits |
| `getClaimsStatus()` | Track claim status |
| `initiateClaim()` | Create a new claim |
| `renewPolicy()` | Renew an existing policy |
| `getProductCoverage()` | Retrieve available insurance products |
| `OnBoardUser()` | Register a new customer and create a policy |
| `RequestUpdate()` | Submit customer information update requests |
| `getRequestStatus()` | Track update request status |
| `createCase()` | Create a customer support case |
| `escalateToAgent()` | Transfer conversation to a live agent |

---

## Project Timeline

### Week 1 — Foundation

- Authentication
- Intent Routing
- Policy Services
- Claims
- Happy Path Implementation
- Backend API Integration

### Week 2 — Feature Enhancements

- Customer Onboarding
- Product Coverage
- Multi-Policy Handling
- Update Request Workflow
- Proactive Policy Renewal
- Improved Prompt Engineering
- Fallbacks and callbacks
- Security Guardrails

### Week 3 — Final Evaluation

- End-to-End Testing
- Golden Evaluations
- Scenario Evaluations
- Regression Testing
- KPI Validation
- Production Readiness Assessment
- Final Demonstration

---

## Testing & Evaluation

The solution has been evaluated using multiple testing strategies:

- Authentication Testing
- Golden Evaluations
- Scenario Evaluations
- End-to-End Testing

### Evaluation Metrics

- Intent Recognition Accuracy
- Automation Rate
- Average Handle Time (AHT)
- Escalation Rate
- Task Completion Rate

---

## Design Principles

The solution was designed around the following principles:

- Modular architecture
- Secure authentication
- Context-aware conversations
- Reusable business components
- Scalable flow design
- Reliable backend integration
- Graceful error handling
- Seamless human handoff

---

## Final Outcome

This project demonstrates a production-oriented Conversational AI solution for the insurance industry by combining secure authentication, intelligent intent routing, modular business workflows, backend API integration, comprehensive testing, and seamless human escalation to deliver an efficient and scalable customer support experience.
