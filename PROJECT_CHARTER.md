# Project Charter

## Project Name

Insurance Conversational AI Voice Agent

---

## Business Problem

Insurance contact centers handle a large volume of customer requests related to policy inquiries, benefits information, claims processing, policy renewals, customer information updates, and new policy purchases. Manual handling of these requests often results in longer wait times, inconsistent customer experiences, higher operational costs, and increased workload for support agents.

---

## Proposed Solution

Develop an AI-powered conversational voice agent using **CX Agent Studio** that securely authenticates customers, understands user intent, invokes backend APIs to perform insurance operations, and seamlessly escalates complex requests to a live support agent with complete conversation context.

The solution follows a modular architecture consisting of dedicated business service agents for Policy Services, Claims Management, Customer Onboarding, Update Requests, and Human Escalation.

---

## Project Objectives

- Automate routine insurance customer service requests.
- Provide secure customer authentication and session management.
- Reduce dependency on live agents for repetitive tasks.
- Support multiple insurance products (Motor, Health, and Life).
- Enable secure customer information update workflows.
- Provide proactive policy renewal reminders.
- Integrate backend services through APIs.
- Deliver a scalable and modular conversational AI solution.

---

## Team Roles

| Role | Team Members |
|------|--------------|
| Conversational AI Developer | Riya Kungotra, Venkata Sujay |
| Business Analyst | Sanskriti Shrey, Harshita Kaur |
| Quality Assurance Engineer | Sanskriti Shrey, Harshita Kaur |

---

## Project Scope

### In Scope

- Customer Authentication
- Intent Detection and Routing
- Multi-Policy Handling
- Policy Details
- Benefits Information
- Policy Renewal
- Claim Status
- New Claim Initiation
- Customer Onboarding
- Product Coverage
- Customer Update Requests
- Update Request Status Tracking
- Human Escalation
- Session Management
- Backend API Integration
- Evaluation and Testing

---

### Out of Scope

- Production deployment
- Real insurance backend integration
- Payment gateway integration
- Full telephony integration
- CRM integration
- AI-powered analytics dashboard
- Voice biometrics
- Multilingual support

---

## Deliverables

- Business Requirements Documentation
- CX Agent Studio Design
- Conversation Flows
- Intents and Entities
- Session Parameters
- API Contracts
- Backend APIs
- Testing Documentation
- Evaluation Reports
- Demo Scripts
- Architecture Diagrams
- GitHub Project Documentation

---

## Success Criteria

The project will be considered successful if it satisfies the following objectives:

- Customer authentication is completed securely.
- Intent routing correctly directs requests to the appropriate business service.
- All supported insurance workflows execute successfully.
- Backend APIs are invoked successfully through webhooks.
- Session context is maintained throughout the conversation.
- Update requests follow the approval workflow.
- Human escalation transfers complete conversation context.
- Golden and Scenario-based test cases pass successfully.
- Documentation is complete and reproducible.
- Final demonstration validates all end-to-end business scenarios.

---

## Expected Business Benefits

- Reduced Average Handle Time (AHT)
- Improved customer experience
- Increased automation rate
- Lower operational costs
- Faster claims and policy servicing
- Consistent customer responses
- Secure handling of sensitive customer information
- Improved scalability for future insurance services
