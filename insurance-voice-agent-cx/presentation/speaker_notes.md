# Speaker Notes

## Project Introduction
Our project is an Insurance Conversational AI Voice Agent designed to automate common policy and claims services. The goal is to reduce customer waiting time, provide secure self-service, and reduce dependency on support agents for routine insurance requests.

## Authentication
Authentication is implemented as a common entry layer, not as a separate intent. The customer is verified using registered mobile number, date of birth, and two verification questions. Once authenticated, the session remains active throughout the call.

## Intent Routing
After authentication, the bot identifies the customer request and routes the conversation to the correct flow, such as policy inquiry, benefits, claim status, new claim, renewal, or escalation.

## Policy Renewal
Policy renewal allows customers to renew active or expiring policies using the renewPolicy API. The bot confirms renewal and shares the new validity date.

## Agent Escalation
Agent escalation handles cases where AI cannot resolve the customer request. The bot creates a support case, generates a ticket number, transfers conversation context, and connects the customer to a live agent.

## Closing
Week 1 focuses on foundation and happy path flows. Week 2 will include edge cases, fallback handling, retries, API failures, and more detailed testing.
