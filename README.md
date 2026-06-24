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
insurance-voice-agent-cx
│
├── README.md
├── PROJECT_CHARTER.md
├── WEEKLY_PLAN.md
│
├── docs
│   ├── 01_business_problem.md
│   ├── 02_requirements.md
│   ├── 03_authentication_layer.md
│   ├── 04_intent_catalog.md
│   ├── 05_user_stories.md
│   ├── 06_acceptance_criteria.md
│   ├── 07_conversation_flows.md
│   ├── 08_intent_routing_logic.md
│   └── 09_security_guardrails.md
│
├── cx-agent-studio-design
│   ├── flows.md
│   ├── pages.md
│   ├── intents.md
│   ├── entities.md
│   ├── session_parameters.md
│   ├── route_groups.md
│   ├── event_handlers.md
│   ├── webhooks.md
│   └── implementation_steps.md
│
├── apis
│   ├── api_contracts.md
│   └── mock_api_responses.md
│
├── mock-data
│   ├── customers.json
│   ├── policies.json
│   └── claims.json
│
├── testing
│   ├── test_strategy.md
│   ├── happy_path_test_cases.md
│   ├── authentication_test_cases.md
│   ├── intent_routing_test_cases.md
│   └── regression_test_cases.md
│
├── architecture
│   ├── solution_architecture.md
│   ├── authentication_workflow.png
│   ├── intent_routing_diagram.png
│   └── end_to_end_process_flow.png
│
├── demo
│   ├── week1_demo_script.md
│   ├── demo_test_utterances.md
│   └── screenshots
│
├── presentation
│   ├── speaker_notes.md
│   ├── mentor_questions_answers.md
│   └── final_presentation.pptx
│
└── references
    ├── insurance_vehicle_claims_requirement.pdf
    ├── week1_documentation.pdf
    └── supporting_resources
```

### Folder Description

* **docs/** → Business requirements, user stories, acceptance criteria, authentication design, conversation flows, and guardrails.
* **cx-agent-studio-design/** → Dialogflow CX implementation design including flows, pages, intents, entities, route groups, session parameters, and webhooks.
* **apis/** → API contracts and sample/mock API responses.
* **mock-data/** → Sample customer, policy, and claim datasets used for testing and development.
* **testing/** → Test strategy, happy path scenarios, authentication tests, routing tests, and regression coverage.
* **architecture/** → Solution architecture, authentication workflow, intent routing, and end-to-end process diagrams.
* **demo/** → Demo script, test utterances, screenshots, and demo artifacts.
* **presentation/** → Speaker notes, mentor Q&A preparation, and presentation materials.
* **references/** → Requirement documents, project documentation, and supporting resources.

```
```


## Week 1 Demo Scope
For Week 1, the demo focuses on authentication, intent routing, happy path flows, and mock API-driven responses for primary insurance services.
