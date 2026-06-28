# QA Testing Execution Plan

## Objective

This document defines the overall testing workflow for the Insurance Conversational AI Voice Agent. It describes how the QA team will validate the application after development, record results, report defects, and verify fixes before the final demo.

---

# Overall Testing Workflow

```text
Development Completed
        ↓
Execute Happy Path Testing
        ↓
Execute Edge Case & Negative Testing
        ↓
Log Test Results
        ↓
Report Defects
        ↓
Developer Fixes Defects
        ↓
Retest Fixed Features
        ↓
Regression Testing
        ↓
QA Sign-off
```

---

# Phase 1 – Happy Path Testing

## Purpose

The first phase verifies that all core business functionalities work correctly under normal conditions.

## Scope

The following modules will be tested:

* Authentication
* New User Onboarding
* Policy Inquiry
* Benefits Information
* Claim Status
* New Claim Initiation
* Policy Renewal
* Agent Escalation

## Example

**Scenario**

Customer enters a valid phone number, DOB, and verification answers.

**Expected Result**

Customer is authenticated successfully and can continue to the requested insurance service.

If all expected behaviour is observed, the test case will be marked as **PASS**.

---

# Phase 2 – Edge Case & Negative Testing

## Purpose

Once the happy path is verified, the chatbot will be tested with invalid inputs and unexpected situations to ensure it behaves correctly.

## Scope

Examples include:

* Invalid phone number
* Wrong DOB
* Invalid Policy ID
* Invalid Claim ID
* API timeout
* API error
* User silence
* User changes intent
* No active policy
* Claim already closed

## Example

**Scenario**

Customer enters an invalid Policy ID.

**Expected Result**

The chatbot informs the customer that the policy could not be found, prompts for a valid Policy ID, follows the retry policy, and escalates if the retry limit is exceeded.

Each edge case will be marked as **PASS** or **FAIL** after execution.

---

# Phase 3 – Test Execution, Bug Tracking & Regression Testing

## Purpose

Record testing results, report defects, verify bug fixes, and ensure that existing functionality continues to work after changes.

## Step 1 – Test Execution

Every executed test case will be recorded.

### Example

| Test ID | Module         | Result | Remarks                           |
| ------- | -------------- | ------ | --------------------------------- |
| TC-001  | Authentication | PASS   | Working as expected               |
| TC-002  | Policy Inquiry | FAIL   | Incorrect policy details returned |

---

## Step 2 – Bug Tracking

Whenever a test case fails, a bug will be logged.

### Example

| Bug ID  | Module         | Severity | Expected Result                  | Actual Result          | Status |
| ------- | -------------- | -------- | -------------------------------- | ---------------------- | ------ |
| BUG-001 | Policy Inquiry | High     | Correct policy details displayed | Wrong policy displayed | Open   |

---

## Step 3 – Retesting

After the developer fixes the reported issue, the failed test case will be executed again.

If the issue is resolved, the bug status will be updated to **Closed**.

---

## Step 4 – Regression Testing

Previously passed test cases will be executed again to verify that new code changes have not affected existing functionality.

### Example

After fixing **Claim Status**, **Authentication** and **Policy Inquiry** will also be tested again to ensure they still function correctly.

---

# Final Deliverables

At the end of testing, the QA team will produce:

* Test Execution Report
* Bug Report
* Final Test Summary Report
* QA Sign-off for Demo

---

# Reporting Templates

The following reports will be maintained throughout the testing lifecycle to document execution progress, defects, and overall testing status.

---

## 1. Test Execution Report

### Purpose

Tracks the execution status of every test case performed during Happy Path and Edge Case testing.

### Proposed Format

| Test ID     | Module         | Test Scenario     | Tester | Execution Date | Result | Remarks                     |
| ----------- | -------------- | ----------------- | ------ | -------------- | ------ | --------------------------- |
| TC-AUTH-001 | Authentication | Valid Login       | Name   | DD/MM/YYYY     | PASS   | Authentication successful   |
| TC-POL-002  | Policy Inquiry | Invalid Policy ID | Name   | DD/MM/YYYY     | FAIL   | Policy details not returned |

---

## 2. Bug Report

### Purpose

Records every defect identified during testing and tracks its resolution.

### Proposed Format

| Bug ID  | Related Test Case | Module         | Severity | Priority | Expected Result                | Actual Result              | Assigned To | Status |
| ------- | ----------------- | -------------- | -------- | -------- | ------------------------------ | -------------------------- | ----------- | ------ |
| BUG-001 | TC-POL-002        | Policy Inquiry | High     | High     | Display correct policy details | Incorrect policy displayed | Developer   | Open   |

---

## 3. Retest Verification Report

### Purpose

Verifies that defects reported by QA have been fixed successfully.

### Proposed Format

| Bug ID  | Related Test Case | Retest Date | Result | Verified By | Remarks                     |
| ------- | ----------------- | ----------- | ------ | ----------- | --------------------------- |
| BUG-001 | TC-POL-002        | DD/MM/YYYY  | PASS   | Name        | Issue resolved successfully |

---

## 4. Final Test Summary Report

### Purpose

Provides an overall summary of testing activities before project sign-off.

### Proposed Format

| Metric                    |          Value |
| ------------------------- | -------------: |
| Total Test Cases Executed |             80 |
| Passed                    |             75 |
| Failed                    |              5 |
| Total Bugs Logged         |             12 |
| Open Bugs                 |              1 |
| Closed Bugs               |             11 |
| Overall QA Status         | Ready for Demo |

---

# QA Sign-off

The project will be considered ready for demonstration when:

* All Happy Path test cases have passed.
* Critical Edge Cases have been validated.
* No Critical or High severity defects remain open.
* Regression testing has been completed successfully.
* QA approval has been provided.
