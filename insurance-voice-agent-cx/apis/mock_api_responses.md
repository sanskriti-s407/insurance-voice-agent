# Mock API Responses

```python
def validateUser(phone, dob):
    return {
        "authenticated": True,
        "customerName": "Amit Verma"
    }

def getPolicyDetails(policy_id):
    return {
        "policyId": policy_id,
        "type": "Vehicle Insurance",
        "status": "Active",
        "expiryDate": "2027-01-15"
    }

def getClaimsStatus(claim_id):
    return {
        "claimId": claim_id,
        "status": "In Progress",
        "amount": 25000
    }

def initiateClaim(policy_id):
    return {
        "status": "Claim Initiated",
        "claimId": "CLM12345"
    }

def getBenefitsInfo(policy_id):
    return {
        "benefits": ["Accident Cover", "Cashless Garage", "Roadside Assistance"]
    }

def renewPolicy(policy_id):
    return {
        "status": "Renewed",
        "validTill": "2028-01-15"
    }

def createCase(issue):
    return {
        "status": "Case Created",
        "ticketId": "T56789"
    }
```
