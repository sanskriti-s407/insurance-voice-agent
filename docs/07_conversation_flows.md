# Conversation Flows

## - New User Onboarding Flow

1. Customer requests a new insurance policy.
2. Bot retrieves available insurance products.
3. Bot presents product options.
4. Customer selects a product.
5. Bot collects the customer's mobile number and sends an OTP.
6. Customer verifies the OTP.
7. Bot collects the customer's date of birth and security question answers.
8. For Motor Insurance, the bot collects the vehicle number and chassis number.
9. System validates the vehicle details.
10. System creates the insurance policy.
11. Bot shares the newly generated Policy ID and policy expiry date.

---

## - Policy Inquiry Flow

1. Customer requests policy details.
2. System verifies that the customer is authenticated.
3. System retrieves policies associated with the customer.
4. Bot displays the available policies.
5. Customer selects a policy.
6. System calls getPolicyDetails(policy_id).
7. Bot provides policy information including status, coverage, and expiry details.
8. Bot asks whether additional assistance is required.

---

## - Benefits Information Flow

1. Customer requests policy benefits.
2. System verifies that the customer is authenticated.
3. System retrieves customer policies.
4. Customer selects a policy.
5. System calls getBenefitsInfo(policy_id).
6. Bot provides benefits, coverage details, and included services.
7. Bot asks whether additional assistance is required.

---

## Claim Status Flow

1. Customer requests claim status information.
2. System verifies that the customer is authenticated.
3. System retrieves customer policies.
4. Customer selects a policy.
5. System retrieves claims associated with the selected policy.
6. Customer selects a claim.
7. System calls getClaimsStatus(claim_id).
8. Bot provides claim status, claim amount, and latest update.
9. Bot asks whether additional assistance is required.

---

## New Claim Initiation Flow

1. Customer requests to register a new claim.
2. System verifies that the customer is authenticated.
3. System retrieves customer policies.
4. Customer selects a policy.
5. System calls initiateClaim(policy_id).
6. Claim request is created successfully.
7. System generates a Claim ID.
8. Bot shares the generated Claim ID with the customer.
9. Bot asks whether additional assistance is required.

---

## Policy Renewal Flow

1. Customer requests policy renewal.
2. System verifies that the customer is authenticated.
3. System retrieves customer policies.
4. Bot displays policies available for renewal.
5. Customer selects a policy.
6. System calls renewPolicy(policy_id).
7. Policy renewal is processed successfully.
8. System returns renewal status and updated validity date.
9. Bot confirms successful renewal and shares the new validity date.
10. Bot asks whether additional assistance is required.

---

## Agent Escalation Flow

1. Customer requests human assistance.
2. System verifies that the customer is authenticated.
3. Bot asks for the reason for escalation.
4. Customer provides the escalation reason.
5. System calls createCase().
6. System generates a support ticket number.
7. System transfers conversation context and customer information.
8. System calls escalateToAgent().
9. Customer is connected to a live support agent.
10. Bot provides the generated ticket number for reference.
