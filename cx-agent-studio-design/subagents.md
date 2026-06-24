# Subagent Architecture

## Authentication Subagent

Responsibilities:

* Mobile number collection
* DOB verification
* Security question validation
* Customer authentication

Invoked At:

Conversation start.

---

## Policy Management Subagent

Responsibilities:

* Policy Inquiry
* Benefits Information
* Policy Renewal

Associated APIs:

* getPolicyDetails()
* getBenefitsInfo()
* renewPolicy()

---

## Claims Management Subagent

Responsibilities:

* New Claim Initiation
* Claim Status Tracking

Associated APIs:

* initiateClaim()
* getClaimsStatus()

---

## New User Onboarding Subagent

Responsibilities:

* Product selection
* OTP verification
* Vehicle validation
* Policy creation

Associated APIs:

* getProductCoverage()
* sendOTP()
* verifyOTP()
* verifyVehicle()
* createPolicy()

---

## Agent Escalation Subagent

Responsibilities:

* Case creation
* Ticket generation
* Context transfer
* Live agent handoff

Associated APIs:

* createCase()
* escalateToAgent()
