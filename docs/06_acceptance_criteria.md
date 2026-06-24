# Acceptance Criteria

### 1. New User Onboarding

- AC-NEW-001    
Given a new customer requests to buy a policy  
When the customer selects a product type  
Then the system shall retrieve and present the relevant product coverage details.

- AC-NEW-002    
Given the customer provides a mobile number  
When sendOTP(phone) is called and the customer enters the correct OTP  
Then verifyOTP(phone, otp) shall confirm phone ownership and proceed.

- AC-NEW-003
Given OTP verification is successful  
When the customer provides date of birth and security question answers  
Then the system shall capture and store the profile details for future authentication.

- AC-NEW-004    
Given the selected product is Motor Insurance  
When the customer provides vehicle number and chassis number  
Then verifyVehicle() shall validate the vehicle authenticity before policy creation.

- AC-NEW-005    
Given identity, profile, and vehicle verification are successful  
When createPolicy() is called  
Then the system shall generate and provide a new Policy ID and expiry date.

### 2. Policy Inquiry

- AC-POL-001    
Given the customer is authenticated  
When the customer selects one of the policies displayed by the system  
Then the system shall retrieve policy details successfully.

- AC-POL-002     
Given policy details are available  
When getPolicyDetails(policy_id) returns a response  
Then the system shall provide policy type, status, coverage details, and expiry date.

### 3. Benefits Information

- AC-BEN-001    
Given the customer is authenticated  
When the customer selects a displayed policy ID  
Then the system shall retrieve benefits information.

- AC-BEN-002    
Given benefits information is available  
When getBenefitsInfo(policy_id) returns a response  
Then the system shall provide benefit details, coverage information, and included services.

### 4. Claim Status

- AC-CLS-001    
Given the customer is authenticated  
When the customer selects a valid Claim ID  
Then the system shall retrieve claim status information.

- AC-CLS-002    
Given claim status information is available  
When getClaimsStatus(claim_id) returns a response  
Then the system shall provide claim status, claim amount, and latest update.

### 5. New Claim Initiation

- AC-CLM-001    
Given the customer is authenticated  
When the customer selects a valid Policy ID  
Then the system shall initiate a new claim request.

- AC-CLM-002    
Given claim creation is successful  
When initiateClaim(policy_id) returns a response  
Then the system shall generate and provide a Claim ID.

### 6. Policy Renewal

- AC-REN-001    
Given the customer is authenticated  
When the customer selects a valid Policy ID  
Then the system shall initiate the policy renewal process.

- AC-REN-002    
Given policy renewal is successful  
When renewPolicy(policy_id) returns a response  
Then the system shall provide renewal confirmation and the new validity date.

### 7. Agent Escalation

- AC-ESC-001    
Given the customer requests human assistance  
When the escalation request is initiated  
Then the system shall create a support case.

- AC-ESC-002    
Given a support case is created  
When escalateToAgent() is executed  
Then the customer shall be transferred to a live support agent.

- AC-ESC-003        
Given escalation is successful  
When the customer is connected to an agent  
Then the conversation context and case information shall be transferred to the agent.
