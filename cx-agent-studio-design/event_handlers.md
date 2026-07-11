# Event Handlers

## No-Match Default

### Prompt
- Sorry, I didn't understand your request. Could you please say it again?

### After Repeated No-Match
- I'm still unable to understand your request. I'll transfer you to a live support agent for further assistance.

---

## No-Input Default

### Prompt
- I didn't receive any response. Please say that again.

### After Repeated No-Input
- Since I haven't received a response, I'll connect you to a live support agent.

---

## Webhook Error

### Prompt
- I'm unable to retrieve the requested information at the moment due to a temporary system issue. I'll transfer you to a live support agent.

---

## Authentication Failure

### Condition
- retry_count >= 3

### Action
- Create a support case.
- Transfer the conversation to a live agent with the authentication context.

---

## Session Timeout

### Prompt
- Your session has expired for security reasons. Please authenticate again to continue.

### Action
- Clear the current session.
- Restart the authentication flow.

---

## Invalid Policy Selection

### Prompt
- I couldn't find the selected policy. Please provide a valid policy ID or choose one of your available policies.

### Action
- Reprompt for policy selection.

---

## Multiple Policies Found

### Prompt
- I found multiple policies linked to your account. Please tell me which policy you'd like to use.

### Action
- Display or read out the available policies.
- Wait for the customer to select one.

---

## Invalid Update Request

### Prompt
- I'm sorry, that information cannot be updated through this service. I'll connect you to a live support agent for further assistance.

### Action
- Create a support case.
- Transfer to a live agent.

---

## Escalation Request

### Trigger
- Customer requests a human agent.
- Repeated fallback or no-match.
- Authentication failure.
- System or webhook error.

### Action
- Create a support case.
- Transfer the complete conversation context to a live support agent.
