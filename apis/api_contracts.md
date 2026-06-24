# API Contracts

## validateUser()

### Purpose
Authenticate customer using phone, DOB, and verification answers.

### Request
```json
{
  "phone": "9876543210",
  "dob": "1990-05-15",
  "verificationAnswers": ["Greenfield School", "Sharma"]
}
```

### Response
``json
{
  "authenticated": true,
  "customerId": "C001",
  "customerName": "Amit Verma"
}
``

## getPolicyDetails(policy_id)

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

## getClaimsStatus(claim_id)

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

## initiateClaim(policy_id)

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

## getBenefitsInfo(policy_id)

### Request
```json
{
  "policyId": "P101"
}
```

### Response
```json
{
  "benefits": ["Accident Cover", "Cashless Garage", "Roadside Assistance"]
}
```

## renewPolicy(policy_id)

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

## createCase(issue)

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

## escalateToAgent(ticket_id)

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
