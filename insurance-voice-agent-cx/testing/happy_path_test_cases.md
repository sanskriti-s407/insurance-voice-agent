# Happy Path Test Cases

## TC-001: Authentication Success
Input: Valid phone, DOB, and verification answers  
Expected Result: Customer is authenticated and routed to intent selection.

## TC-002: New User Onboarding
Input: "I want to buy a new policy"  
Expected Result: Product options are shown, OTP is verified, and a new policy ID is generated.

## TC-003: Policy Inquiry
Input: "Check my policy details"  
Expected Result: Policy details are displayed.

## TC-004: Benefits Information
Input: "What benefits do I have?"  
Expected Result: Benefit details and included services are displayed.

## TC-005: Claim Status
Input: "Track my claim"  
Expected Result: Claim status, claim amount, and last update are displayed.

## TC-006: New Claim Initiation
Input: "I want to file a claim"  
Expected Result: New claim is created and Claim ID is generated.

## TC-007: Policy Renewal
Input: "Renew my policy"  
Expected Result: Policy renewal confirmation and new validity date are displayed.

## TC-008: Agent Escalation
Input: "Talk to an agent"  
Expected Result: Ticket is created and customer is transferred to live agent.
