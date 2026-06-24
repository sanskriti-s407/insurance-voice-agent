# Insurance Conversational AI Voice Agent

## Project Overview
Insurance companies receive a high volume of customer requests related to policy inquiries, benefits information, claims processing, claim status tracking, policy renewals, and escalation requests. These requests are traditionally handled manually, which increases customer wait time, support workload, and operational cost.

This project proposes an AI-powered Insurance Conversational Voice Agent built using Google Dialogflow CX / CX Agent Studio. The agent securely authenticates customers, detects customer intent, executes policy and claims workflows using mock APIs, and escalates complex issues to a live support agent with conversation context.

## Business Objectives
- Reduce call handling time.
- Improve customer experience.
- Provide faster claim and policy services.
- Reduce operational workload.
- Provide consistent and accurate responses.
- Support secure user authentication.
- Enable seamless escalation to human agents.

## Core Capabilities
- Authentication Layer
- New User Onboarding / New Policy Purchase
- Policy Inquiry
- Benefits Information
- Claim Status
- New Claim Initiation
- Policy Renewal
- Agent Escalation
- Intent Routing
- Mock API Integration

## Technology Stack
- Google Dialogflow CX
- CX Agent Studio
- Webhooks
- Mock APIs
- JSON Mock Dataset
- GitHub Documentation

## Project Timeline
- Week 1: Foundation + Happy Path
- Week 2: Edge Cases + Fallbacks + Evaluation
- Week 3: Integration + Testing + Final Demo

## Repository Structure
```text
docs/                    Business and functional documentation
cx-agent-studio-design/  Dialogflow CX implementation design
apis/                    API contracts and mock API responses
mock-data/               Sample customer, policy, and claim data
testing/                 QA strategy and test cases
architecture/            Architecture and workflow diagrams
demo/                    Demo scripts and test utterances
presentation/            Speaker notes and mentor Q&A
references/              Original project documents
```

## Week 1 Demo Scope
For Week 1, the demo focuses on authentication, intent routing, happy path flows, and mock API-driven responses for primary insurance services.
