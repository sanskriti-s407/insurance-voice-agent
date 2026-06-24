# Solution Architecture

## High-Level Architecture
```text
Customer
↓
Voice Agent / CX Agent Studio
↓
Authentication Flow
↓
Intent Routing Flow
↓
Business Flows
↓
Webhook Layer
↓
Mock APIs / Future Insurance Backend
↓
Response to Customer
```

## Core Components
- CX Agent Studio Agent
- Authentication Layer
- Intent Routing
- Business Service Flows
- Mock Webhook APIs
- Session Parameters
- Escalation Flow
- Live Agent Handoff

## Context Transfer to Agent
The following information should be transferred during escalation:
- Customer Name
- Customer ID
- Phone Number
- Selected Policy ID
- Selected Claim ID
- Last Intent
- Conversation Summary
- Ticket ID
