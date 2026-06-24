# Webhooks

## Webhook Resource
Name: Insurance_Backend_Webhook

## Webhook Actions

### validateUser()
Authenticates customer using mobile number, DOB, and verification answers.

### getProductCoverage()
Retrieves insurance product catalogue and coverage information.

### sendOTP(phone)
Sends OTP to new customer's mobile number.

### verifyOTP(phone, otp)
Verifies OTP entered by customer.

### verifyVehicle(vehicle_number, chassis_number)
Validates motor insurance vehicle details.

### createPolicy(product_type, customer_details, vehicle_details)
Creates a new policy for a new customer.

### getPolicyDetails(policy_id)
Fetches policy details.

### getBenefitsInfo(policy_id)
Fetches policy benefits and inclusions.

### getClaimsStatus(claim_id)
Retrieves claim status and updates.

### initiateClaim(policy_id)
Creates a new claim.

### renewPolicy(policy_id)
Processes policy renewal.

### createCase(issue)
Creates support case or ticket.

### escalateToAgent(ticket_id)
Transfers conversation to live agent with context.
