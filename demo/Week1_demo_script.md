# Week 1 Demo Script

## Demo Objective
Show that the Insurance Voice Agent can authenticate a customer, identify intent, route to the correct flow, and complete happy path journeys using mock APIs.

## Demo Sequence

### 1. Authentication
User provides phone number, DOB, and verification answers.  
Expected: Authentication successful.

### 2. Policy Inquiry
User says: "Check my policy details."  
Expected: Bot displays policy details.

### 3. Benefits Information
User says: "What benefits do I have?"  
Expected: Bot displays benefits.

### 4. Claim Status
User says: "Track my claim."  
Expected: Bot displays claim status.

### 5. New Claim Initiation
User says: "I want to file a claim."  
Expected: Bot creates a claim and provides Claim ID.

### 6. Policy Renewal
User says: "Renew my policy."  
Expected: Bot renews policy and provides new validity date.

### 7. Agent Escalation
User says: "Talk to an agent."  
Expected: Bot creates ticket and transfers conversation context.

## Closing Line
This Week 1 demo validates the happy path foundation. Week 2 will focus on edge cases, fallbacks, retries, and advanced testing.
