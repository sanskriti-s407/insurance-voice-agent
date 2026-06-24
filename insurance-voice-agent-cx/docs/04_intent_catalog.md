# Intent Catalog

## 1. New User Onboarding Intent
**Intent Name:** `new_user_onboarding`

**Purpose:** Allows a new customer to explore insurance products, verify identity, register profile details, and create a new policy.

**Example User Queries:**
- I want to buy a new policy.
- I am a new customer.
- I do not have a policy yet.
- I want to purchase vehicle insurance.
- Get me a new insurance policy.

**APIs Used:**
- getProductCoverage()
- sendOTP(phone)
- verifyOTP(phone, otp)
- verifyVehicle(vehicle_number, chassis_number)
- createPolicy(product_type, customer_details, vehicle_details)

---

## 2. Policy Inquiry Intent
**Intent Name:** `policy_inquiry`

**Purpose:** Allows customers to retrieve policy information including type, status, coverage, and expiry date.

**Example User Queries:**
- What are my policy details?
- Check my policy information.
- Show my policy status.
- Is my policy active?
- When does my policy expire?

**API Used:** getPolicyDetails(policy_id)

---

## 3. Benefits Information Intent
**Intent Name:** `benefits_information`

**Purpose:** Allows customers to view benefits, inclusions, and coverage under their policy.

**Example User Queries:**
- What benefits are included in my policy?
- Show my policy coverage.
- What am I covered for?
- Tell me my policy benefits.
- What services are included in my insurance?

**API Used:** getBenefitsInfo(policy_id)

---

## 4. Claim Status Intent
**Intent Name:** `claim_status`

**Purpose:** Allows customers to check the current status of an existing claim.

**Example User Queries:**
- What is the status of my claim?
- Check my claim progress.
- Has my claim been approved?
- Track my insurance claim.
- Claim status for claim ID CLM12345.

**API Used:** getClaimsStatus(claim_id)

---

## 5. New Claim Initiation Intent
**Intent Name:** `initiate_claim`

**Purpose:** Allows customers to register a new claim against an active policy.

**Example User Queries:**
- I want to file a claim.
- Register a new claim.
- Start a vehicle insurance claim.
- Report an accident.
- Create a claim request.

**API Used:** initiateClaim(policy_id)

---

## 6. Policy Renewal Intent
**Intent Name:** `policy_renewal`

**Purpose:** Allows customers to renew an active or expiring insurance policy.

**Example User Queries:**
- Renew my policy.
- My policy is expiring.
- I want to extend my insurance.
- Renew policy P101.
- Policy renewal.

**API Used:** renewPolicy(policy_id)

---

## 7. Agent Escalation Intent
**Intent Name:** `agent_escalation`

**Purpose:** Transfers the customer to a live support agent when the AI cannot resolve the issue.

**Example User Queries:**
- Talk to an agent.
- Connect me to customer support.
- I need human assistance.
- Transfer my call.
- Speak to a representative.

**APIs Used:**
- createCase()
- escalateToAgent()
