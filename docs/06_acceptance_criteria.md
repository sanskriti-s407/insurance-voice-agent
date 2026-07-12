# Acceptance Criteria

### 1. Customer Onboarding

- **AC-ONB-001**  
Given a new customer wants to purchase an insurance policy  
When the customer selects an insurance product  
Then the system shall retrieve and display the product coverage details.

- **AC-ONB-002**  
Given the customer provides the required personal information  
When OnBoardUser() is executed  
Then the system shall create a customer profile and generate a new Policy ID.

- **AC-ONB-003**  
Given onboarding is successful  
When the response is received  
Then the system shall display the customer ID, Policy ID, and confirmation message.

### 2. Policy Services

#### Policy Inquiry

- **AC-POL-001**  
Given the customer is authenticated  
When the customer selects one of the available policies  
Then the system shall retrieve the corresponding policy details.

- **AC-POL-002**  
Given policy details are available  
When getPolicyDetails() returns a response  
Then the system shall display the policy type, status, coverage details, and expiry date.

#### Benefits Information

- **AC-BEN-001**  
Given the customer is authenticated  
When the customer selects a policy  
Then the system shall retrieve the policy benefits.

- **AC-BEN-002**  
Given benefits information is available  
When getBenefitsInfo() returns a response  
Then the system shall display the policy benefits, coverage information, and included services.

#### Policy Renewal

- **AC-REN-001**  
Given the customer is authenticated  
When the customer selects an eligible policy  
Then the system shall initiate the policy renewal process.

- **AC-REN-002**  
Given policy renewal is successful  
When renewPolicy() returns a response  
Then the system shall display the renewal confirmation and updated policy validity date.

- **AC-REN-003**  
Given the customer's policy is approaching its expiry date  
When the customer logs in  
Then the system shall proactively notify the customer about the upcoming renewal.

### 3. Claims

#### Claim Status

- **AC-CLS-001**  
Given the customer is authenticated  
When the customer selects a valid claim  
Then the system shall retrieve the claim status.

- **AC-CLS-002**  
Given claim details are available  
When getClaimsStatus() returns a response  
Then the system shall display the claim status, claim amount, and latest update.

#### New Claim Initiation

- **AC-CLM-001**  
Given the customer is authenticated  
When the customer selects a valid policy  
Then the system shall initiate a new claim.

- **AC-CLM-002**  
Given claim creation is successful  
When initiateClaim() returns a response  
Then the system shall generate and display a Claim ID.

### 4. Update Requests

#### Submit Update Request

- **AC-UPD-001**  
Given the customer wants to update personal information  
When RequestUpdate() is executed  
Then the system shall create an update request instead of directly modifying customer information.

- **AC-UPD-002**  
Given the update request is submitted successfully  
When the response is received  
Then the system shall generate and display a Request ID.

#### Update Request Status

- **AC-REQ-001**  
Given the customer provides a valid Request ID  
When getRequestStatus() is executed  
Then the system shall retrieve the current request status.

- **AC-REQ-002**  
Given request status information is available  
When the response is received  
Then the system shall display the request status, last updated date, and remarks.

### 5. Human Escalation

- **AC-ESC-001**  
Given the customer requests human assistance  
When createCase() is executed  
Then the system shall generate a support ticket.

- **AC-ESC-002**  
Given a support case has been created  
When escalateToAgent() is executed  
Then the customer shall be transferred to a live support agent.

- **AC-ESC-003**  
Given escalation is successful  
When the customer is connected to a live support agent  
Then the complete conversation context and ticket information shall be transferred to the agent.
