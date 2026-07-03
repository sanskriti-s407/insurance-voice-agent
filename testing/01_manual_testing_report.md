# Manual Testing Report

## Insurance Conversational AI Chatbot

---

# 1. Introduction

Manual testing was performed to validate the functionality of the Insurance Conversational AI chatbot before running automated evaluations. The objective was to verify that every chatbot feature worked as expected from an end-user perspective.

Unlike automated testing, manual testing focuses on interacting with the chatbot naturally and confirming that it provides the correct response, follows the expected conversation flow, triggers the appropriate backend tools, and handles invalid user inputs gracefully.

The chatbot was developed using **Google Cloud CX Agent Studio** and supports multiple insurance-related services including policy inquiry, claims management, onboarding, policy renewal, benefits information, and human agent escalation.

---

# 2. Objectives

The primary objectives of manual testing were:

- Verify all business functionalities work correctly.
- Validate chatbot conversation flow.
- Ensure correct intent recognition.
- Verify authentication flow.
- Check API and tool execution.
- Test normal user interactions.
- Test edge cases and invalid inputs.
- Identify functional defects before automated evaluations.

---

# 3. Testing Environment

| Parameter | Details |
|-----------|---------|
| Platform | Google Cloud CX Agent Studio |
| Testing Type | Manual Functional Testing |
| Application | Insurance Conversational AI Chatbot |
| Evaluation Method | Manual User Interaction |

---

# 4. Testing Approach

Each chatbot feature was tested individually by entering predefined user queries and comparing the chatbot response with the expected business outcome.

During testing, the following checkpoints were verified:

- Correct intent detection
- Authentication flow
- Conversation continuity
- Backend tool execution
- API response
- Final chatbot response
- Error handling

Every executed test case was recorded in the Manual Testing Excel sheet along with its execution status and remarks.

---

# 5. Modules Tested

## Authentication

- Valid Login
- Invalid Date of Birth
- Incorrect Verification Answer
- Maximum Retry Limit
- Session Maintenance

## New User Onboarding

- Motor Policy Creation
- Health Policy Creation
- Life Policy Creation

## Policy Services

- Policy Details
- Policy Renewal
- Benefits Information

## Claims

- Claim Status
- New Claim Registration

## Human Support

- Live Agent Escalation

## Intent Routing

- Route to Policy Inquiry
- Route to Benefits Information
- Route to Claim Status
- Route to Policy Renewal
- Route to New User Onboarding
- Route to Human Escalation

---

# 6. Edge Case Testing

The chatbot was also validated using multiple abnormal scenarios.

## Authentication Edge Cases

- Invalid phone number
- Invalid Date of Birth
- Incorrect verification answer
- Authentication failure

## Policy Edge Cases

- No active policy found
- Expired policy
- Invalid policy ID

## Claim Edge Cases

- No claims found
- Invalid claim ID
- Closed claim status

## API Edge Cases

- API timeout
- API error
- Empty API response
- Invalid API response

## Conversation Edge Cases

- User silence
- Unrelated user input
- User changes intent
- Repeated request for human support

---

# 7. Sample Test Cases

| Module | Test Case | Result |
|---------|-----------|--------|
| Policy Inquiry | Retrieve Policy Details | Pass |
| Claim Status | Retrieve Claim Status | Pass |
| Benefits Information | Retrieve Benefits | Pass |
| Policy Renewal | Renew Policy | Pass |
| Agent Escalation | Transfer to Live Agent | Pass |
| Authentication | Invalid DOB | Pass |
| Conversation | User Changes Intent | Pass |

---

# 8. Test Results

Manual testing confirmed that the chatbot successfully handled the majority of business functionalities.

### Successfully Validated

- Authentication workflow
- Policy Inquiry
- Benefits Information
- Claim Status
- New Claim Registration
- Policy Renewal
- Human Escalation
- Intent Routing
- New User Onboarding

Edge cases such as invalid authentication details, expired policies, invalid claim IDs, conversation interruptions, and repeated escalation requests were also verified.

The results obtained during manual testing provided confidence to proceed with automated Golden Evaluations.

---

# 9. Deliverables

The following artifacts were produced during manual testing:

- Manual Test Case Excel Sheet
- Test Execution Results
- Pass/Fail Status
- Execution Remarks
- Identified Defects (documented separately)

---

# 10. Conclusion

Manual testing verified that the Insurance Conversational AI chatbot was functionally stable and capable of handling both standard and exceptional user interactions.

The successful completion of manual testing established a reliable baseline for conducting Golden Evaluations and Scenario-Based Evaluations.
