# Webhooks

## Webhook Resource

**Name:** `Insurance_Backend_Webhook`

---

## Webhook Actions

### validateUser()

Authenticates an existing customer using the registered mobile number, date of birth, and verification answers.


### getProductCoverage()

Retrieves the available insurance products along with their coverage details, eligibility criteria, and premium information.


### OnBoardUser()

Registers a new customer and creates a new insurance policy after collecting the required customer details.


### getPolicyDetails()

Retrieves detailed information about the selected insurance policy.


### getBenefitsInfo()

Fetches the benefits, coverage, and services included in the selected insurance policy.


### getClaimsStatus()

Retrieves the latest status and details of an existing insurance claim.


### initiateClaim()

Creates a new insurance claim for the selected policy.


### renewPolicy()

Processes the renewal of an existing insurance policy and returns the updated validity period.


### RequestUpdate()

Submits a customer information update request (such as address, mobile number, email, or date of birth) for processing.


### getRequestStatus()

Retrieves the current status of a previously submitted customer update request.


### createCase()

Creates a customer support case for requests requiring manual assistance or investigation.


### escalateToAgent()

Transfers the conversation, customer details, and complete conversation context to a live support agent.
