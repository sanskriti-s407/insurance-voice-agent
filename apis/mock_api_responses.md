# Mock API Responses

```python
def validateUser(phone, dob):
    return {
        "authenticated": True,
        "customerId": "C001",
        "customerName": "Amit Verma"
    }


def getPolicyDetails(policy_id):
    return {
        "policyId": policy_id,
        "type": "Vehicle Insurance",
        "status": "Active",
        "coverageDetails": "Accident Cover, Cashless Garage, Roadside Assistance",
        "expiryDate": "2027-01-15"
    }


def getClaimsStatus(claim_id):
    return {
        "claimId": claim_id,
        "status": "In Progress",
        "amount": 25000,
        "lastUpdate": "2025-05-10"
    }


def initiateClaim(policy_id):
    return {
        "status": "Claim Initiated",
        "claimId": "CLM12345"
    }


def getBenefitsInfo(policy_id):
    return {
        "benefits": [
            "Accident Cover",
            "Cashless Garage",
            "Roadside Assistance"
        ]
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


def getProductCoverage(product_type):
    return {
        "productType": product_type,
        "coverage": [
            "Accident Cover",
            "Third Party Liability",
            "Cashless Garage",
            "Roadside Assistance"
        ],
        "eligibility": "Vehicle must be registered in India",
        "startingPremium": 4500
    }


def OnBoardUser(customer_name, phone, dob, product_type, email, address):
    return {
        "status": "Success",
        "customerId": "C001",
        "policyId": "P101",
        "message": "Customer onboarded successfully."
    }


def RequestUpdate(customer_id, request_type, new_value):
    return {
        "requestId": "REQ1001",
        "status": "Submitted",
        "message": "Your update request has been received and is under review."
    }


def getRequestStatus(request_id):
    return {
        "requestId": request_id,
        "status": "Approved",
        "lastUpdated": "2026-07-11",
        "remarks": "Customer address updated successfully."
    }
```
