# Authentication Test Cases

## TC-AUTH-001: Valid Authentication
Steps:
1. Enter valid registered mobile number.
2. Enter valid DOB.
3. Answer two verification questions correctly.

Expected Result:
Customer is authenticated successfully.

## TC-AUTH-002: Invalid Mobile Number
Expected Result:
System asks the customer to retry.

## TC-AUTH-003: Invalid DOB
Expected Result:
System asks the customer to retry.

## TC-AUTH-004: Incorrect Verification Answers
Expected Result:
System increments retry count.

## TC-AUTH-005: Three Failed Attempts
Expected Result:
System escalates customer to live support agent.

## TC-AUTH-006: Session Persistence
Expected Result:
Customer is not asked to authenticate again within the same active session.
