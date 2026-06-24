# Mentor Questions and Answers

## Q1. Why is authentication not treated as an intent?
Authentication is not a customer goal. It is a security layer required before accessing sensitive insurance services. Customers usually ask for services like policy details or claim status, so authentication should happen before intent routing.

## Q2. Why are mock APIs used?
Mock APIs allow the team to validate conversational flows before real backend systems are available. They help demonstrate the happy path and API-driven architecture.

## Q3. Why is intent routing important?
Intent routing allows one voice agent to support multiple insurance services by detecting the customer's request and sending it to the correct flow.

## Q4. Why is agent escalation needed?
Some issues require human judgment. Agent escalation ensures the customer can reach support while the live agent receives conversation context.

## Q5. What is the Week 1 scope?
Week 1 includes authentication, core intents, happy path flows, mock APIs, and a functional bot design for primary insurance flows.

## Q6. What will be done in Week 2?
Week 2 will include edge cases, failed authentication, invalid inputs, API failures, fallback handling, retry logic, and detailed testing.
