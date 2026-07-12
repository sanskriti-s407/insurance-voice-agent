# Week 2 Edge Cases

## Authentication Edge Cases
- Invalid phone number
- Invalid date of birth
- Incorrect verification answers
- Authentication failure after 3 attempts
- Session timeout during authentication

## New User Onboarding Edge Cases
- Invalid vehicle number
- Invalid chassis number
- Unsupported insurance product selected

## Policy Services Edge Cases
- Invalid policy selection
- Expired policy
- Policy not eligible for renewal
- Customer cancels policy selection

## Claims Edge Cases
- Claim already closed
- Claim cannot be initiated for inactive policy

## Update Request Edge Cases
- Invalid update information
- Duplicate update request already pending
- Invalid Request ID

## API Edge Cases
- API timeout
- API unavailable
- Internal server error
- Empty response
- Invalid response format

## Conversation Edge Cases
- Unknown intent
- User remains silent
- User changes intent mid-conversation
- User repeatedly requests a human agent
- Missing required information

## Session Management Edge Cases
- Session timeout
- Missing session parameters
- Authentication expired
- Invalid session data

## Proactive Renewal Edge Cases
- No policies nearing expiry
- Multiple policies eligible for renewal
- Renewal already completed
