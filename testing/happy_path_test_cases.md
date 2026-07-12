# Happy Path Test Cases

## TC-001: Customer Authentication

**Objective:** Verify successful customer authentication.

**Input:**
- Registered phone number
- Valid DOB
- Correct verification answers

**Expected Result:**
- Customer is authenticated successfully.
- Customer profile is retrieved.
- All associated policies are displayed.
- Customer is routed to Intent Routing.

---

## TC-002: New User Onboarding

**Objective:** Verify successful onboarding of a new customer.

**Input:**
"I want to buy a new insurance policy."

**Expected Result:**
- Available insurance products are displayed.
- Customer selects Motor, Health, or Life Insurance.
- Product coverage is displayed.
- OTP is sent and verified.
- Customer details are collected.
- For Motor Insurance, vehicle details are validated.
- New policy is created successfully.
- Policy ID is generated and displayed.

---

## TC-003: Policy Services – Policy Details

**Objective:** Verify retrieval of policy information.

**Input:**
"Show my policy details."

**Expected Result:**
- Customer's policies are displayed.
- Customer selects a policy.
- Policy details including type, status, premium, and expiry date are displayed.

---

## TC-004: Policy Services – Benefits Information

**Objective:** Verify retrieval of policy benefits.

**Input:**
"What benefits are included in my policy?"

**Expected Result:**
- Customer selects a policy.
- Benefits and coverage details are displayed successfully.

---

## TC-005: Policy Services – Policy Renewal

**Objective:** Verify successful policy renewal.

**Input:**
"Renew my policy."

**Expected Result:**
- Eligible policies are displayed.
- Customer selects a policy.
- Renewal is processed successfully.
- Updated validity date is displayed.

---

## TC-006: Claims – Claim Status

**Objective:** Verify claim status retrieval.

**Input:**
"Check my claim status."

**Expected Result:**
- Customer's claims are displayed.
- Customer selects a claim.
- Claim status, amount, and last update are displayed.

---

## TC-007: Claims – New Claim

**Objective:** Verify successful claim creation.

**Input:**
"I want to file a new claim."

**Expected Result:**
- Customer selects a policy.
- Claim request is submitted.
- New Claim ID is generated and displayed.

---

## TC-008: Update Request Submission

**Objective:** Verify customer update request creation.

**Input:**
"I want to update my phone number."

**Expected Result:**
- Bot collects updated information.
- Update request is submitted.
- Request ID is generated.
- Customer is informed that the request will be reviewed before approval.

---

## TC-009: Update Request Status

**Objective:** Verify update request tracking.

**Input:**
"Check my update request status."

**Expected Result:**
- Customer provides Request ID.
- Current request status is displayed.
- Latest update and remarks are shown.

---

## TC-010: Human Escalation

**Objective:** Verify seamless live-agent transfer.

**Input:**
"I want to speak to a customer support representative."

**Expected Result:**
- Support case is created.
- Case ID is generated.
- Conversation context is transferred.
- Customer is connected to a live support agent.

---

## TC-011: Proactive Renewal Reminder

**Objective:** Verify proactive renewal notification.

**Input:**
Customer logs in with a policy nearing expiry.

**Expected Result:**
- Bot detects the upcoming expiry.
- Customer is proactively informed about the renewal.
- Bot asks whether the customer wants to renew the policy.
