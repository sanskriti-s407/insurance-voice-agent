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


### Folder Description
* **docs/** → Business requirements, user stories, acceptance criteria, authentication design, conversation flows, and guardrails.
* **cx-agent-studio-design/** → Dialogflow CX implementation design including flows, pages, intents, entities, route groups, session parameters, and webhooks.
* **apis/** → API contracts and sample/mock API responses.
* **mock-data/** → Sample customer, policy, and claim datasets used for testing and development.
* **testing/** → Test strategy, happy path scenarios, authentication tests, routing tests, and regression coverage.
* **testing_excel_reports/** → Manual testing reports, Golden Evaluation reports, Scenario Evaluation reports, regression testing reports, and QA testing artifacts in CSV/Excel format.
* **architecture/** → Solution architecture, authentication workflow, intent routing, and end-to-end process diagrams.
* **demo/** → Demo script, test utterances, screenshots, and demo artifacts.

`
## Week 1 Demo Scope
For Week 1, the demo focuses on authentication, intent routing, happy path flows, and mock API-driven responses for primary insurance services.
