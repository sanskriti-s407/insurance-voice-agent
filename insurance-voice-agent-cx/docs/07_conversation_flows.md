# Conversation Flows

## Authentication Flow
Customer starts call  
↓  
Voice agent welcomes customer  
↓  
Bot collects registered mobile number  
↓  
System validates mobile number  
↓  
Bot collects date of birth  
↓  
System validates DOB  
↓  
Bot asks verification question 1  
↓  
Customer answers question 1  
↓  
Bot asks verification question 2  
↓  
Customer answers question 2  
↓  
System calls validateUser()  
↓  
Authentication successful  
↓  
System retrieves customer profile and policies  
↓  
Customer proceeds to intent routing  

## New User Onboarding Flow
Customer requests a new insurance policy  
↓  
Bot retrieves available insurance products  
↓  
Bot presents product options  
↓  
Customer selects product  
↓  
Bot collects mobile number and sends OTP  
↓  
Customer verifies OTP  
↓  
Bot collects DOB and security question answers  
↓  
For motor insurance, bot collects vehicle and chassis number  
↓  
System validates vehicle details  
↓  
System creates policy  
↓  
Bot shares new Policy ID and expiry date  

## Policy Inquiry Flow
Customer requests policy details  
↓  
System verifies customer is authenticated  
↓  
System retrieves policies linked to customer  
↓  
Bot displays available policies  
↓  
Customer selects policy  
↓  
System calls getPolicyDetails(policy_id)  
↓  
Bot provides policy details  
↓  
End conversation or ask if further help is needed  

## Benefits Information Flow
Customer asks for policy benefits  
↓  
System verifies customer is authenticated  
↓  
System retrieves customer policies  
↓  
Customer selects policy  
↓  
System calls getBenefitsInfo(policy_id)  
↓  
Bot provides benefit details, coverage information, and included services  
↓  
End conversation or ask if further help is needed  

## Claim Status Flow
Customer asks for claim status  
↓  
System verifies customer is authenticated  
↓  
System retrieves policies  
↓  
Customer selects policy  
↓  
System retrieves claims under selected policy  
↓  
Customer selects claim  
↓  
System calls getClaimsStatus(claim_id)  
↓  
Bot provides claim status, amount, and latest update  
↓  
End conversation or ask if further help is needed  

## New Claim Initiation Flow
Customer requests to file a claim  
↓  
System verifies customer is authenticated  
↓  
System retrieves customer policies  
↓  
Customer selects policy  
↓  
System calls initiateClaim(policy_id)  
↓  
Claim is created successfully  
↓  
System generates Claim ID  
↓  
Bot shares Claim ID with customer  

## Policy Renewal Flow
Customer requests policy renewal  
↓  
System verifies customer is authenticated  
↓  
System retrieves customer policies  
↓  
Bot displays policies available for renewal  
↓  
Customer selects policy  
↓  
System calls renewPolicy(policy_id)  
↓  
Policy renewal is processed successfully  
↓  
System returns renewal status and new validity date  
↓  
Bot confirms renewal  

## Agent Escalation Flow
Customer requests human assistance  
↓  
System verifies customer is authenticated  
↓  
Bot asks for escalation reason  
↓  
Customer provides reason  
↓  
System calls createCase()  
↓  
System generates ticket number  
↓  
System transfers conversation context  
↓  
System calls escalateToAgent()  
↓  
Customer is connected to live support agent
