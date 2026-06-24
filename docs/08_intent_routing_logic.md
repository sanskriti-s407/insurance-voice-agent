# Intent Routing Logic

| User Says | Routed Intent |
|---|---|
| I want to buy a new policy | New User Onboarding |
| I am a new customer | New User Onboarding |
| Get me insurance | New User Onboarding |
| Check my policy | Policy Inquiry |
| Show policy details | Policy Inquiry |
| Policy status | Policy Inquiry |
| What benefits do I have? | Benefits Information |
| Show my coverage | Benefits Information |
| Roadside assistance | Benefits Information |
| Check my claim | Claim Status |
| Track claim | Claim Status |
| Claim status | Claim Status |
| File a claim | New Claim Initiation |
| Register a claim | New Claim Initiation |
| Report an accident | New Claim Initiation |
| Renew policy | Policy Renewal |
| Extend insurance | Policy Renewal |
| Policy renewal | Policy Renewal |
| Talk to agent | Agent Escalation |
| Customer support | Agent Escalation |
| Human assistance | Agent Escalation |

## Routing Design
After authentication, customer utterances are mapped to the correct business flow through intent detection. If the system cannot confidently identify an intent, fallback handling is triggered.
