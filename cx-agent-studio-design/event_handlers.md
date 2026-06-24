# Event Handlers

## No-Match Default
Prompt:
text
Sorry, I could not understand that. Could you please repeat your request?


After repeated no-match:
```text
I am unable to understand your request clearly. I will connect you to a support agent for better assistance.
```

## No-Input Default
Prompt:
```text
I did not receive any response. Please say that again.
```

After repeated no-input:
```text
I will connect you to a support agent so that your request can be handled properly.
```

## Webhook Error
Prompt:
```text
I am unable to fetch the required details right now. Let me connect you to a support agent.
```

## Authentication Failure
Condition:
```text
retry_count >= 3
```

Action:
Route to Agent Escalation Flow.

## Session Timeout
Prompt:
```text
Your session has expired for security reasons. Please authenticate again to continue.
```
