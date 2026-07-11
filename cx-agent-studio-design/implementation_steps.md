# CX Agent Studio Implementation Steps

## Step 1: Create Agent

Create a new CX Agent Studio agent named:

```text
Insurance Voice Agent
```

---

## Step 2: Create Flows

Create the following flows:

- Authentication Flow
- Intent Routing Flow
- Policy Services Flow
- Claims Flow
- Onboarding Flow
- Update Request Flow
- Human Escalation Flow

---

## Step 3: Create Intents

Create all intents listed in `intents.md`, including:

- Policy Inquiry
- Benefits Information
- Policy Renewal
- Claim Status
- New Claim Initiation
- Product Coverage
- New Policy Purchase
- Submit Update Request
- Check Update Request Status
- Human Escalation

---

## Step 4: Create Entities

Create all entities listed in `entities.md`.

---

## Step 5: Build the Authentication Flow

Create the following pages:

- Welcome
- Collect Phone Number
- Collect Date of Birth
- Ask Verification Questions
- Validate User
- Authentication Success
- Authentication Failure

Configure retry logic (maximum 3 attempts).

---

## Step 6: Configure Session Parameters

Configure all session parameters listed in `session_parameters.md`, including:

- customer_id
- customer_name
- phone
- policy_id
- selected_policy
- claim_id
- request_id
- authenticated
- escalation_required

---

## Step 7: Configure Webhooks

Create one webhook resource:

```text
Insurance_Backend_Webhook
```

Configure fulfillment for the following backend APIs:

- validateUser()
- getProductCoverage()
- OnBoardUser()
- getPolicyDetails()
- getBenefitsInfo()
- getClaimsStatus()
- initiateClaim()
- renewPolicy()
- RequestUpdate()
- getRequestStatus()
- createCase()
- escalateToAgent()

---

## Step 8: Build the Intent Routing Flow

After successful authentication (or onboarding completion), route customers to the Intent Routing Flow.

Create transition routes for:

- Policy Services
- Claims
- Customer Onboarding - Health, Life, Motor
- Update Request
- Human Escalation

---

## Step 9: Build Business Flows

### Policy Services Flow

Create pages for:

- Multi-Policy Selection (if applicable)
- Policy Inquiry
- Benefits Information
- Policy Renewal

---

### Claims Flow

Create pages for:

- Claim Status
- New Claim Initiation

---

### Customer Onboarding Flow

Create pages for:

- Product Coverage Detail for Selected Type
- Collect Customer Details
- Create Customer & Policy

---

### Update Request Flow

Create pages for:

- Select Update Type
- Submit Update Request
- Check Update Request Status

---

### Human Escalation Flow

Create pages for:

- Create Case
- Transfer to Live Agent
- Send Conversation Context

---

## Step 10: Configure Event Handlers

Configure:

- No Match
- No Input
- Webhook Error
- Authentication Failure
- Session Timeout
- Invalid Policy Selection
- Escalation Request

---

## Step 11: Test the Agent

Validate the following scenarios:

- Existing customer authentication
- New customer onboarding
- Multi-policy selection
- Policy inquiry
- Benefits information
- Claim status
- New claim initiation
- Policy renewal
- Customer update request
- Human escalation
- Authentication failure after 3 attempts
- Webhook failure handling
- No-input and no-match scenarios
