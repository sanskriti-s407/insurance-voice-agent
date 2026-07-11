# API Contracts

## validateUser()

### Purpose
Authenticate customer using phone number, date of birth, and verification answers before granting access to insurance services.

### Request
```json
{
  "phone": "9876543210",
  "dob": "1990-05-15",
  "verificationAnswers": ["Greenfield School", "Sharma"]
}
```

### Response
```json
{
  "authenticated": true,
  "customerId": "C001",
  "customerName": "Amit Verma"
}
```

---

## getPolicyDetails(policy_id)

### Purpose
Retrieve the details of a customer's insurance policy using the policy ID.

### Request
```json
{
  "policyId": "P101"
}
```

### Response
```json
{
  "policyId": "P101",
  "type": "Vehicle Insurance",
  "status": "Active",
  "coverageDetails": "Accident Cover, Cashless Garage, Roadside Assistance",
  "expiryDate": "2027-01-15"
}
```

---

## getClaimsStatus(claim_id)

### Purpose
Retrieve the current status and details of an insurance claim.

### Request
```json
{
  "claimId": "CLM12345"
}
```

### Response
```json
{
  "claimId": "CLM12345",
  "status": "In Progress",
  "amount": 25000,
  "lastUpdate": "2025-05-10"
}
```

---

## initiateClaim(policy_id)

### Purpose
Initiate a new insurance claim for the specified policy.

### Request
```json
{
  "policyId": "P101"
}
```

### Response
```json
{
  "status": "Claim Initiated",
  "claimId": "CLM12345"
}
```

---

## getBenefitsInfo(policy_id)

### Purpose
Retrieve the list of benefits and coverage included in a policy.

### Request
```json
{
  "policyId": "P101"
}
```

### Response
```json
{
  "benefits": [
    "Accident Cover",
    "Cashless Garage",
    "Roadside Assistance"
  ]
}
```

---

## renewPolicy(policy_id)

### Purpose
Renew an existing insurance policy and return the updated validity period.

### Request
```json
{
  "policyId": "P101"
}
```

### Response
```json
{
  "status": "Renewed",
  "validTill": "2028-01-15"
}
```

---

## createCase(issue)

### Purpose
Create a customer support case for issues that require further investigation or assistance.

### Request
```json
{
  "issue": "Customer requested human assistance",
  "customerId": "C001"
}
```

### Response
```json
{
  "status": "Case Created",
  "ticketId": "T56789"
}
```

---

## escalateToAgent(ticket_id)

### Purpose
Transfer the customer's conversation and case details to a live support agent.

### Request
```json
{
  "ticketId": "T56789",
  "conversationContext": "Customer requested escalation after unresolved issue."
}
```

### Response
```json
{
  "status": "Transferred",
  "agentAvailable": true
}
```

---

## getProductCoverage()

### Purpose
Retrieve the coverage details, eligibility, and premium information for an insurance product.

### Request
```json
{
  "productType": "Vehicle Insurance"
}
```

### Response
```json
{
  "productType": "Vehicle Insurance",
  "coverage": [
    "Accident Cover",
    "Third Party Liability",
    "Cashless Garage",
    "Roadside Assistance"
  ],
  "eligibility": "Vehicle must be registered in India",
  "startingPremium": 4500
}
```

---

## OnBoardUser()

### Purpose
Register a new customer and create a new insurance policy after successful onboarding.

### Request
```json
{
  "customerName": "Amit Verma",
  "phone": "9876543210",
  "dob": "1990-05-15",
  "productType": "Vehicle Insurance",
  "email": "amit.verma@example.com",
  "address": "Delhi, India"
}
```

### Response
```json
{
  "status": "Success",
  "customerId": "C001",
  "policyId": "P101",
  "message": "Customer onboarded successfully."
}
```

---

## RequestUpdate()

### Purpose
Submit a request to update customer or policy information for review and approval.

### Request
```json
{
  "customerId": "C001",
  "requestType": "Update DOB",
  "newValue": "2003-04-12"
}
```

### Response
```json
{
  "requestId": "REQ1001",
  "status": "Submitted",
  "message": "Your update request has been received and is under review."
}
```

---

## getRequestStatus()

### Purpose
Retrieve the current status of a previously submitted customer update request.

### Request
```json
{
  "requestId": "REQ1001"
}
```

### Response
```json
{
  "requestId": "REQ1001",
  "status": "Approved",
  "lastUpdated": "2026-07-11",
  "remarks": "Customer address updated successfully."
}
```
