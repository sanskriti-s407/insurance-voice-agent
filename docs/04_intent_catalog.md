# Intent Catalog

## 1. New User Onboarding

**Intent Name:** `new_user_onboarding`

**Purpose:**
Allows new customers to explore available insurance products, view product coverage, provide customer details, and purchase a new insurance policy.

**Example User Queries:**

- I want to buy a new policy.
- I am a new customer.
- I don't have a policy yet.
- Show me your insurance plans.
- I want Motor Insurance.
- I want Health Insurance.
- I want Life Insurance.

**APIs Used:**

- getProductCoverage()
- OnBoardUser()

---

## 2. Policy Inquiry

**Intent Name:** `policy_inquiry`

**Purpose:**
Allows authenticated customers to retrieve policy information, including policy type, status, coverage details, and expiry date.

**Example User Queries:**

- Show my policy details.
- Check my policy information.
- Is my policy active?
- When does my policy expire?
- Show my Motor Insurance policy.

**API Used:**

- getPolicyDetails()

---

## 3. Benefits Information

**Intent Name:** `benefits_information`

**Purpose:**
Allows authenticated customers to view policy benefits, coverage, and included services.

**Example User Queries:**

- What benefits are included in my policy?
- Show my policy coverage.
- What am I covered for?
- Does my Motor Insurance include roadside assistance?
- What services are included in my insurance?

**API Used:**

- getBenefitsInfo()

---

## 4. Claim Status

**Intent Name:** `claim_status`

**Purpose:**
Allows authenticated customers to check the current status of an existing insurance claim.

**Example User Queries:**

- Track my claim.
- Check my claim status.
- Has my claim been approved?
- Show my claim progress.
- Track my Motor Insurance claim.

**API Used:**

- getClaimsStatus()

---

## 5. New Claim Initiation

**Intent Name:** `initiate_claim`

**Purpose:**
Allows authenticated customers to register a new insurance claim for an eligible policy.

**Example User Queries:**

- I want to file a claim.
- Register a new claim.
- Report an accident.
- Create a claim request.
- Start a new insurance claim.

**API Used:**

- initiateClaim()

---

## 6. Policy Renewal

**Intent Name:** `policy_renewal`

**Purpose:**
Allows authenticated customers to renew an active or expiring insurance policy.

**Example User Queries:**

- Renew my policy.
- My policy is expiring.
- Extend my insurance.
- Renew my Motor Insurance.
- Renew my Health Insurance.

**API Used:**

- renewPolicy()

---

## 7. Customer Update Request

**Intent Name:** `update_request`

**Purpose:**
Allows authenticated customers to submit requests for updating personal information such as address, email, mobile number, or date of birth. Requests are submitted for manual approval before changes are applied.

**Example User Queries:**

- Update my address.
- Change my mobile number.
- Update my email address.
- Change my date of birth.
- I need to update my policy information.

**API Used:**

- RequestUpdate()

---

## 8. Update Request Status

**Intent Name:** `request_status`

**Purpose:**
Allows customers to check the status of previously submitted update requests.

**Example User Queries:**

- Check my update request status.
- Track my request.
- Has my request been approved?
- Show my request status.
- What is the status of my update request?

**API Used:**

- getRequestStatus()

---

## 9. Human Escalation

**Intent Name:** `agent_escalation`

**Purpose:**
Transfers the customer to a live support agent when the request cannot be resolved automatically or when the customer explicitly requests human assistance.

**Example User Queries:**

- Talk to an agent.
- Connect me to customer support.
- I need human assistance.
- Transfer me to a representative.
- Speak to a customer support executive.

**APIs Used:**

- createCase()
- escalateToAgent()

---

## Intent Routing Summary

| Intent | Authentication Required | Backend API |
|---------|-------------------------|-------------|
| New User Onboarding | No | getProductCoverage(), OnBoardUser() |
| Policy Inquiry | Yes | getPolicyDetails() |
| Benefits Information | Yes | getBenefitsInfo() |
| Claim Status | Yes | getClaimsStatus() |
| New Claim Initiation | Yes | initiateClaim() |
| Policy Renewal | Yes | renewPolicy() |
| Customer Update Request | Yes | RequestUpdate() |
| Update Request Status | Yes | getRequestStatus() |
| Human Escalation | Yes* | createCase(), escalateToAgent() |

> *Human escalation can also occur automatically in cases such as repeated authentication failures, webhook errors, no-match, or no-input events.
