# CX Agent Studio Implementation Steps

## Step 1: Create Agent
Create a new CX Agent Studio agent named:
```text
Insurance Voice Agent
```

## Step 2: Create Flows
Create:
- Authentication Flow
- Intent Routing Flow
- New User Onboarding Flow
- Policy Inquiry Flow
- Benefits Information Flow
- Claim Status Flow
- New Claim Initiation Flow
- Policy Renewal Flow
- Agent Escalation Flow

## Step 3: Create Intents
Create all intents listed in `intents.md`.

## Step 4: Create Entities
Create all entities listed in `entities.md`.

## Step 5: Create Authentication Flow
Add pages:
- Collect Mobile Number
- Collect DOB
- Verification Question 1
- Verification Question 2
- Validate User
- Authentication Success
- Authentication Failure

## Step 6: Configure Session Parameters
Use session parameters listed in `session_parameters.md`.

## Step 7: Configure Webhooks
Create one webhook resource:
```text
Insurance_Backend_Webhook
```
Map fulfillment tags to backend mock API actions.

## Step 8: Configure Intent Routing
After authentication success, route customer to Intent Routing Flow. Add transition routes for all business intents.

## Step 9: Build Business Flows
Create one separate flow per intent.

## Step 10: Add Fallbacks and Escalation
Add no-match, no-input, webhook error, and retry handling.

## Step 11: Test in Simulator
Test all happy paths and authentication failure escalation.
