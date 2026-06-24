# Security and Guardrails

## Authentication Guardrails
- Do not provide policy, benefit, claim, or renewal information before successful authentication.
- Authentication must use registered mobile number, DOB, and two verification questions.
- Maximum authentication attempts allowed: 3.
- Failed authentication after 3 attempts must route to agent escalation.

## Data Privacy Guardrails
- Mask sensitive customer information in logs and demo screenshots.
- Do not expose complete phone numbers or personal identifiers in user-facing responses unless required.
- Do not store sensitive data beyond active session requirements.

## API Guardrails
- Do not expose internal API errors to the customer.
- Use customer-friendly error messages.
- Retry or escalate if backend systems fail.

## Conversation Guardrails
- Confirm customer intent before performing important actions such as renewal or claim initiation.
- Escalate if customer repeatedly asks for human assistance.
- Maintain conversation context for live agent handoff.
